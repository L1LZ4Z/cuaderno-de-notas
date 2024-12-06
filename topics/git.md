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

<h4>Tu identidad en Git</h4>

<h5>Archivos de configuración</h5>

Git almacena tres archivos de configuración que identifican a un usuario al momento de hacer commits. Entre ellos están:
 - /etc/gitconfig: son globales para TODO el sistema operativo, mediante la bandera --system.
 - ~/.gitconfig: es específico para un usuario del sistema operativo, mediante la bandera --global.
 - config: es específico para un proyecto y no requiere usar banderas.

 <h5>Cambiar configuración</h5>

 La configuración se puede cambiar mediante el comando git config con la bandera del scope deseado. A continuación se muestra un ejemplo de cambiar la configuración a scope global:

```
    git config --global user.name "John Doe"
    git config --global user.email "johndoe@example.com"
```

<h5>Revisar configuración</h5>

Cuando hacemos commits, se toma la configuración del scope más específico disponible, lo que podría causar conflictos inesperados. Por ello, es imporatnte revisar la configuración para saber qué debemos corregir. A continuación se muestra un ejemplo de revisar la configuración a scope global:

```
    git config --global user.name
    git config --global user.email
```