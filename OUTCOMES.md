
# Exercise Outcomes Submission Template

**Student/Group Name**: Daniel Lozano Moya - Grupo DS-01  
**Level Completed**: Intermediate  
**Date**: 02/01/2026

---

## 📋 Exercise Summary

### Exercise: Intermediario
**Status**: ✅ 

**What I did**:
He completado con éxito el nivel intermedio del taller. Las tareas principales incluyeron la creación de dos ramas de características paralelas (`feature/header` y `feature/footer`) que modificaban el mismo archivo (`page.html`). Esto me permitió experimentar y resolver un **conflicto de fusión** manual. Posteriormente, implementé un sistema de versionado mediante el uso de **etiquetas (tags)**, diferenciando entre 2 tipos de etiquetas.

**Commands Used**:
```bash
# List the key Git commands you used across all parts of the exercise
git checkout intermediate
git checkout -b feature/header
git checkout intermediate
git checkout -b feature/footer
git checkout feature/header
git add page.html
git commit -m "Add header to page"
git checkout feature/footer
git add page.html
git commit -m "Add footer to page"
git checkout intermediate
git merge feature/header
git merge feature/footer
git add page.html
git commit -m "Merge footer with resolved conflicts"
git tag -a v1.0 -m "First stable version with merged features"
git tag
git show v1.0
git push origin v1.0
git tag v1.0-test
git show v1.0
git show v1.0-test
git checkout intermediate
git checkout -b group-DS01-outcomes/intermediate
git checkout main -- OUTCOME_TEMPLATE.md
# etc.
```

**Results/Output**:
```
daniellozano:~/master/ds/git/taller-master-ugrgroup-DS01-outcomes/intermediate$ git log --oneline --graph --all
*   37a7af6 (HEAD -> group-DS01-outcomes/intermediate, tag: v1.0-test, tag: v1.0, intermediate) Merge footer with resolved conflicts
|\
| * 096a6e1 (feature/footer) Add footer to page
* | f89e6af (feature/header) Add header to page
|/
* 994450b (origin/intermediate) refactor: consolidate intermediate exercises into single comprehensive exercise
* a1c17e7 docs: Add submission instructions to intermediate level
* 9f25f7a Update README for intermediate level exercises
| * 9eb1e69 (origin/group-X-outcomes/newbie, group-X-outcomes/newbie) docs: Add newbie level exercise outcomes for Group X
| | * 5c8671a (origin/feature/my-info, feature/my-info) Add personal information
| |/
| * 00916e7 (newbie) Add hello.txt with my name
| * 360f4a4 (origin/newbie) refactor: consolidate newbie exercises into single comprehensive exercise
| * 5eedc97 docs: Add submission instructions to newbie level
| * 45e1c31 Update README for newbie level exercises
|/
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
```

```
daniellozano:~/master/ds/git/taller-master-ugrintermediate$ git merge feature/footer
Auto-merging page.html
CONFLICT (add/add): Merge conflict in page.html
Automatic merge failed; fix conflicts and then commit the result.
```

```
daniellozano:~/master/ds/git/taller-master-ugrintermediate$ git show v1.0
tag v1.0
Tagger: Daniel Lozano Moya <daniellozanomoya@gmail.com>
Date:   Fri Jan 2 15:17:26 2026 +0100

First stable version with merged features

commit 37a7af6bfe0ad61cc3d26a76899697e8e9a673d0 (HEAD -> intermediate, tag: v1.0-test, tag: v1.0)
Merge: f89e6af 096a6e1
Author: Daniel Lozano Moya <daniellozanomoya@gmail.com>
Date:   Fri Jan 2 15:14:44 2026 +0100

    Merge footer with resolved conflicts

diff --cc page.html
index a8613bc,acd4ecc..0262ec3
--- a/page.html
+++ b/page.html
@@@ -1,1 -1,1 +1,5 @@@
- <h1>CABECERA</h1>
 -<footer>PIE PAGINA</footer>
++
++<h1>CABECERA</h1>
++
++<footer>PIE PAGINA</footer>
++
```

