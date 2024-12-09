# Git

## Contenido

- [Pro Git, Second Edition - Scott Chacon & Ben Straub](#pro-git-second-edition---scott-chacon--ben-straub)
  - [Acerca de Git](#acerca-de-git)
    - [Git como DVCS](#git-como-dvcs)
    - [Cómo funciona Git](#cómo-funciona-git)
  - [Tu identidad en Git](#tu-identidad-en-git)
    - [Archivos de configuración](#archivos-de-configuración)
    - [Cambiar configuración](#cambiar-configuración)
    - [Revisar configuración](#revisar-configuración)
  - [Manejando repositorios](#manejando-repositorios)
    - [Inicializar un repositorio](#inicializar-un-repositorio)
    - [Clonar un repositorio](#clonar-un-repositorio)
  - [Manejando archivos y cambios](#manejando-archivos-y-cambios)
    - [Conceptos clave](#conceptos-clave)
    - [Añadir un archivo (staging)](#añadir-un-archivo-staging)
    - [Quitando archivos (unstaging)](#quitando-archivos-unstaging)

---

## Pro Git, Second Edition - Scott Chacon & Ben Straub

### Acerca de Git

#### Git como DVCS

Un VCS (sistema de control de versiones) guarda los cambios realizados en un grupo de archivos, lo cual permite:

- Ver la evolución de un proyecto a lo largo del tiempo.
- Saber quién realizó un cambio y en qué momento.
- Retroceder a una versión anterior en caso de emergencia.

Git es un DVCS (sistema de control de versiones distribuido). Esto significa que cada persona tiene una copia completa de todas las versiones del proyecto, lo cual ofrece:

- Trabajo sin conexión a internet.
- Mayor velocidad al no depender de un servidor.
- Recuperación del proyecto mediante una copia local si se pierde el servidor central.

#### Cómo funciona Git

A diferencia de otros DVCS, Git no almacena "cambios", sino que cada commit guarda una copia nueva de los archivos (salvo si son idénticos al anterior). Además, permite deshacer acciones fácilmente.

### Tu identidad en Git

#### Archivos de configuración

Git utiliza tres archivos de configuración:

- `/etc/gitconfig`: configuración global para todo el sistema operativo (`--system`).
- `~/.gitconfig`: configuración específica para un usuario (`--global`).
- `config`: configuración específica de un proyecto.

#### Cambiar configuración

Usa `git config` para modificar la configuración, especificando el scope:

```bash
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
```

#### Revisar configuración

Verifica la configuración activa para evitar conflictos:

```bash
git config --global user.name
git config --global user.email
```

### Manejando repositorios

#### Inicializar un repositorio

Crea un repositorio desde cero:

```bash
git init
```

#### Clonar un repositorio

Copia un repositorio existente:

```bash
git clone https://github.com/L1LZ4Z/cuaderno-de-notas.git
```

Puedes personalizar el nombre de la carpeta:

```bash
git clone https://github.com/L1LZ4Z/cuaderno-de-notas.git NombrePersonalizado
```

### Manejando archivos y cambios

#### Conceptos clave

- **Modified (M):** un archivo cambiado pero no guardado.
  - Un archivo podría haber sido modificado, pero los cambios no se guardaron.
   - Se debe considerar que dependiendo del IDE los cambios se guardan o no de forma automática.
- **Staged (A):** un archivo añadido para commit.
  - Un *commit* es una confirmación de los cambios realizados a nivel local para ser enviados al repositorio externo.
- **Staged, then modified (MM):** cambios adicionales realizados tras el staging que aún no fueron añadidos.
  - Es importante tener cuidado con esto porque podríamos terminar enviando una versión antigua de un archivo y causar errores.

#### Añadir un archivo (staging)

Añade todos los archivos:

```bash
git add .
```

O especifica un archivo:

```bash
git add app/utils/constants.js
```

#### Quitando archivos (unstaging)

Retira todos los archivos del staging:

```bash
git restore --staged .
```

O un archivo específico:

```bash
git restore --staged app/utils/constants.js
```
