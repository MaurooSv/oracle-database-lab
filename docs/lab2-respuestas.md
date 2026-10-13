Laboratorio 2 - Preguntas de comprobacion



1\.  ¿Por qué un Issue sin criterios de aceptación es un problema, aunque la descripción general parezca clara?



Porque no permite comprobar de forma objetiva si la tarea esta terminada. Aunque la descripcion sea clara, pueden existir diferentes interpretaciones sobre lo que se debe entregar.



En nuestro Issue #1 establecimos cuatro criterios: crear CONTRIBUTING.md, explicar las convenciones de ramas, documentar Conventional Commits y enlazar el archivo desde README.md.



2\. Explica la diferencia entre "Refs #N" y "Closes #N" en un mensaje de commit o en la

descripción de un Pull Request.



`Refs #N` relaciona un commit con un Issue, pero no lo cierra.



`Closes #N` indica que el cambio resuelve el Issue y permite cerrarlo automaticamente cuando el Pull Request se fusiona en la rama principal.



En nuestro laboratorio utilizamos `Refs #1` en el commit inicial y `Closes #1` en la descripcion del Pull Request #2.



3\. ¿Qué ocurre exactamente si intentas hacer git push directamente sobre una branch main

protegida? ¿Es un error tuyo o un fallo del sistema?



Si la regla de proteccion se aplica correctamente y exige Pull Request, GitHub rechaza el push directo.



No es un fallo de Git, sino el comportamiento esperado de una regla que impide modificar main sin pasar por el proceso de revision.



4\. Un compañero te dice: "he aprobado el PR sin mirar los archivos, total ya me fío". ¿Qué riesgo tiene esa forma de revisar?



Se pueden integrar errores, cambios accidentales, vulnerabilidades o modificaciones que no cumplen los criterios de aceptacion.



Un reviewer debe comprobar el diff, el objetivo del Issue, la documentacion y las pruebas antes de aprobar.



Confiar en el compañero no sustituye una revision tecnica.



5\. Si el reviewer pide un cambio y tú ya habías hecho push de tu branch, ¿tienes que abrir un Pull Request nuevo? Explica qué ocurre técnicamente con el PR existente cuando haces un nuevo commit.



No, solo se modifica la misma rama de trabajo, se realiza otro commit y se ejecuta `git push`.



GitHub actualiza automaticamente el Pull Request existente con los nuevos commits.



\## 6. Describe con tus palabras la diferencia entre Merge commit, Squash and merge y Rebase and merge. ¿Cuál usarías para una branch con commits "wip", "fix", "fix2", "ok ya"?



\*\*Merge commit:\*\* integra la rama conservando sus commits originales y crea un commit de fusion.



\*\*Squash and merge:\*\* combina todos los commits de la rama en un unico commit antes de integrarlos.



\*\*Rebase and merge:\*\* incorpora los commits individualmente sobre la rama de destino, generando un historial lineal.



Si una rama contiene commits poco descriptivos como `wip`, `fix`, `fix2` y `ok ya`, utilizaria Squash and merge para integrarlos como un unico commit con un mensaje claro.



7\. ¿Por qué borrar una branch después del merge no elimina el trabajo realizado en ella?



Porque los cambios ya se han incorporado al historial de la rama principal y eliminar la branch elimina la referencia a esa linea de trabajo, pero no los commits integrados.



8\. ¿Qué información debería contener siempre la descripción de un Pull Request, como mínimo?



Como minimo debe explicar:



\- \*\*Summary:\*\* que hace el cambio.

\- \*\*Changes:\*\* que archivos o funcionalidades se modificaron.

\- \*\*Testing:\*\* como se verifico el resultado.

\- \*\*Related Issue:\*\* que Issue resuelve.



9\. Un reviewer escribe solo "esto está mal" como comentario. ¿Qué le falta a ese comentario para ser útil? Reescríbelo tú con un ejemplo inventado.


Porque no identifica el problema ni explica como solucionarlo, un comentario de revision debe indicar que se ha observado, por que importa y que cambio se propone.



Ejemplo:



`issue (blocking): La migracion elimina una columna sin comprobar si contiene datos. Propongo validar su contenido antes de ejecutar el cambio para evitar perdida de informacion.`



10\. ¿Qué diferencia hay entre que main esté protegida y que simplemente el equipo "se ponga de acuerdo" en no hacer push directo?



Un acuerdo depende de que todos los colaboradores recuerden y respeten una norma, una regla de proteccion efectiva hace que GitHub impida automaticamente las operaciones que incumplen las condiciones configuradas, por tanto, proteger main convierte una recomendacion del equipo en una restriccion tecnica verificable.



13\. ¿Por qué abrir un Draft PR desde el primer commit estructural puede ahorrar tiempo al

equipo, aunque parezca más lento para el autor individual?


Porque permite compartir el trabajo antes de que este terminado y recibir comentarios tempranos sin indicar que ya esta listo para fusionarse, esto ayuda a detectar errores de enfoque, problemas de arquitectura o requisitos mal interpretados antes de invertir muchas horas, aunque requiere documentar el trabajo desde el inicio, reduce las correcciones grandes al final del desarrollo.



