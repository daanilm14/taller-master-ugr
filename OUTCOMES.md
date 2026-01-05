# Exercise Outcomes Submission Template

**Student/Group Name**: Daniel Lozano Moya - DS01 
**Level Completed**: Master of the universe  
**Date**: 05/01/2026

---

## 📋 Exercise Summary

### Exercise: Branch Protection Rules and Security Best Practices.
**Status**: ✅ Completed 

**What I did**:
He implementado un sistema de gobernanza y seguridad en el repositorio, cuyas tareas principales son:

1. Configuración de reglas en la rama main (protección contra push directo, requisitos previos para el pull request, ...)
2. Archivo de propietarios del código para las solicitudes de revisión.
3. Generación de claves GPG con la respectiva configuración en Git mediante la firma automática de commits.
4. Auditoría del historial en busca de datos sensibles.
5. Estudio y activación de las funciones de seguridad avanzadas de GitHub.

**Commands Used**:
```bash
gpg --full-generate-key
gpg --list-secret-keys --keyid-format=long
gpg --armor --export [KEY_ID]
git config --global user.signingkey [KEY_ID]
git config --global commit.gpgsign true

git commit -S -m "feat: Add verified commit"
git log --show-signature -1

git log -p | grep -i "password\|api_key\|secret\|token"
git rev-list --objects --all | git cat-file --batch-check='%(objecttype) %(objectname) %(objectsize) %(rest)' | sed -n 's/^blob //p' | sort --numeric-sort --key=2 | tail -n 10
# etc.
```

**Results/Output**:

Pruebas de las reglas de protección de la rama main al intentar hacer un push:

```
daniellozano:~/master/ds/git/taller-master-ugrmain$ git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 300 bytes | 300.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: error: GH006: Protected branch update failed for refs/heads/main.
remote:
remote: - Commits must have verified signatures.
remote:   Found 1 violation:
remote:
remote:   34d3d73f4c5cdc7d5b96e031f9ba30948d6a1ef3
remote:
remote: - Changes must be made through a pull request.
To github.com:daanilm14/taller-master-ugr.git
 ! [remote rejected] main -> main (protected branch hook declined)
error: failed to push some refs to 'github.com:daanilm14/taller-master-ugr.git'
```

Prueba de la creación de una clave GPG.
```
daniellozano:~/master/ds/git/taller-master-ugrfeature/protected-workflow$ gpg --list-secret-keys --keyid-format=long
gpg: checking the trustdb
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
/home/daniellozano/.gnupg/pubring.kbx
-------------------------------------
sec   rsa4096/************** 2026-01-05 [SC]
      ****************************
uid                 [ultimate] Daniel Lozano Moya <daniellozanomoya@gmail.com>
ssb   rsa4096/************** 2026-01-05 [E]
```

Pruebas del uso de la clave GPG en los commits.
```
daniellozano:~/master/ds/git/taller-master-ugrfeature/protected-workflow$ git log --show-signature -2
commit 752a72d630eeb1dfa9a3c954eead76a8addc3d6e (HEAD -> feature/protected-workflow)
gpg: Signature made Mon Jan  5 13:50:27 2026 CET
gpg:                using RSA key 
***************************************
gpg: Good signature from "Daniel Lozano Moya <daniellozanomoya@gmail.com>" [ultimate]
Author: Daniel Lozano Moya <daniellozanomoya@gmail.com>
Date:   Mon Jan 5 13:50:27 2026 +0100

    feat: Add second signed commit

commit 2de36e63b8744a64b00c7405bb5ac090ab67c487
gpg: Signature made Mon Jan  5 13:47:52 2026 CET
gpg:                using RSA key 
***************************************
gpg: Good signature from "Daniel Lozano Moya <daniellozanomoya@gmail.com>" [ultimate]
Author: Daniel Lozano Moya <daniellozanomoya@gmail.com>
Date:   Mon Jan 5 13:47:52 2026 +0100

    feat: Add first signed commit
```


Prueba del escaneo de potenciales secretos en el historial del repositorio. El escaneo reveló que no existen secretos reales en el código actual, pero detectó menciones en la documentación de ejercicios anteriores, lo cuál confirma que el patrón de búsqueda es correcto.

```
daniellozano:~/master/ds/git/taller-master-ugrfeature/protected-workflow$ git log -p | grep -i "password\|api_key\|secret\|token" | head -20
-   config/secrets.yml
-2. **Detection** - Use git-secrets or similar tools:
+2. **Detection** - Scan for potential secrets in repository history:
-   # Install git-secrets
-   git secrets --install
-   git secrets --register-aws
-3. **Remediation** - Remove accidentally committed secrets:
+   git log -p | grep -i "password\|api_key\|secret\|token" | head -20
-   git filter-repo --path config/secrets.yml --invert-paths
-   bfg --delete-files secrets.yml
-   * Use environment variables for secrets
-   * Use secret management tools (HashiCorp Vault, AWS Secrets Manager)
-   * Use GitHub Secrets for CI/CD
-   * Enable secret scanning on GitHub
-   git log -p | grep -i "password\|api_key\|secret"
-   * Enable: Secret scanning
+     - Secret scanning (if available)
+   * Best practices for secret management (environment variables, secret vaults)
-     - Demonstration of secret detection (if using tools)
-     - Pattern search for potential secrets
```

