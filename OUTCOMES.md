# Exercise Outcomes Submission Template

**Student/Group Name**: Daniel Lozano Moya - Grupo DS01 
**Level Completed**: Master  
**Date**: 03/01/2026

---

## 📋 Exercise Summary

### Exercise: Nivel Maestro
**Status**: ✅ Completed 

**What I did**:
He completado el taller en el nivel Maestro, el cuál está centrado en la reescritura del historial de Git. Este taller se ha dividido en tres fases. En primer lugar he corregido un commit sin que se generen duplicados haciendo uso de commit --amend. En segundo lugar he realizado un rebase -i para aplicar un fixup sobre un error, limpiando así el historial de commits intermedios. Por último he sincronizado la rama feature/awesome-feature con la rama master haciendo uso de rebase, logrando así un historial lineal perfecto. Finalmente, he conseguido realizar un análisis de los riesgos del uso de estas operaciones en espacios compartidos.

**Commands Used**:
```bash
# List the key Git commands you used across all parts of the exercise
git add
git commit -m ""
gitr commit --amend -m ""
git log --oneline -n 3
git rebase -i HEAD~3
git log --oneline -n 5
git checkout -b feature/awesome-feature
git rebase master
git log --graph --oneline --all -n 10
# etc.
```

**Results/Output**:

Parte 1 (Amend): El SHA cambió demostrando que se creó un nuevo objeto commit.

```
# 1. Primer commit.

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git commit -m "Add configuration file"
[master e11fc22] Add configuration file
 1 file changed, 1 insertion(+)
 create mode 100644 config.txt

# 2. Commit con --amend.

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git commit --amend -m "Add complete configuration file"
[master 0f2cb53] Add complete configuration file
 Date: Sat Jan 3 12:33:07 2026 +0100
 1 file changed, 2 insertions(+)
 create mode 100644 config.txt

# 3. Log tras el --amend.

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git log --oneline -n 3
0f2cb53 (HEAD -> master) Add complete configuration file
```

Como se observa, el identicador único del commit cambió de e11fc22 a 0f2cb53. Esto es posible gracias al comando --amend ya que no edita el objeto existente, sino que crea uno nuevo y mueve el puntero de la rama para que apunte a este nuevo commit.

Parte 2: Interactive Rebase (Limpieza de historial)
Mediante el rebase interactivo, he agrupado commits de correcciones menores para mantener un historial profesional y limpio.

```
# 1. 3 commits iniciales.

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git commit -m "Add feature A"
[master f39b1a8] Add feature A
 1 file changed, 1 insertion(+)
 create mode 100644 featureA.txt

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git commit -m "Add feature B"
[master 302f588] Add feature B
 1 file changed, 1 insertion(+)
 create mode 100644 featureB.txt

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git commit -m "Fix typo"
[master b414bc4] Fix typo
 1 file changed, 1 insertion(+)

# 2. Ejecución del rebase interactivo para aplicar 'fixup'

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/master.

# 3. Verificación del historial.

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git log --oneline -n 5
ffc9315 (HEAD -> master) Add feature B
f39b1a8 Add feature A
0f2cb53 Add complete configuration file
```

Como se puede observazr en el log final, el commit de "Fix typo" ha desaparecido de la vista principal. Al utilizar la opción fixup en el editor de rebase interactivo, Git ha fusionado los cambios del error dedntro del commit anterior. Esto permite que el historial refleje solo funcionalidades terminadas, ocultando los errores intermedios de desarrollo.


Parte 3: Rebasing a Branch (Rebase de rama)
He sincronizado la rama de funcionalidad con la rama principal evitando los commits de "merge" para obtener un historial lineal.

