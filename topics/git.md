# Git

## Notas

<h3>Pro Git, Second Edition - Scott Chacon & Ben Straub</h3>

<h4>Empezando</h4>

<h5>Git como DVCS</h5>

Un VCS (sistema de control de versiones en inglés) es un sistema que guarda cambios realizados a un grupo de archivos, lo cual permite:
 - Ver la evolución de un proyecto a lo largo del tiempo.
 - Saber quién realizó un cambio y en qué momento.
 - Retroceder a una versión anterior en caso de emergencia.

Git, por su parte, no es cualquier tipo de VCS, sino que es un DVCS (sistema de control de versiones distribuido). Esto significa que Git no solo guarda los cambios realizados a los archivos, sino que a todo aquel que quiera trabajar con él en un proyecto le pasará una copia COMPLETA de todas las versiones del proyecto. Esto tiene varias ventajas:
 - Permite trabajar localmente sin conexión a internet.
 - Aumenta la velocidad del trabajo al no esperar a ningún servidor.
 - Recuperar el proyecto mediante una copia local en caso se pierda el servidor central.