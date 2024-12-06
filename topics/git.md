# Git

## Notas

<h3>Pro Git, Second Edition - Scott Chacon & Ben Straub</h3>

<h4>Acerca de Git</h4>

<h5>Git como DVCS</h5>

Un VCS (sistema de control de versiones en inglés) es un sistema que guarda cambios realizados a un grupo de archivos, lo cual permite:
 - Ver la evolución de un proyecto a lo largo del tiempo.
 - Saber quién realizó un cambio y en qué momento.
 - Retroceder a una versión anterior en caso de emergencia.

Git, por su parte, no es cualquier tipo de VCS, sino que es un DVCS (sistema de control de versiones distribuido). Esto significa que Git no solo guarda los cambios realizados a los archivos, sino que a todo aquel que quiera trabajar con él en un proyecto le pasará una copia COMPLETA de todas las versiones del proyecto. Esto tiene varias ventajas:
 - Permite trabajar localmente sin conexión a internet.
 - Aumenta la velocidad del trabajo al no esperar a ningún servidor.
 - Recuperar el proyecto mediante una copia local en caso se pierda el servidor central.

<h5>Cómo funciona Git</h5>

A diferencia de otros DVCSs, Git no almacena "cambios" realizados a archivos, sino que a cada commit realizado almacena una copia nueva de cada archivo (excepto si el archivo es idéntico al anterior con el mismo nombre).

Git revisará cada archivo antes de cada commit, asegurándose que sea imposible cambiar un archivo sin echarle la culpa a nadie por ello. Además, por cómo está diseñado Git, toda acción se puede deshacer fácilmente.