Si encontrara una credencial expuesta, el protocolo sería:

1. Rotar el secreto inmediatamente: Cambiar la contraseña o anular el token en el proveedor (AWS, Google, etc.).
2. Reescribir el historial: Usar git-filter-repo para eliminar el rastro del commit de forma permanente.
3. Análisis de impacto: Revisar logs de acceso para ver si la credencial fue explotada.

---

## 🎯 Key Learnings

**Main concepts I learned**:
1. Criptografía de Clave Pública en Git: Entender que un commit verificado garantiza que el autor es quien dice ser y que el código no ha sido alterado.
2. Gobernanza mediantre CODEOWNERS: Cómo delegar la responsabilidad de partes críticas del código a expertos de forma automatizada.
3. Inmutabilidad del Historial Sensible: El riesfo que supone subir un secreto y por qué se requieren herramientas como git-filter-repo para reescribir la historia.

**Skills I improved**:
- Configuración de entornos de firma GPG en sistemas Linux/WSL.
- Auditoría técnica de repositorios para detectar vulnerabilidades en dependencias.
- Gestión de flujos de trabajo profesionales donde el administrador también debe cumplir las normas.

---

## 🚧 Challenges Faced

### Challenge 1: GPG Signin
**Problem**: Al intentar hacer un commit firmado, GPG fallaba porque no podía abrir una ventana para pedir la contraseña en la terminal.

**Solution**: Tuve que exportar la variable de entorno GPG_TTY para indicarle a GPG en qué terminal debía interactuar

**Commands/Approach**:
```bash
export GPG_TTY=$(tty)
# Añadido a ~/.bashrc para permanencia
```

---

### Challenge 2: Bloqueo del PullRequest
**Problem**: No he podido verificar los pull request ya que con la configuración de seguridad de la rama main es necesario la aceptación de un revisor para poder fusionar las ramas. Posteriormente cambié el autor del archivo CODEOWNERS y puse el mio para ver si poniendome a mi como revisor podía verificar el pull request. Esto fue inutil ya que GitHub ompide la auto-aprobación por seguridad.

**Solution**: Entendí que ese es el comportamiento deseado en seguridad, por lo que no fue posible termininar el pull request del ejercicio ya que las reglas de seguridad de la rama también prohibían al administrador verificar el pull request sin la comprobación de un revisor.

---

## 💭 Personal Reflection

La culminación del nivel "Master of the Universe" me ha permitido comprender que la seguridad en Git no es un complemento, sino un requisito estructural del desarrollo moderno. En un ecosistema donde los ataques a la cadena de suministro de software son cada vez más frecuentes, el anonimato de los commits estándar representa un riesgo inaceptable. El uso de firmas GPG establece un protocolo de no-repudio; garantiza que cada línea de código tiene una autoría verificable y que no ha sido alterada maliciosamente entre el entorno local y el servidor.

Por otro lado, la implementación de Branch Protection Rules y CODEOWNERS introduce una fricción necesaria en el flujo de trabajo. Aunque esto pueda parecer una merma en la velocidad de desarrollo, en realidad protege la estabilidad y seguridad del producto final. En un entorno profesional, mi estrategia para la gestión de secretos se basa en la prevención absoluta: los secretos nunca deben tocar el repositorio (uso de .gitignore estricto y variables de entorno). Si ocurriera una filtración, el protocolo de remediación debe ser integral: invalidar la credencial inmediatamente, limpiar el historial mediante git-filter-repo y auditar los logs de acceso.

Integrar estas prácticas fomenta una cultura de responsabilidad compartida. La seguridad deja de ser una fase final para convertirse en un proceso continuo desde el primer git init. Como futuro profesional, aplicar estos estándares desde el inicio de un proyecto asegura que la escalabilidad técnica vaya acompañada de una gobernanza de seguridad robusta

---

## 📊 Self-Assessment

Rate your confidence level for each topic (1-5, where 5 is very confident):

| Topic | Confidence (1-5) | Notes |
|-------|------------------|-------|
| Basic Git commands | [5 ] | |
| Branching & merging | [ 5] | |
| Remote operations | [ 5] | |
| Conflict resolution | [ 4] | |
| History rewriting | [4 ] | |
| Git hooks | [4 ] | |
| Security practices | [ 5] | |

---

## 🔗 Evidence/Artifacts

**Links to branches/commits**:
- Link to your outcome branch: `https://github.com/daanilm14/taller-master-ugr/tree/group-DS01-outcomes/master-of-the-universe`


**Submission Date**: [01/05/2026]  
**Ready for Review**: ✅ Yes
