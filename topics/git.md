# Git

## Contenido

 - [Pro Git, Second Edition - Scott Chacon & Ben Straub](#1)
   - [Acerca de Git](#1.1)
     - [Git como DVCS](#1.1.1)
     - [Cómo funciona Git](#1.1.2)
   - [Tu identidad en Git](#1.2)
     - [Archivos de configuración](#1.2.1)
     - [Cambiar configuración](#1.2.2)
     - [Revisar configuración](#1.2.3)
   - [Manejando repositorios](#1.3)
     - [Inicializar un repositorio](#1.3.1)
     - [Clonar un repositorio](#1.3.2)
   - [Manejando archivos y cambios](#1.4)
     - [Conceptos clave](#1.4.1)
     - [Añadir un archivo (staging)](#1.4.2)
     - [Quitando archivos (unstaging)](#1.4.3)

## Notas

<h3 id="1">Pro Git, Second Edition - Scott Chacon & Ben Straub</h3>

<h4 id="1.1">Acerca de Git</h4>

<h5 id="1.1.1">Git como DVCS</h5>

Un VCS (sistema de control de versiones en inglés) es un sistema que guarda cambios realizados a un grupo de archivos, lo cual permite:
 - Ver la evolución de un proyecto a lo largo del tiempo.
 - Saber quién realizó un cambio y en qué momento.
 - Retroceder a una versión anterior en caso de emergencia.

Git, por su parte, no es cualquier tipo de VCS, sino que es un DVCS (sistema de control de versiones distribuido). Esto significa que Git no solo guarda los cambios realizados a los archivos, sino que a todo aquel que quiera trabajar con él en un proyecto le pasará una copia COMPLETA de todas las versiones del proyecto. Esto tiene varias ventajas:
 - Permite trabajar localmente sin conexión a internet.
 - Aumenta la velocidad del trabajo al no esperar a ningún servidor.
 - Recuperar el proyecto mediante una copia local en caso se pierda el servidor central.

<h5 id="1.1.2">Cómo funciona Git</h5>

A diferencia de otros DVCSs, Git no almacena "cambios" realizados a archivos, sino que a cada commit realizado almacena una copia nueva de cada archivo (excepto si el archivo es idéntico al anterior con el mismo nombre).

Git revisará cada archivo antes de cada commit, asegurándose que sea imposible cambiar un archivo sin echarle la culpa a nadie por ello. Además, por cómo está diseñado Git, toda acción se puede deshacer fácilmente.

<h4 id="1.2">Tu identidad en Git</h4>

<h5 id="1.2.1">Archivos de configuración</h5>

Git almacena tres archivos de configuración que identifican a un usuario al momento de hacer commits. Entre ellos están:
 - /etc/gitconfig: son globales para TODO el sistema operativo, mediante la bandera --system.
 - ~/.gitconfig: es específico para un usuario del sistema operativo, mediante la bandera --global.
 - config: es específico para un proyecto y no requiere usar banderas.

<h5 id="1.2.2">Cambiar configuración</h5>

La configuración se puede cambiar mediante el comando git config con la bandera del scope deseado. A continuación se muestra un ejemplo de cambiar la configuración a scope global:

```
    git config --global user.name "John Doe"
    git config --global user.email "johndoe@example.com"
```

<h5 id="1.2.3">Revisar configuración</h5>

Cuando hacemos commits, se toma la configuración del scope más específico disponible, lo que podría causar conflictos inesperados. Por ello, es imporatnte revisar la configuración para saber qué debemos corregir. A continuación se muestra un ejemplo de revisar la configuración a scope global:

```
    git config --global user.name
    git config --global user.email
```

<h4 id="1.3">Manejando repositorios</h4>

<h5 id="1.3.1">Inicializar un repositorio</h5>

Usando la CLI que más prefieras, puedes navegar por las carpetas y crear un repositorio desde cero (o convertir una carpeta ya con archivos en un repositorio).

```
    git init
```

<h5 id="1.3.2">Clonar un repositorio</h5>

Navegando por las carpetas usando la CLI puedes clonar un repositorio (.git) en la dirección actual.

```
    git clone https://github.com/L1LZ4Z/cuaderno-de-notas.git
```

Este comando creará una nueva carpeta con el nombre del repositorio en la dirección elegida. Sin embargo, el nombre puede ser personalizado agregandolo después del repositorio.

```
    git clone https://github.com/L1LZ4Z/cuaderno-de-notas.git NombrePersonalizado
```

<h4 id="1.4">Manejando archivos y cambios</h4>

<h5 id="1.4.1">Conceptos clave</h5>

Esta puede ser la parte más densa de aprender. Por ello, en mis notas puntualizaré lo más posible para evitar extenderme mucho.

Existen una serie de conceptos sobre como se manejan los archivos y los cambios que se les realizan. Trataré de explicarlos. La nomenclatura entre paréntesis será útil más adelante.
 - Modified (M): Un archivo se considera modified si su contenido ha cambiado en al menos un caracter.
   - Un archivo podría haber sido modificado, pero los cambios no se guardaron.
   - Se debe considerar que dependiendo del IDE los cambios se guardan o no de forma automática.
 - Staged (A): Un archivo se considera staged si tras haberse encontrado en modified, se decide añadirlo para un *commit*.
   - Un *commit* es una confirmación de los cambios realizados a nivel local para ser enviados al repositorio externo.
 - Staged, then modified (MM): Un archivo se considera staged, then modified si tras haber estado en staged, se le realizan otros cambios pero estos últimos no se añaden al *commit*.
   - Es importante tener cuidado con esto porque podríamos terminar enviando una versión antigua de un archivo y causar errores.

<h5 id="1.4.2">Añadir un archivo (staging)</h5>

Es posible añadir todos los archivos con un solo comando.

```
    git add .
```

Sin embargo, esto puede conducir a resultados no deseados. Por ejemplo, incluir las bibliotecas o dependencias del proyecto en el repositorio. Esto no es práctico, porque normalmente se usa un gestor de paquetes para descargarlos localmente.

Para evitar problemas, se recomienda hacer staging de los archivos que nosotros queremos incluir, uno por uno. Para ello se puede usar:

```
    git add nombrearchivo.extension
```

Se debe tomar en cuenta que se usa la ruta absoluta desde el punto de vista de la carpeta principal del proyecto. 

Supongamos que dentro de tu repositorio tienes una carpeta app y en ella una carpeta utils y en ella se encuentra tu archivo modificado constants.js

```
    Repositorio/
    └── app/
        └── utils/
            └── constants.js
```

Entonces el comando a utilizar para añadir dicho archivo sería:

```
    git add app/utils/constants.js
```

<h5 id="1.4.3">Quitando archivos (unstaging)</h5>

Es posible retirar todos los archivos de stage con un solo comando.

```
    git restore --staged .
```

Similar al staging, también es posible hacer unstage de un archivo específico. Para ello puedes usar:

```
    git restore --staged nombrearchivo.extension
```

Se aplican las mismas reglas para el enrutamiento del archivo. 

Supongamos que dentro de tu repositorio tienes una carpeta app y en ella una carpeta utils y en ella se encuentra tu archivo modificado constants.js

```
    Repositorio/
    └── app/
        └── utils/
            └── constants.js
```

Para quitar dicho archivo del staging puedes usar

```
    git restore --staged app/utils/constants.js
```