```
# 1. Creación de rama y commit de funcionalidad.

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git checkout -b feature/awesome-feature
Switched to a new branch 'feature/awesome-feature'

daniellozano:~/master/ds/git/taller-master-ugrfeature/awesome-feature$ git commit -m "Add awesome feature"
[feature/awesome-feature 2213b92] Add awesome feature
 1 file changed, 1 insertion(+)
 create mode 100644 awesome.txt

# 2. Avance de la rama master mientras trabajaba en la feature.

daniellozano:~/master/ds/git/taller-master-ugrfeature/awesome-feature$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git commit -m "Update on master branch"
[master dacd20a] Update on master branch
 1 file changed, 1 insertion(+)
 create mode 100644 master-update.txt

# 3. Rebase de feature sobre master.

daniellozano:~/master/ds/git/taller-master-ugrmaster$ git checkout feature/awesome-feature
Switched to branch 'feature/awesome-feature'
daniellozano:~/master/ds/git/taller-master-ugrfeature/awesome-feature$ git rebase master
Successfully rebased and updated refs/heads/feature/awesome-feature.

# 4. Visualización del grafo lineal.

daniellozano:~/master/ds/git/taller-master-ugrfeature/awesome-feature$ git log --graph --oneline --all -n 10
* f19da45 (HEAD -> feature/awesome-feature) Add awesome feature
* dacd20a (master) Update on master branch
* ffc9315 Add feature B
* f39b1a8 Add feature A
```

El resultado del comando git log --graph muestra una línea perfecta. A diferencia de un merge, que habria creado un nodo de uinión y una bifurcación en el grafo, el rebase ha tomado el commit de la rama feature y lo ha re-hubicado encima del último cambio de master.


---

## 🎯 Key Learnings

**Main concepts I learned**:
1. La mutabilidad del SHA: He comprendido que cualquier cambio en el contenido o mensaje de un commit genera un nuevo identificador único, por lo que editar puede asemejarse tambien a reemplazar.
2. El rebase permite mover commitrs ene l tiempo para que el historial sea una línea recta, facilitando la auditoría de código.
3. He aprendido la diferencia crítica entre --force y --force-with-lease, siendo esta última la única opción profesional aceptable para evitar pisar el trabajo de compañeros.

**Skills I improved**:
- Limpieza del historial.
- Rebase de ramas.

---

---

## 💭 Personal Reflection

La reescritura de la historia en Git es una técnica poderosa pero con implicaciones críticas de seguirdad y colaboración. Según lo analizado en este nivel, reescribir la historia es seguro únicamente en ramas privadas y locales que aún no han sido publicadas. En este entorno, el uso de rebase o --amend nos permite crear historiales profesionales, limpios y fáciles de leer.

Es peligroso reescribir la historia en ramas compartidas o públicas ya que con el cambio de los SHA de los commits se rompe la relación de descendencia para cualquier compañero que haya hecho pull de esos commits. Hacxiendo uso de git push --force podemos sobrescribir y borrar comits que otros compañeros hayan subido mientras estamos trabajando. Para mitigar este riesgo es importante hacer uso de git push --force-with-lease. Esto permite el envío sí el historial remoto coiuncide con nuestra última imagen local, garantizando que no borrramos accidentalmente el trabajo de nadie.

Es importante comprender la diferencia fundamental entre rebase y merge, pues el primero lineariza la historia mientras que el segundoi preserva la cronología real con un commit de unión. En un equipo de desarrollo profesional, sería interesante la implementación de un flujo de trabajo donde el rebase se utilice para limpiar las ramas de features antes de integrarlas, asegurando que el historial del proyecto principal se mantenga limpio y fácil de seguir.

---

## 📊 Self-Assessment

Rate your confidence level for each topic (1-5, where 5 is very confident):

| Topic | Confidence (1-5) | Notes |
|-------|------------------|-------|
| Basic Git commands | [5 ] | |
| Branching & merging | [5 ] | |
| Remote operations | [ 4] | |
| Conflict resolution | [ 4] | |
| History rewriting | [5 ] | |
| Git hooks | [3 ] | |
| Security practices | [ 4] | |

---

## 🔗 Evidence/Artifacts

**Links to branches/commits**:
- Link to your outcome branch: `https://github.com/daanilm14/taller-master-ugr/tree/group-DS01-outcomes/master`
- Key commits demonstrating your work:
  - 0f2cb53: Commit tras amend.
  - f19da45: Commit final tras rebase lineal.

---

---

---

**Submission Date**: [01/03/2026]  
**Ready for Review**: ✅ Yes
