# README - PPS Unidad 0 Actividad 3

## Índice

1. [Introducción](#introducción)
   - Objetivo de la actividad
   - Flujo de trabajo con Git

2. [Configuración Inicial de Git](#configuración-inicial-de-git)
   - Configuración del Editor de Comandos
   - Configuración del Visor de Mensajes para `git diff` y `git log`
   - Consulta de las Variables de Configuración de Git
   - Configuración de Colores en Git
  
3. [Creación del Proyecto y Repositorio en GitHub](#creación-del-proyecto-y-repositorio-en-github)
   - Crear la Carpeta del Proyecto
   - Crear un Repositorio Público en GitHub
   - Configuración del Repositorio en Línea de Comandos
   - Confirmación en GitHub

4. [Iniciando el Proyecto](#iniciando-el-proyecto)
   - Visualización de Archivos en el Directorio
   - Creación del Archivo `README.md`
   - Comprobación del Estado de Git
   - Escribir una Descripción en el Archivo `README.md`
   - Volver a Comprobar el Estado de Git

5. [Ignorando Archivos](#ignorando-archivos)
   - Creación de la Carpeta `Excluded`
   - Creación de Archivos para Pruebas
   - Creación del Archivo `.gitignore`
   - Configuración de `.gitignore`
   - Comprobación del Estado de Git para Archivos Ignorados

6. [Trabajo con Git](#trabajo-con-git)
   - Creación del Archivo `index.html`
   - Comprobación del Estado del Proyecto
   - Añadir Archivo y Realizar Commit
   - Comprobación Final y Subida de Cambios

7. [Creación de Nuestro Servidor Web y Visualización del Proyecto](#creación-de-nuestro-servidor-web-y-visualización-del-proyecto)
   - Iniciar el Servidor Web con PHP
   - Visualizar la Página en el Navegador

8. [Seguimos Trabajando con Git](#seguimos-trabajando-con-git)
   - Crear una Copia de Respaldo del Archivo `index.html`
   - Comprobar las Diferencias con `git diff`
   - Restaurar el Archivo a la Versión Anterior
   - Sobrescribir `index.html` con `index.html.save` usando `git mv`
   - Realizar Cambios desde la Interfaz de GitHub y Sincronizar

9. [Visualización del Historial de Confirmaciones con `git log`](#visualización-del-historial-de-confirmaciones-con-git-log)
   - Mostrar el Historial Completo de Confirmaciones
   - Mostrar los Logs de los Últimos 3 Commits
   - Mostrar los Logs con el Modificador `--pretty`
   - Mostrar los Logs de los Últimos 2 Commits con Diferencias
   - Mostrar los Logs de las Modificaciones Realizadas en el Último Día

10. [Ramas en Git](#ramas-en-git)
    - Listar las Ramas Existentes
    - Crear una Nueva Rama `Vers1`
    - Modificar el Archivo `index.html` y Guardar en la Rama `Vers1`
    - Subir la Rama `Vers1` al Repositorio Remoto
    - Verificación de las Diferencias entre Ramas

---

## Introducción
En esta actividad, aprenderemos los conceptos básicos de control de versiones con Git y la gestión de repositorios en GitHub. La actividad se centra en configurar Git en nuestro entorno de trabajo, crear un repositorio en GitHub y realizar operaciones esenciales de seguimiento de cambios en un proyecto de desarrollo web. A través de una serie de pasos guiados, abordaremos la configuración de usuario, personalización de Git, manejo de archivos con `.gitignore`, y los comandos fundamentales para crear, modificar y sincronizar proyectos en un repositorio remoto.

El objetivo principal es familiarizarnos con el flujo de trabajo de Git para que podamos gestionar eficazmente el historial de versiones en futuros proyectos y colaborar en equipo de manera eficiente. Como práctica, desarrollaremos una simple página web con un mensaje de "Hola Mundo" que nos servirá para explorar cómo Git rastrea cambios y permite un control detallado del código fuente.

## Creación de repositorio 

En esta sección crearemos un repositorio en GitHub que contenga un proyecto en PHP para visualizar la información de diferentes usuarios, incluyendo una foto y una descripción. Primero debemos crear el repositorio desde la plataforma de Github, ya visto en prácticas anteriores, para despues ir documentando todo en el README.md.

Haremos uso de comandos básicos como:
   ```bash
echo "# PPS-Unidad0Actividad5-TuNombre" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:TuUsuarioGitHub/PPSUnidad0Actividad5TuNombre.git
git push -u origin main
   ```
o comandos como ```git remote -v``` para verificar que el repositorio remoto esté correctamente configurado.

Una vez creado el repositorio debemos crear la distribución del mismo. Dentro de la carpeta del proyecto, se debe organizar y crear los archivos necesarios para el proyecto PHP. El objetivo es crear una página donde se visualice información de diferentes usuarios, incluyendo una foto de cada usuario y una descripción breve de cada usuario:

   ```graphql
PPS-ActividadUnidad0-TuNombre/
├── images/                  # Carpeta para las fotos de los usuarios
├── index.php                # Archivo principal en PHP para visualizar usuarios
├── README.md                # Documentación del proyecto
└── profile/                 # Carpeta nuestra página de perfil personalizada
   ```


## Visualizando la página web
En esta sección, vamos a lanzar un servidor web local utilizando PHP para visualizar el contenido de nuestra página web. Además, añadiremos una imagen de perfil y crearemos una página individual que permita visualizar nuestro perfil personal.

*1*. **Iniciar el Servidor PHP**
Para comenzar, lanzaremos un servidor PHP desde la terminal para que podamos visualizar nuestra página web en un navegador, con el siguiente comando:
   ```bash
   php -S 0.0.0.0:8080
   ```
Esto iniciará un servidor en el puerto 8080. Podremos acceder a la página web desde el navegador en la siguiente dirección:

   ```plaintext
   http://localhost:8080
   ```

> **Nota**: Mantendremos la terminal abierta mientras el servidor esté activo. Si queremos detener el servidor en algún momento, simplemente presionaremos ``CTRL + C`` en la terminal.

*2*. **Añadir una Imagen de Perfil**
Ahora vamos a personalizar la página web añadiendo una imagen de perfil. Colocaremos una foto o avatar en la carpeta ``img`` dentro de nuestro proyecto. El archivo de imagen debe llevar nuestro nombre como nombre de archivo, sin espacios y con una extensión compatible (por ejemplo, ``nombre.jpg`` o ``nombre.png``):
   ```plaintext
   img/Cristian.png
   ```
> **Nota**: Asegurémonos de que la imagen tenga un tamaño adecuado para una visualización en web, optimizando si es posible.

*3*. **Crear una Página de Perfil en HTML**
A continuación, crearemos un archivo HTML en la carpeta profile con el mismo nombre que el de nuestra imagen de perfil. Este archivo HTML servirá como nuestra página de perfil personalizada.
   - Primero, navegamos a la carpeta profile y creamos el archivo HTML. Por ejemplo:

      ```bash
      touch profile/Cristian.html
      ```

   - Luego, editaremos este archivo HTML para incluir nuestra imagen de perfil y una breve descripción. Podemos usar un editor de texto para agregar el siguiente contenido:

      ```html
      <!DOCTYPE html>
      <html lang="es">
      <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width, initial-scale=1.0">
         <title>Perfil de Cristian</title>
      </head>
      <body>
         <h1>Bienvenido a mi perfil</h1>
         <img src="../img/Cristian.png" alt="Foto de Cristian" width="200">
         <p>Hola, soy Cristian. Esta es mi página de perfil donde puedes conocer un poco más sobre mí.</p>
      </body>
      </html>
      ```
En este código, nos aseguramos de que la ruta de la imagen esté correctamente referenciada (``../img/Nombre.png``).

*4*. **Diseñar página principal**
A continuación, crearemos la página principal que hará de enlace hacia los perfiles creados, en la carpeta `profile`. El archivo se llamará `index.html` y tendrá un código como este:

   ```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista de Perfiles de Usuarios</title>
</head>
<body>
    <h1>Bienvenidos a la Página de Perfiles</h1>
    <p>A continuación, encontrarás una lista de usuarios y sus perfiles.</p>

    <div class="usuarios">
        <!-- Perfil de Cristian -->
        <div class="usuario">
            <h2><a href="profile/Cristian.html">Cristian</a></h2>
            <a href="profile/Cristian.html">
                <img src="img/Cristian.jpg" alt="Foto de Cristian" width="150">
            </a>
            <p>Hola, soy Cristian. Haz clic en mi nombre o en mi foto para ver mi perfil completo.</p>
        </div>

        <!-- Puedes añadir más perfiles de otros usuarios aquí -->
    </div>
</body>
</html>
   ```

*4*. **Visualizar página**
Una vez que hayamos configurado la imagen y creado la página de perfil, volvemos al navegador y refrescamos la página (o accedemos nuevamente a ``http://localhost:8080``). Revisaremos el contenido para verificar que la imagen de perfil y la página HTML personalizada se muestren correctamente. Si todo está bien configurado, deberíamos ver nuestra página de perfil personalizada con la foto que añadimos y el texto que describimos.

Con estos pasos, hemos lanzado el servidor local, añadido una imagen personalizada, y creado una página de perfil HTML. Esto nos permite visualizar el contenido de nuestra página web en un entorno de desarrollo local y comprobar cómo se actualizan los cambios en tiempo real.

<p align="center">
  <img src="./images/Configuracion_inicial_Git.png" alt="Configuración Inicial de Git">
</p>
<p align="center"><em>Imagen 1: Configuración Inicial de Git</em></p>



## Colaborando en el Proyecto
En esta fase, vamos a colaborar activamente en los repositorios de nuestros compañeros y les permitiremos colaborar en el nuestro. Utilizaremos varias funciones de Git y GitHub para gestionar esta colaboración de forma ordenada y eficiente.

*1*. **Añadir colaboradores a nuestro proyecto**
Para que nuestros compañeros puedan colaborar en nuestro proyecto, primero debemos añadirlos como colaboradores en nuestro repositorio en GitHub. Esto se realiza desde la Configuración del Repositorio, en la sección de Collaborators.
   - Vamos a **Settings** > **Collaborators** y añadimos los nombres de usuario de al menos dos compañeros. 
   - Nuestros compañeros recibirán una invitación para colaborar en el proyecto. Una vez que acepten la invitación, podrán realizar cambios en el repositorio.

*2*. **Colaborar en los Proyectos de Nuestros Compañeros**
A continuación, vamos a colaborar en los proyectos de nuestros compañeros. Repetimos los siguientes pasos para cada repositorio al que nos hayan invitado.

   - Aceptamos la Invitación: Nos dirigimos a nuestro correo o a la sección de notificaciones de GitHub para aceptar la invitación de colaboración en el repositorio del compañero.
   - Clonamos el Repositorio: Una vez aceptada la invitación, clonamos el repositorio en nuestro equipo. Para evitar conflictos, creamos una nueva carpeta específica para este proyecto.
   - Para evitar interferir en el trabajo de nuestro compañero, vamos a trabajar en una nueva rama con nuestro nombre:
      ```bash
      # Crea una rama con mi nombre
      git branch Cristian

      # Cambiar a mi rama
      git checkout MiNombre

      # Verificar nuestra rama
      git status -s
      ```
   - Antes de realizar cambios, verificamos los remotos configurados para asegurarnos de que estamos conectados al repositorio correcto, con `git remote -v`
   - Añadimos nuestro archivo de imagen (foto o avatar) y nuestro perfil HTML a la rama que hemos creado:
      ```bash
      # Copiar archivos de perfil de mis carpetas a las de los compañeros
      ```
*3*. **Configuración del Repositorio en Línea de Comandos**

Ahora, sigue los comandos a continuación para inicializar el repositorio, agregar un archivo README y vincular el repositorio local con el remoto en GitHub.

   ```bash
# Crea un archivo README.md con el nombre del proyecto
echo "# PPS-Unidad0Actividad4-TuNombre" >> README.md

# Inicializa un repositorio de Git en la carpeta actual
git init

# Agrega el archivo README.md al área de preparación
git add README.md

# Realiza el primer commit con un mensaje descriptivo
git commit -m "first commit"

# Cambia la rama principal a 'main'
git branch -M main

# Agrega el repositorio remoto (reemplaza "TuNombreDeUsuario" por tu nombre de usuario en GitHub)
git remote add origin git@github.com:TuNombreDeUsuario/PPS-Unidad0Actividad4-TuNombre.git

# Envía los cambios a la rama principal del repositorio remoto
git push -u origin main
   ```

> Nota: Si ya tienes un ``origin`` configurado, es decir, un repositorio remoto configurado y deseas hacer cambios en otro repositorio al poner un origen distinto al configurado se genera un error `remote origin already exists`. Esto ocurre porque el comando git remote add origin intenta agregar un nuevo origen, pero el nombre origin ya está en uso. Para solucionarlo, primero verifica las url que estén configuradas y, luego, actualizalas. 
> - **Verifica el origen remoto actual**:
>    ```bash
>   git remote -v
>   ```
> - **Actualiza el origen remoto**:
>    ```bash
>   git remote set-url origin git@github.com:Clealg01/PPS-Unidad0Actividad4-Cristian.git
>   ```
> - **Elimina el origen y vuelve a agregarlo**:
>    ```bash
>    git remote remove origin
>    git remote add origin git@github.com:Clealg01/PPS-Unidad0Actividad4-Cristian.git
>    ```
> - **Verifica el origen remoto actual**: <p align="center">
  <img src="./images/solucion_cambiar_repositorio_remoto.png" alt="Solución cambiar repositorio remoto">
</p>

> <p align="center"><em>Imagen 2: Solución cambiar repositorio remoto</em></p>
 
*4*. **Confirmación en GitHub**

Después de ejecutar estos comandos, tu proyecto debería estar disponible en GitHub en el repositorio ``PPS-Unidad0Actividad4-TuNombre``. Puedes verificarlo visitando el enlace de tu repositorio en GitHub.

> Nota: Asegúrate de reemplazar ``TuNombreDeUsuario`` y ``TuNombre`` en los comandos y el nombre de la carpeta según corresponda a tu caso.

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="./images/inicializar_repositorio.png" alt="Inicializar repositorio" width="300">
        <br><em>Imagen 3: Inicializar repositorio</em>
      </td>
      <td align="center">
        <img src="./images/Subir%20README%20a%20repositorio%20remoto.png" alt="Subir archivo README.md a repositorio remoto" width="300">
        <br><em>Imagen 4: Subir archivo README.md a repositorio remoto</em>
      </td>
    </tr>
  </table>
</div>

</div>

<p align="center">
  <img src="./images/Repositorio_actualizado.png" alt="Repositorio actualizado">
</p>
<p align="center"><em>Imagen 5: Repositorio inicializado</em></p>

## Iniciando el Proyecto
En este paso, vamos a inicializar el proyecto y gestionar el archivo `README` con Git, además de realizar algunas comprobaciones de estado.

*1.* **Visualización de Archivos en el Directorio**

Primero, haremos un listado de todos los archivos y carpetas en el directorio del proyecto en forma de árbol. Esto permite ver la estructura del proyecto. Ejecuta el siguiente comando:

   ```bash
tree -a
   ```
> Nota: Si no tienes el comando tree instalado, puedes instalarlo con ``sudo apt install tree`` en sistemas basados en Debian/Ubuntu o utilizar ``ls -a`` para ver todos los archivos, incluidos los ocultos.

   ```bash
┌──(kali㉿kali)-[~/PPS-Unidad0Actividad4-Cristian]
└─$ tree -a
.
├── .git
│   ├── branches
│   ├── COMMIT_EDITMSG
│   ├── config
│   ├── description
│   ├── FETCH_HEAD
│   ├── HEAD
│   ├── hooks
│   │   ├── applypatch-msg.sample
│   │   ├── commit-msg.sample
│   │   ├── fsmonitor-watchman.sample
│   │   ├── post-update.sample
│   │   ├── pre-applypatch.sample
│   │   ├── pre-commit.sample
│   │   ├── pre-merge-commit.sample
│   │   ├── prepare-commit-msg.sample
│   │   ├── pre-push.sample
│   │   ├── pre-rebase.sample
│   │   ├── pre-receive.sample
│   │   ├── push-to-checkout.sample
│   │   ├── sendemail-validate.sample
│   │   └── update.sample
│   ├── index
│   ├── info
│   │   └── exclude
│   ├── logs
│   │   ├── HEAD
│   │   └── refs
│   │       ├── heads
│   │       │   └── main
│   │       └── remotes
│   │           └── origin
│   │               └── main
│   ├── objects
│   │   ├── 06
│   │   │   └── 10c8382742b68028e83bc5ad0895d6e984bbc2
│   │   ├── 08
│   │   │   └── 0cf4f98a19125157be085ef8da9d32a09f70a3
│   │   ├── 0a
│   │   │   ├── 23f4e97569059528f2957c8e6229fe10f56dc1
│   │   │   ├── 2f6f54979a0512d7862297e5ef552e396cba18
│   │   │   └── f2f311f96cb7cce427dc081c41c1984abbe99e
│   │   ├── 0d
│   │   │   └── f1b4f5b570958401ee75f64869cd26b5b8798a
│   │   ├── 17
│   │   │   └── c0af11f16c08d5a789117fe37d8e08e50f241c
│   │   ├── 1d
│   │   │   └── 214bd39011a3ca1fbc037e20b14d100123758f
│   │   ├── 1e
│   │   │   └── 20e3d69c9ffe96dd6395f2ccce8a9a03cb53e4
│   │   ├── 25
│   │   │   └── 5250caed7809bbbf55a4608f766452e757477e
│   │   ├── 26
│   │   │   └── 55d8c93b310811920bfd7f46d51a716e72dc05
│   │   ├── 28
│   │   │   └── 2ca021175ae44b4a9d8ff369d08d70cafb23f8
│   │   ├── 38
│   │   │   └── 76a1175868d672df375cd881cb4d835272c688
│   │   ├── 40
│   │   │   └── 4b872838bf520f12ac42bad66a0cc8e5516fea
│   │   ├── 42
│   │   │   └── d5057236fa35ad5c12110ff17775f56155f476
│   │   ├── 46
│   │   │   └── 8a0e1050f0cb4c2160180343562f5c63be6c25
│   │   ├── 47
│   │   │   └── cf883badaeb8295ef540d05b8f6e983579ad0d
│   │   ├── 4c
│   │   │   └── e1a90128610bcba66f49ffcca626636edbc228
│   │   ├── 4e
│   │   │   └── 09e21fae17bb055799d63a66af678b40161f2c
│   │   ├── 50
│   │   │   └── 04fc6ac9c5cd4a8e1fa8017bde1c1b4102e9cf
│   │   ├── 5a
│   │   │   └── c8be479ad61ed6e3f60467acef10d56cbee6ae
│   │   ├── 82
│   │   │   └── a0446c382141bf433d6c8217354b9fbbfd4a20
│   │   ├── 86
│   │   │   ├── 1f6deeaa193a008e5ed4d24967972afc857ae2
│   │   │   └── 213e189bfcbe7c6a30b76f46e2f1915f2e6572
│   │   ├── 88
│   │   │   └── 6a86f8fd585938ec1f9da6423be96296e81e96
│   │   ├── 8b
│   │   │   └── 137891791fe96927ad78e64b0aad7bded08bdc
│   │   ├── a1
│   │   │   └── b5ab8412586232f0c4a0e361d7b99f5bf87489
│   │   ├── a3
│   │   │   └── a15ba76b649eb205ff55b14006343c4cfc1e22
│   │   ├── a5
│   │   │   └── 3b67a857e4de5e3e7d8afe841cbf00b3331183
│   │   ├── b9
│   │   │   ├── 19bc4de4e98ec10c7d6dbdb38b9978694fc922
│   │   │   └── 6ee6f222d00421e01489c49e66f377d048d259
│   │   ├── c3
│   │   │   └── abda589821069081e4b6418c124d6ef469fc99
│   │   ├── c6
│   │   │   └── 12e8398d96a2fdbbe8e9864c812fb5db3da45c
│   │   ├── ca
│   │   │   └── 1e2cd00bb81fbef59ec29dccc640534e87a641
│   │   ├── d8
│   │   │   └── 04a56eaf7f64dffa23120d1d64a1b905e2bbf2
│   │   ├── dc
│   │   │   └── 244d114def754aa5f3f927e70f38fadb3ca363
│   │   ├── de
│   │   │   └── f56c6f75e90670b7268cf5d731021cb20eb83b
│   │   ├── eb
│   │   │   └── 09aa8b05ec525c277893e9d4b0872da62f5f0a
│   │   ├── ee
│   │   │   └── 389d489ca6b35b624f48bdad6184dec0169853
│   │   ├── f7
│   │   │   └── fa8a03fd54ecd451ea623f39d34eed1d5f1945
│   │   ├── f9
│   │   │   └── bc756da239bf824a1031360804ef74e94247f6
│   │   ├── fa
│   │   │   └── 7f5eb769ba1b2721036935cf20a522089a099c
│   │   ├── ff
│   │   │   └── e6a881928fab313bd5eef9bb2ac516cf287432
│   │   ├── info
│   │   └── pack
│   ├── ORIG_HEAD
│   ├── REBASE_HEAD
│   └── refs
│       ├── heads
│       │   └── main
│       ├── remotes
│       │   └── origin
│       │       └── main
│       └── tags
├── images
│   ├── Configuracion_inicial_Git.png
│   ├── inicializar_repositorio.png
│   ├── Repositorio_actualizado.png
│   ├── solucion_cambiar_repositorio_remoto.png
│   └── Subir README a repositorio remoto.png
└── README.md

58 directories, 78 files
   ```
<p align="center"><em>Resultado del comando en repositorio local de Linux</em></p>

*2.* **Creación del Archivo ``README``**

Si aún no existe un archivo ``README.md``, créalo con el siguiente comando:
   ```bash
touch README.md
   ```
A continuación, añade el archivo ``README.md`` al área de preparación en Git:

   ```bash
git add README.md
   ```

*3.* **Comprobación del Estado de Git**

Comprueba el estado de Git para ver los cambios pendientes en el proyecto. Puedes hacerlo con el comando:

   ```bash
git status -s
   ```
o, alternativamente:

   ```bash
git status --short
   ```
Esto mostrará un listado breve del estado de los archivos en el repositorio.

*4.* **Escribir una Descripción en el Archivo ``README.md``**

Abre el archivo ``README.md`` en tu editor de texto y escribe una breve descripción de la actividad. Puedes utilizar el siguiente comando si estás usando nano como editor:

   ```bash
nano README.md
   ```
Dentro del archivo, escribe algo similar a:

   ```markdown
# Proyecto PPS - Unidad 0 Actividad 4
Esta actividad consiste en configurar un repositorio Git y realizar tareas básicas de seguimiento de versiones.
   ```
Guarda los cambios y cierra el editor.

*5.* **Volver a Comprobar el Estado de Git**

Una vez hayas modificado el archivo ``README.md``, vuelve a comprobar el estado de Git para ver los cambios pendientes de confirmación:

   ```bash
git status -s
   ```
Esto te permitirá confirmar que el archivo ``README.md`` tiene cambios pendientes que aún no se han guardado en el historial de Git.

<p align="center">
  <img src="./images/Modificacion-con-nano-README.png" alt="Modificacion con nano del archivo README">
</p>
<p align="center"><em>Imagen 6: Modificacion con nano del archivo README</em></p>

<p align="center">
  <img src="./images/Comprobar_cambios_pendientes_GIT.png" alt="Comprobar los cambios pendientes que hay en el repositorio local">
</p>
<p align="center"><em>Imagen 7: Comprobar los cambios pendientes que hay en el repositorio local</em></p>

## Ignorando Archivos
En esta sección, configuraremos Git para que ignore ciertos archivos y carpetas que no queremos que se incluyan en el repositorio. Esto es útil para evitar subir documentos o archivos temporales que no son necesarios en el proyecto.

*1.* **Creación de la Carpeta ``Excluded``**

Primero, crea una carpeta llamada ``Excluded`` dentro del directorio principal del proyecto. Esta carpeta contendrá la documentación o archivos que no queremos rastrear ni sincronizar en GitHub.

   ```bash
mkdir Excluded
   ```

*2.* **Creación de Archivos para Pruebas**

Dentro de la carpeta ``Excluded``, crea un archivo vacío (por ejemplo, ``doc.txt``) para verificar que Git puede ignorarlo correctamente. Además, en el directorio principal del proyecto, crea un archivo llamado ``excluido.txt``:

   ```bash
touch Excluded/doc.txt
touch excluido.txt
   ```

<p align="center">
  <img src="./images/Creacion_archivos_excluidos.png" alt="Creación de archivos y carpetas a excluir">
</p>
<p align="center"><em>Imagen 8: Creación de archivos y carpetas a excluir</em></p>

*3.* **Creación de archivo ``.gitignore``**
A continuación, crea un archivo ``.gitignore`` en el directorio principal del proyecto. Este archivo le indicará a Git qué archivos o carpetas debe ignorar. Usa el siguiente comando para crear el archivo:

   ```bash
touch .gitignore
   ```

*4.* **Configuración ``.gitignore``**
Abriremos con el editor `nano` el archivo para indicar a Git que ignore cualquier archivo con extensión, por ejemplo, ``.txt`` y la carpeta `Excluded`

   ```plaintext
# Ignorar todos los archivos .txt
*.txt

# Ignorar carpetas 
Excluded/
   ```

> Nota: Si vamos a usar nano, directamente se crearía y se podría editar el archivo en un solo comando: `nano .gitignore`.

<p align="center">
  <img src="./images/Creacion_gitignore.png" alt="Creación del archivo gitignore">
</p>
<p align="center"><em>Imagen 9: Creación del archivo .gitignore</em></p>

*5.* **Comprobación del Estado de Git**
Verifica el estado del proyecto para confirmar que Git está ignorando correctamente los archivos especificados en ``.gitignore``. Para ello, se debe de añadir el archivo al área de preparación y confirmar los cambios para que Git comience a respetar las reglas de ignorado.

   ```bash
git add .gitignore
git commit -m "Agrega .gitignore para ignorar archivos y carpetas no deseadas"
git status -s

   ```

Si todo está configurado correctamente, Git no debería mostrar ``doc.txt``, ``excluido.txt``, ni la carpeta ``Excluded`` en el listado de archivos no rastreados.

<p align="center">
  <img src="./images/Verificacion_gitignore.png" alt="Verificación del uso de gitignore">
</p>
<p align="center"><em>Imagen 10: Verificación de la exclusión de archivos en Git, con el archivo .gitignore</em></p>

## Trabajo con Git
En esta sección, aprenderemos a añadir un nuevo archivo HTML, visualizar el estado del proyecto, realizar un commit, y subir los cambios a nuestro repositorio en GitHub.

*1.* **Creación de archivo con nombre `index.html`**
Con el uso del editor nano crearemos el archivo mediante el comando `nano index.html` y añadimos el siguiente código para mostrar un mensaje personalizado:

   ```html
<h1>Hola Cristian ¿Qué tal te encuentras?</h1>
   ```

<p align="center">
  <img src="./images/Creacion_archivo_html.png" alt="Creación del archivo html">
</p>
<p align="center"><em>Imagen 11: Creación del archivo html</em></p>
   
*2.* **Comprobación del Estado del Proyecto**
Verifica el estado del proyecto para ver los archivos no rastreados o modificados mediante el comando git status:
   ```bash
git status -s
   ```

Esto mostrará que se habrá añadido un nuevo archivo, el ``.html``.
*3.* **Añadir archivo y realizar commit**
Añadimos el archivo index.html al área de preparación y realizamos un commit con el mensaje que describe los cambios

   ```bash
git add index.html
git commit -am "Añade archivo index.html con mensaje de bienvenida"
   ```

> ⚠️ **Advertencia**: Este comando (``git commit -am``) combina ``add`` y ``commit`` en un solo paso, pero solo funciona para archivos que ya están siendo rastreados por Git. Como ``index.html`` es un archivo nuevo, primero se debe agregar con ``git add`` antes de usar este método.<p align="center">
  <img src="./images/Error_no_añadir_archivo_html.png" alt="Creación del archivo html">
</p>

*4.* **Comprobación final y subir cambios**
Verificamos el estado del proyecto de nuevo y subimos los cambios al repositorio remoto en GitHub

   ```bash
git status -s
git push 
   ```

<p align="center">
  <img src="./images/html_subido.png" alt="Subir archivo html">
</p>
<p align="center"><em>Imagen 12: Subir archivo html</em></p>

## Creación de nuestro servidor web y visualización de nuestro proyecto
En este paso, vamos a lanzar un servidor web local para visualizar la página HTML que hemos creado en el proyecto. Utilizaremos PHP para iniciar el servidor de una manera rápida y sencilla.

*1.* **Iniciar el Servidor Web con PHP**
Se debe levantar en una terminal, en el mismo directorio, un servidor PHP. Con la dirección 0.0.0.0:8080 podemos indicar que el servidor escuchará en todas las interfaces de red en el puerto 8080 de tu equipo. 

   ```bash
   php -S 0.0.0.0:8080 
   ```

*2.* **Visualizar la Página en el Navegador**
Se puede visualizar desde un navegador web, en nuestro caso Firefox, indicando la dirección:
   ```plaintext
   http://localhost:8080
   ```
Para cerrar el servicio levantado, desde la terminal en la que lo iniciamos presionamos `CTRL + C`.

<p align="center">
  <img src="./images/levantar_servicio_php.png" alt="Levantar servicio PHP">
</p>
<p align="center"><em>Imagen 13: Levantar servicio PHP</em></p>

## Seguimos Trabajando con Git
En este paso, realizaremos varias operaciones avanzadas en Git, incluyendo la comparación de diferencias, restauración de archivos, y sincronización con GitHub. También practicaremos cómo trabajar con una copia de respaldo de un archivo y cómo actualizar nuestro proyecto local con cambios realizados en GitHub.

*1.* **Crear una Copia de Respaldo del Archivo ``index.html``**
Realiza una copia del archivo index.html con el nombre index.html.save para tener un respaldo de su contenido actual:
   ```bash
   cp index.html index.html.save 
   ```
A continuación, debes modificar el archivo original y realizar cambios en el contenido mostrado en la página y verificar el estado actual del proyecto con `git status -s`.

<p align="center">
  <img src="./images/Creacion_backup_y_modificacion_html.png" alt="Creacion de un backup del servicio html y modificación del mismo">
</p>
<p align="center"><em>Imagen 14: Creacion de un backup del servicio html y modificación del mismo</em></p>

*2.* **Comprobar las diferencias con ``git diff``**
Para ver las diferencias entre el archivo index.html modificado y la versión anterior en el repositorio podemos usar:
   ```bash
   git diff index.html 
   ```
Este comando mostrará las líneas que se han cambiado en el archivo. Para poder ver los cambios realizados en el contenido, en la propia página, debemos abrir el navegador y refrescar la página. Para volver a la versión anterior del archivo index.html, utiliza el siguiente comando:
   ```bash
   git restore index.html
   ```
Esto deshará los cambios no confirmados en index.html, restaurándolo a su estado anterior en el repositorio.

<p align="center">
  <img src="./images/Visualizar_cambios_giff_y_restauracion_version_anterior.png" alt="Visualizar cambios con giff y realizar cambios a una versión anterior del servicio">
</p>
<p align="center"><em>Imagen 15: Visualizar cambios con giff y realizar cambios a una versión anterior del servicio</em></p>

*3.* **Sobrescribir ``index.html`` con ``index.html.save`` usando ``git mv``**
Utiliza el comando git mv para reemplazar index.html con la copia de respaldo index.html.save:
   ```bash
   git mv index.html.save index.html
   ```
Esto renombrará ``index.html.save`` a ``index.html`` y hará que Git reconozca este cambio. 

> Nota: Para que git mv funcione, el archivo a sobreescribir debe de estar eliminado.

A continuación, verificamos el estado del proyecto, realizados un commit con los cambios y subimos los cambios al repositorio en GitHub:
   ```bash
git status -s
git commit -m "Restaurar index.html desde respaldo"
git push origin main
   ```

<p align="center">
  <img src="./images/Usar_backup.png" alt="Hacer uso del backup del servicio">
</p>
<p align="center"><em>Imagen 16: Hacer uso del backup del servicio</em></p>

*4.* **Realizar cambios desde interfaz gráfica de Github**
Ve a [GitHub.com](https://github.com/), abre el archivo index.html en el repositorio y edítalo directamente en la página de GitHub. Realiza cambios y guarda con un mensaje de commit. Después de realizar cambios en GitHub, vuelve a la terminal local y utiliza git pull para traer esos cambios al proyecto local:
   ```bash
git pull origin main
   ```
Refresca el navegador para ver cómo los cambios hechos en GitHub se han reflejado en el servidor local.

<p align="center">
  <img src="./images/Realizar_cambios_desde_Github.png" alt="Realizar cambios desde Github">
</p>
<p align="center"><em>Imagen 17: Realizar cambios desde Github</em></p>

<p align="center">
  <img src="./images/Traer_cambios.png" alt="Traer cambios desde Github a repositorio local">
</p>
<p align="center"><em>Imagen 18: Traer cambios desde Github a repositorio local</em></p>

## Git log
En este paso, exploraremos el comando git log y sus diferentes opciones para visualizar el historial de confirmaciones en el proyecto, guiandonos por el libro de [Fundamentos de Git](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Ver-el-Historial-de-Confirmaciones).

*1.* **Mostrar el Historial Completo de Confirmaciones**
Para ver el historial completo de confirmaciones, utiliza el comando básico:
   ```bash
git log
   ```
Esto mostrará una lista de todos los commits, junto con su hash, autor, fecha y mensaje de commit.

<p align="center">
  <img src="./images/Historial_de_confirmaciones.png" alt="Historial de confirmaciones">
</p>
<p align="center"><em>Imagen 19: Historial de confirmaciones</em></p>

*2.* **Mostrar los Logs de los Últimos 3 Commits**
Para limitar la visualización a los últimos 3 commits, utiliza la opción -n, donde n es el número de commits que quieres ver:
   ```bash
git log -3
   ```

<p align="center">
  <img src="./images/Ultimos_3_logs.png" alt="Mostrar los últimos 3 logs">
</p>
<p align="center"><em>Imagen 20: Mostrar los últimos 3 logs</em></p>

*3.* **Mostrar los Logs Utilizando el Modificador `--pretty`**
El modificador ``--pretty`` permite personalizar el formato de salida del ``git log``. Puedes usar otros formatos predefinidos o personalizados, como:
- oneline: muestra cada commit en una sola línea.
- short: muestra un formato reducido.
- full: muestra el formato completo con todos los detalles

   ```bash
   git log --pretty=oneline
   ```

<p align="center">
  <img src="./images/Uso_modificador_pretty.png" alt="Algunos ejemplos del uso del modificador pretty">
</p>
<p align="center"><em>Imagen 21: Algunos ejemplos del uso del modificador pretty para mostrar logs</em></p>

*4.* **Mostrar los Logs de los Últimos 2 Commits con las Diferencias**
Para ver los detalles de los últimos 2 commits, incluyendo las diferencias en los archivos modificados (``diff``), utiliza ``-p`` junto con el límite de commits ``-2``:
   ```bash
   git log -p -2
   ```
Esto mostrará los últimos 2 commits (por ``-2``) y sus diferencias de código (por ``-p``), permitiéndote ver los cambios específicos en cada uno.

<p align="center">
  <img src="./images/Ultimos_2_commits_diferencias.png" alt="Mostrar los últimos 2 logs incluyendo las diferencias en los archivos modificados ">
</p>
<p align="center"><em>Imagen 22: Mostrar los últimos 2 logs incluyendo las diferencias en los archivos modificados</em></p>

*5.* **Mostrar los Logs de las Modificaciones Realizadas en el Último Día**
Para ver los commits realizados en las últimas 24 horas, puedes usar el modificador ``--since``. Este comando muestra los commits realizados desde una fecha específica:
   ```bash
   git log --since="1 day ago"
   ```
Esto listará todos los commits que se hayan hecho en el último día. Puedes cambiar ``1 day ago`` por ``2 days ago``, ``1 week ago``, o fechas específicas si necesitas más flexibilidad.

<p align="center">
  <img src="./images/Cambios_ultimas_24h.png" alt="Mostrar los commits realizados en las últimas 24 horas">
</p>
<p align="center"><em>Imagen 23: Mostrar los commits realizados en las últimas 24 horas</em></p>

## Ramas en Git
En esta sección, vamos a listar las ramas existentes, crear una nueva rama y trabajar con cambios específicos en esa nueva rama. Las ramas en Git nos permiten trabajar en nuevas funcionalidades o versiones de nuestro proyecto sin afectar la rama principal (``main``).

*1.* **Listar las Ramas Existentes**
Para ver las ramas actuales en el repositorio, utiliza el siguiente comando:
   ```bash
   git branch
   ```
Este comando mostrará una lista de todas las ramas locales. La rama en la que estás actualmente estará marcada con un asterisco (`*`).

*2.* **Crear una Nueva Rama ``Vers1``**
Crea una nueva rama llamada ``Vers1`` a partir de la rama actual (suponiendo que estás en ``main``). Esto creará una copia de la rama actual:
   ```bash
   git branch Vers1
   ```
Una vez creada, cambia a la nueva rama con:

   ```bash
   git checkout Vers1
   ```

> Nota: También puedes crear y cambiar a la nueva rama directamente con el siguiente comando combinado:
>   ```bash
> git checkout -b Vers1
>   ```

<p align="center">
  <img src="./images/Manejo_ramas.png" alt="Listado y manejo de ramas y creación de rama Vers1">
</p>
<p align="center"><em>Imagen 24: Listado y manejo de ramas y creación de rama Vers1</em></p>

*3.* **Modificar el archivo ``index.html`` y guradarlo en la rama ``Vers1``**
Realiza una modificación en el archivo index.html en la rama Vers1. Abre el archivo en tu editor de texto, haz los cambios necesarios, y guarda el archivo. Una vez que hayas hecho las modificaciones en index.html, añade el archivo al área de preparación y realiza un commit de los cambios:
   ```bash
git add index.html
git commit -m "Modificación de index.html en la rama Vers1"
   ```

*4.* **Subir la rama ``Vers1`` al repositorio Remoto**
Para subir la rama Vers1 al repositorio remoto, utiliza el siguiente comando:
   ```bash
git push origin Vers1
   ```
Este comando creará la rama ``Vers1`` en el repositorio remoto y subirá los cambios de la rama local. Ahora, el archivo ``index.html`` de la rama ``main`` y la rama ``Vers1`` serán diferentes en el repositorio.

<p align="center">
  <img src="./images/Modificacion_html_rama_Vers1.png" alt="Modificación del archivo html en la rama Vers1 y subida en repositorio remoto para creación de la rama simultáneamente">
</p>
<p align="center"><em>Imagen 25: Modificación del archivo html en la rama Vers1 y subida en repositorio remoto</em></p>

*5.* **Verificación de las Diferencias entre Ramas**
Puedes verificar que los archivos en la rama main y Vers1 son diferentes cambiando de rama y comparando los archivos:
   ```bash
git checkout main
cat index.html   # Ver el contenido en la rama main

git checkout Vers1
cat index.html   # Ver el contenido en la rama Vers1
   ```
Esta comparación confirma que ``index.html`` tiene contenido diferente en cada rama. Se deen ejecutar por separado los comandos, primero los 2 primeros para comprobar una rama principal (`main`) y luego los 2 últimos para comparar la rama nueva (`Vers1`).

<p align="center">
  <img src="./images/Diferencias_entre_ramas_en_local.png" alt="Mostrar la diferencia entre ramas en el mismo archivo">
</p>
<p align="center"><em>Imagen 26: Mostrar la diferencia entre ramas en el mismo archivo</em></p>