```
daniellozano:~/master/ds/git/taller-master-ugrintermediate$ git show v1.0-test
commit 37a7af6bfe0ad61cc3d26a76899697e8e9a673d0 (HEAD -> intermediate, tag: v1.0-test, tag: v1.0)
Merge: f89e6af 096a6e1
Author: Daniel Lozano Moya <daniellozanomoya@gmail.com>
Date:   Fri Jan 2 15:14:44 2026 +0100

    Merge footer with resolved conflicts

diff --cc page.html
index a8613bc,acd4ecc..0262ec3
--- a/page.html
+++ b/page.html
@@@ -1,1 -1,1 +1,5 @@@
- <h1>CABECERA</h1>
 -<footer>PIE PAGINA</footer>
++
++<h1>CABECERA</h1>
++
++<footer>PIE PAGINA</footer>
++
```

---

## 🎯 Key Learnings

**Main concepts I learned**:
1. He aprendido a interpretar los marcadores de conflicto (<<<<<<<, =======, >>>>>>>) y a entender que el conflicto ocurre cuando Git no puede decidir automáticamente qué cambio mantener en la misma línea de código.
2. He comprendido el concepto de fusión de ramas y cómo Git combina historias divergentes de diferentes ramas.
3. He comprendido que las etiquetas anotadas son objetos completos en la base de datos de Git (útiles para versiones oficiales), mientras que las ligeras son simples alias a un commit (útiles para marcas temporales).

**Skills I improved**:
- Resolución manual de colisiones: Edición limpia de código en conflicto.
- Versionado con significado: Uso de etiquetas para identificar aspectos como releases.
- Auditoría de historial: Uso de git show para inspeccionar metadatos de etiquetas y detalles de fusiones.

---

## 🚧 Challenges Faced

### Challenge 1: El Conflicto de Merge.
**Problem**:  Al intentar fusionar la rama del pie de página, Git no supo cómo combinar las líneas en page.html porque ambas ramas empezaban en la línea 1.

**Solution**: Utilicé un editor de texto para limpiar el archivo, eliminando los marcadores de Git y organizando el HTML de forma lógica para que aparecieran tanto la cabecera como el pie de página.

**Commands/Approach**:
```bash
# Tras el error de merge:
git add page.html
git commit # Esto cerró el proceso de merge satisfactoriamente
```

---

## 💭 Personal Reflection

**What surprised me**:
Me sorprendió que Git es capaz de realizar fusiones automáticas la mayor parte del tiempo, y solo pide ayuda cuando los cambios se solapan exactamente en las mismas líneas.

**What I found most difficult**:
Al principio, los marcadores de conflicto (<<<<<<<, =======) resultan intimidantes, pero una vez entiendes que solo delimitan las dos opciones de código, la resolución se vuelve un proceso mecánico y seguro.

**What I found most useful**:
El uso de etiquetas anotadas. En un proyecto real, poder ver quién marcó una versión con un estado y una fecha concreta, aporta una trazabilidad esencial para el equipo de desarrollo.

**How I would apply this in real projects**:
Usaría ramas separadas para cada componente (como en este ejercicio) para trabajar sin interferir en el código estable, y etiquetaría cada hito importante (v1.0, v2.0) para poder volver a cualquier versión anterior del producto de forma instantánea.

---

## 📊 Self-Assessment

Rate your confidence level for each topic (1-5, where 5 is very confident):

| Topic | Confidence (1-5) | Notes |
|-------|------------------|-------|
| Basic Git commands | [5 ] |Proceso de add/commit totalmente asimilado. |
| Branching & merging | [ 5] |Gestión de ramas paralela comprendida. |
| Remote operations | [4 ] |Entendido el push selectivo de ramas y tags. |
| Conflict resolution | [4 ] |Capaz de resolver conflictos manuales sin miedo. |
| History rewriting | [2 ] |Concepto teórico conocido, falta práctica. |

---

## 🔗 Evidence/Artifacts

**Links to branches/commits**:
- Link to your outcome branch: `https://github.com/daanilm14/taller-master-ugr/tree/group-DS01-outcomes/intermediate`
- Key commits demonstrating your work:
  - Etiqueta anotada v1.0: Disponible en el repositorio remoto.

**Additional files created** (if any):
- page.html: Documento integrado con header y footer tras el conflicto.

---

## ✅ Completion Checklist

Before submitting, ensure you have:
- [ ] Completed the exercise for your chosen level (including all parts)
- [ ] Documented all commands used with their outputs
- [ ] Described challenges and how you resolved them
- [ ] Provided a thoughtful reflection on your learning
- [ ] Self-assessed your confidence in each topic
- [ ] Pushed your outcome branch to the remote repository
- [ ] Created a Pull Request (if required by your instructor)

---


---

**Submission Date**: [02/01/2026]  
**Ready for Review**: ✅ Yes
