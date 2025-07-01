# Proyecto de Práctica - Control de Versiones

**Integrantes del equipo:**
- Osvaldo Soto Coronel
- Erick Jost
- Juan Diego Martinez Cruz
- Carlos Uriel Alcantar González

**Descripción del proyecto:**
Este proyecto es una simulación de flujo de trabajo colaborativo en Git y GitHub, aplicando ramas, commits, pull requests, resolución de conflictos y manejo de archivos ignorados.

**Descripcion 2**

Flujo de Trabajo Simplificado con Git y GitHub
Un flujo de trabajo en Git es la estrategia que tu equipo usará para organizar, colaborar y gestionar los cambios en su código, asegurando estabilidad y eficiencia.
1. La Rama Principal: main
La rama main (o master) es el corazón de tu proyecto. Siempre debe estar estable y lista para producción. Nadie debe trabajar directamente en main. Todos los cambios se integran aquí después de una revisión.
 * Tu acción: Antes de empezar cualquier tarea, siempre ve a main y actualízala:
   git checkout main
git pull origin main

2. Ramas de Funcionalidad Personalizadas
Cada nueva característica, mejora o corrección se desarrolla en una rama separada. Esto aísla tu trabajo y evita conflictos tempranos con el de tus compañeros.
 * Tu acción: Crea y cambia a tu rama personal (ej. ramas/osvaldo).
   git checkout -b ramas/osvaldo

 * Trabajo y Commits: Realiza tus cambios, añade nuevos archivos (como aportacion-OSVALDO.txt), y haz múltiples git commit a medida que avanzas.
 * Subir tu rama: Una vez que estés listo, sube tu rama a GitHub:
   git push origin ramas/osvaldo

   (Si es la primera vez, usa --set-upstream: git push --set-upstream origin ramas/osvaldo).
3. Solicitudes de Fusión (Pull Requests - PRs)
Un Pull Request (PR) es tu propuesta para integrar el código de tu rama personal en la rama main. Es el punto clave para la revisión de código y la colaboración.
 * Tu acción:
   * Después de subir tu rama, ve a GitHub en tu navegador.
   * Haz clic en "New pull request" o en el aviso que te muestra GitHub para tu rama recién subida.
   * Asegúrate de que la rama base sea main y tu rama sea la de comparación (ej. ramas/osvaldo).
   * Dale un título y descripción claros a tu PR.
   * Crea el PR.
 * Acción del Revisor (Diego, Erick, Carlos):
   * Un compañero revisa tu PR en GitHub (pestaña "Files changed").
   * Si todo está bien, aprueba el PR.
   * Después de la aprobación, quien tenga permisos (o el mismo revisor) hará clic en "Merge pull request" para fusionar los cambios en main.
4. Resolución de Conflictos
Los conflictos surgen cuando dos personas modifican las mismas líneas en el mismo archivo. Git no sabe cuál mantener y te pedirá que decidas.
 * Escenario: Si Diego modifica una línea en README.md y la sube a main, y luego Carlos modifica la misma línea en su rama y crea un PR, el PR de Carlos mostrará un conflicto.
 * Tu acción (Carlos, para resolver su conflicto):
   * Actualiza tu rama local main: git checkout main y git pull origin main.
   * Regresa a tu rama personal: git checkout ramas/carlos.
   * Integra los cambios de main en tu rama: git merge main (o git rebase main).
   * Edita manualmente el archivo conflictivo (README.md en este caso) para decidir qué versión de la línea quieres conservar, eliminando los marcadores de conflicto (<<<<<<<, =======, >>>>>>>).
   * Marca el archivo como resuelto: git add README.md.
   * Completa la fusión/rebase: git commit (o git rebase --continue).
   * Vuelve a subir tu rama con los conflictos resueltos: git push origin ramas/carlos.
     <!-- end list -->
   * Una vez resuelto localmente y subido, el PR en GitHub se actualizará y podrá ser fusionado.
5. gitignore: Mantén tu Repositorio Limpio
El archivo .gitignore indica a Git qué archivos y carpetas debe ignorar y no incluir en el repositorio. Es crucial para evitar subir archivos temporales, logs o configuraciones locales.
 * Tu acción (Osvaldo):
   * Crea un archivo .gitignore en la raíz de tu repositorio:
     nano .gitignore

   * Dentro de .gitignore, añade las reglas:
     *.log
temp/

   * Guarda el archivo.
   * Crea archivos de prueba (ej. error-OSVALDO.log, temp/temporal.txt).
   * Verifica con git status que Git los ignore.
   * Añade y sube solo el .gitignore a tu rama (git add .gitignore, git commit, git push).
     <!-- end list -->
   * Después, tu PR para esta rama fusionará el .gitignore a main, y esas reglas se aplicarán para todos.
Este proceso, aunque requiere un poco de práctica, asegura un desarrollo colaborativo organizado y robusto.

.....
