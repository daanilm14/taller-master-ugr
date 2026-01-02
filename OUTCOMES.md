# Exercise Outcomes Submission Template

**Student/Group Name**: Daniel Lozano Moya  
**Level Completed**: newbie 
**Date**: 02/01/2026

---

## 📋 Exercise Summary

### Exercise: [Exercise Title]
**Status**: ✅ Completed 

**What I did**:
Este archivo documenta los resultados y aprendizajes obtenidos al completar un ejercicio práctico de Git a nivel principiante en el repositorio del taller. Cada paso del ejercicio fue debidamente documentado y los cambios fueron enviados (pushed) a la rama de resultados (outcome branch) para su posterior evaluación. El objetivo es registrar evidencia del dominio de conceptos fundamentales de Git y control de versiones distribuido.

**Commands Used**:
```bash
# List the key Git commands you used across all parts of the exercise
git config --global user.name ""
git config --global user.email ""
git add hello.txt
git commit -m "Add hello.txt with my name"
git checkout -b feature/my-info
git add my-info.txt
git status
git log
git log --oneline --graph --all
# etc.
```

**Results/Output**:
```
# Paste relevant command outputs, git log, or status messages
# Example:
daniellozano:~/master/ds/git/taller-master-ugrgroup-X-outcomes/newbie$ git log --oneline --graph --all
* 5c8671a (origin/feature/my-info, feature/my-info) Add personal information
* 00916e7 (HEAD -> group-X-outcomes/newbie, newbie) Add hello.txt with my name
* 360f4a4 (origin/newbie) refactor: consolidate newbie exercises into single comprehensive exercise
* 5eedc97 docs: Add submission instructions to newbie level
* 45e1c31 Update README for newbie level exercises
| * 9602351 (origin/main, origin/HEAD, main) Adding GenAI guidelines
| * 7ad3af4 docs: update main branch files to reflect consolidated exercise structure (1 per level)
| * 4d9131e chore: remove instructor files from repository tracking
| *   adbb307 Merge pull request #9 from miguel-oltra/patch-gitignore-update
| |\
| | * e4709e6 Updated CODEOWNERS file
| | * 2a39a02 chore: add INSTRUCTOR_GUIDE.md to gitignore
| | * 0abdbae chore: add SUMMARY.md to gitignore for instructor files
| |/
| * 88a54ab chore: Add .gitignore to exclude instructor files and sensitive data
| * e39ff08 PROMPT for updated
| * df1cfdd fix: Update CODEOWNERS to allow trainee work while protecting exercise branches
| * a011fad config: Add CODEOWNERS file for code review requirements
| * 769be64 docs: Add complete implementation summary
| * 9d008fa Updated README.MD with guidelines for the exercises
| * f66bf22 docs: Update MODEL_SPEC.MD with PROMPT 2 requirements
| * c24fd57 docs: Add outcome submission process and evaluation criteria
| * ec488d0 Update main README with complete training overview and navigation
|/
| * b0fb9dc (origin/master-of-the-universe) refactor: consolidate master-of-the-universe exercises into single comprehensive exercise
| * d1ef79f docs: Add submission instructions to master-of-the-universe level
| * 5bffa64 Update README for master-of-the-universe level exercises
|/
```

**Screenshots** (if applicable):
- [Screenshot 1: Description]
- [Screenshot 2: Description]

---

## 🎯 Key Learnings

**Main concepts I learned**:
1. He comprendido el flujo de trabajo entre el Directorio de Trabajo (archivos locales), el Área de Preparación o Staging Area (el índice) y el Directorio GIT (historial permanente).
2. Entendí que una rama no es una carpeta con copias de archivos, sino un puntero móvil a un commit específico, lo que permite que el cambio de contexto sea instantáneo.

**Skills I improved**:
- Visualización del historial: Uso de git log --graph --oneline para entender el árbol del proyecto.
- Gestión de remotos: Configuración y alternancia entre múltiples remotos.
- Autenticación segura: Generación y configuración de claves SSH para conectar con GitHub sin usar contraseñas.

---

## 🚧 Challenges Faced

### Challenge 1: [Brief title]
**Problem**: Al intentar hacer push de mi rama directamente al repositorio del profesor (miguel-oltra), recibí un error de permiso denegado porque no tengo acceso de escritura en su cuenta.

**Solution**: Implementé el flujo de trabajo de "Forking". Creé un fork en mi propia cuenta de GitHub y actualicé la URL de mi remoto origin para que apuntara a mi copia personal.

**Commands/Approach**:
```bash
git remote set-url origin git@github.com:daanilm14/taller-master-ugr.git
git push origin feature/my-info
```

---

### Challenge 2: [Brief title]
**Problem**: El comando git pull origin newbie fallaba con el mensaje couldn't find remote ref. Esto ocurrió porque mi fork solo copió la rama main por defecto.

**Solution**: Aprendí a configurar un segundo remoto llamado upstream que apunta al repositorio original del profesor para poder descargar las ramas de los ejercicios que me faltaban.

**Commands/Approach**:
```bash
git remote add upstream git@github.com:miguel-oltra/taller-master-ugr.git
git fetch upstream
git pull upstream newbie
```

## 💭 Personal Reflection

**What surprised me**:
Me sorprendió lo eficiente que es Git. Antes pensaba que crear una rama duplicaba todos los archivos del proyecto, pero tras este taller entendí que Git solo mueve punteros, lo que ahorra muchísimo espacio y tiempo.

**What I found most difficult**:
Lo más desafiante fue entender la jerarquía de remotos. Al principio es confuso distinguir entre tu copia local, tu copia en la nube (origin) y la fuente original (upstream)

**What I found most useful**:
El comando git status.

**How I would apply this in real projects**:
Utilizaría siempre ramas de "feature" para cada funcionalidad nueva. Esto permite que la rama principal siempre esté limpia y lista para producción, mientras yo experimento de forma segura en una rama separada.

---

## 📊 Self-Assessment

Rate your confidence level for each topic (1-5, where 5 is very confident):

| Topic | Confidence (1-5) | Notes |
|-------|------------------|-------|
| Basic Git commands | [ 5] | |
| Branching & merging | [ 4] | |
| Remote operations | [4 ] | |
| Conflict resolution | [2 ] | |
| History rewriting | [ 1] | |
| Git hooks | [ 1] | |
| Security practices | [4 ] | |

---

## 🔗 Evidence/Artifacts

**Links to branches/commits**:
- Link to your outcome branch: `https://github.com/daanilm14/taller-master-ugr/tree/group-X-outcomes/newbie`
- Key commits demonstrating your work:
  - Add hello.txt with my name: Demuestra el flujo básico en local.
  - Add personal information: Demuestra el trabajo en una rama de característica (feature).
  - docs: Entrega oficial nivel newbie: El commit que incluye este informe.

**Additional files created** (if any):
- hello.txt: Archivo de prueba para comandos básicos.
- my-info.txt: Archivo creado en una rama separada para practicar el flujo remoto.

---

## ✅ Completion Checklist

Before submitting, ensure you have:
- [ ✅] Completed the exercise for your chosen level (including all parts)
- [ ✅] Documented all commands used with their outputs
- [ ✅] Described challenges and how you resolved them
- [ ✅] Provided a thoughtful reflection on your learning
- [ ✅] Self-assessed your confidence in each topic
- [✅ ] Pushed your outcome branch to the remote repository
- [ ✅] Created a Pull Request (if required by your instructor)

---


---

**Submission Date**: [02/01/2025]  
**Ready for Review**: ✅ Yes
