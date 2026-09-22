# Lab 1 - Respuestas de comprobacion

## 1. El Working Directory es la carpeta del proyecto tal y como se ve y/o modifica en un ordenador, la Staging Area es una zona intermedia donde se preparan exactamente los cambios que se quieren incluir en el siguiente commit y el Local Repository es el historial de commits guardado dentro de la carpeta .git.

Por ejemplo, cuando cree README.md, primero existia solamente en el Working Directory y aparecia como untracked en 'git status'. Después ejecute 'git add README.md', por lo que paso a la Staging Area y aparecio en "Changes to be committed". Finalmente ejecute `git commit -m "docs: add initial project documentation"` y ese cambio paso a formar parte del Local Repository.

## 2. No, un commit solo incluye los cambios que esten preparados en la Staging Area, eso quiere decir que si modifico un archivo pero no ejecuto `git add`, el cambio permanece solamente en el Working Directory.

Esto lo comprobe en la práctica cuando cree 'docs/customer-schema.md' e intenté hacer directamente: 'git commit -m "docs: add customer schema notes"' Git respondio que no habia nada añadido al commit porque el archivo seguia siendo untracked. Despues de ejecutar `git add docs/customer-schema.md`, el commit si se pudo realizar.

## 3. Porque Git no versiona carpetas, sino archivos, es decir, si una carpeta esta 100% vacia, Git no tiene ningun archivo que registrar y por eso no aparece en 'git status'.

Para conservar esas carpetas en el repositorio usamos archivos '.gitkeep'. Asi las carpetas dejan de estar vacias y Git las incluye en el repositorio.

## 4. HEAD es el puntero que indica donde estoy trabajando actualmente dentro del historial de Git. Normalmente apunta a la branch activa y, a traves de ella, al commit actual.

## 5. Que 'git switch -c' crea una nueva linea de evolucion dentro del historial de Git y cambia HEAD a esa branch. En cambio, 'mkdir' crea una carpeta fisica real en el sistema de archivos.

Lo comprobe al crear: 'git switch -c feature/customer-search' Despues ejecute 'ls -la' y no aparecio ninguna carpeta llamada 'feature'. Mas adelante creamos 'docs/customer-search.md' unicamente en esa branch y cuando cambie a 'main', el archivo desaparecio del Working Directory, y cuando regrese a 'feature/customer-search', volvio a aparecer. Eso demuestra que una branch no es una carpeta, sino una referencia a una linea concreta del historial.

## 6. El contenido entre '<<<<<<< HEAD' y '=======' representaba la version que ya estaba en la branch actual, que en nuestro caso era 'main'. El contenido entre '=======' y '>>>>>>> fix/readme-subtitle' representaba la version que venia de la branch que intentsbamos fusionar.

## 7. Porque 'git commit --amend' reescribe el ultimo commit y el commit anterior deja de ser el actual y se crea uno nuevo con un hash diferente. He visto que si un commit ya se ha enviado a GitHub y otra persona lo ha descargado, modificarlo con '--amend' provoca que el historial local y el remoto de otras personas dejen de coincidir, por eso el laboratorio recomienda usar '--amend' solamente mientras el commit siga siendo local y todavia no se haya hecho push.

## 8. Si borro la carpeta '.git', pierdo toda la informacion interna que convierte esa carpeta en un repositorio Git: los commits, branches, referencias, historial y configuración local del repositorio.

Sin embargo, los archivos normales del proyecto que estan en el Working Directory no se borran automaticamente. Por ejemplo, 'README.md' o los archivos dentro de 'docs' seguirian fisicamente en el disco.

## 9. Git es el sistema de control de versiones que utilizo directamente en mi ordenador y con Git se pueden crear commits, branches, hacer merges, consultar el historial y trabajar incluso sin conexion a Internet.

GitHub es una plataforma que aloja repositorios Git en un servidor y permite compartirlos y trabajar con otras personas. Ademas añade herramientas de colaboracion como Pull Requests, Issues, revision de código y otras funciones.

## 10. Porque como sabemos un archivo '.env' puede contener informacion sensible como contraseñas, claves API o tokens y aunque el repositorio sea privado, una credencial puede quedar guardada en el historial de Git y seguir existiendo incluso si despues se elimina del archivo actual.

## 11. Probablemente el repositorio remoto contiene uno o más commits que la copia local todavia no tiene. Esto puede ocurrir, por ejemplo, si alguien modifico el repositorio desde otra máquina o directamente desde la interfaz de GitHub.

El primer comando que ejecutaría sería: 'git pull' para traer e integrar los cambios remotos. Después revisaria si aparece algún conflicto y, una vez resuelto y confirmado, volveria a ejecutar 'git push'.


