
# Desarrolladores de Software Antioqueña de Porcinos S.A.S.  

> En esta organización encontrará los repositorios de la empresa Antioquena de Porcinos S.A.S., administrada por 'Área de Desarrollo de Software'.

> [![My Skills](https://skillicons.dev/icons?i=visualstudio,dotnet,cs,aws,azure,docker,redis,github,git,vscode,py,anaconda,tensorflow,html,js,css,nodejs,angular,react,tailwind,vite,postman,stackoverflow,windows,vercel)](https://skillicons.dev)


## Menú
* [Información General](#información-general)
* [Uso de los Repositorios](#uso-de-los-repositorios)
  - [Clonar un Repositorio](#clonar-un-repositorio)
  - [Estructura de las Ramas](#estructura-de-las-ramas)
  - [Agregar Cambios](#agregar-cambios)
  [Versionamiento](#versionamiento)

## Información General
Los proyectos que se desarrollan para la empresa Antioqueña de Porcinos S.A.S. se almacenan en esta organización para el registro de los cambios, bugs, mejoras, documentación y versiones de las aplicaciones.
> Únicamente se tendrán usuarios de la organización.

## Uso de los Repositorios
Es necesario tener los comandos básicos de uso dentro de los procesos de cambios en los repositorios, para consultarlos haga [click aquí](https://gist.github.com/dasdo/9ff71c5c0efa037441b6).
> Báscios para manejo de ramas, consultas de cambios, etc.

### Clonar un Repositorio
Para clonar un repositorio de la organizaión se deberán seguir los siguientes pasos:
* Tener instalado localmente Git en su última versión estable [Ir a la Página de Git](https://git-scm.com/install/windows).
* En tu PC, desde una consola o la aplicación de Git Bash configurar el usuario autorizado en la organización para subir y obtener cambios:

Usuario:
```
git config --global user.name <USERNAME>
```
Correo:
```
git config --global user.email <EMAIL>
```
* En el repositorio de GitHub dar click en el botón **Clone** y seleccionar en **Local** la opción **HTTPS**, copia la URL del repositorio (también puedes tomarla directo de la página del repositorio en el navegador).
* En tu escritorio o en la carpeta que desees guardar el repositorio local debes abrir la terminal o el Git Bash y ejecutar el siguiente comando:
```
git clone <URL>
```
> Es posible que al intentar clonar el repositorio se te pida integresar nuevamente las credenciales de GitHub, solo será la primera vez.

> Nota: La contraseña no se ve en la terminal, al pegar 1 vez el texto dar enter y seguir con el proceso.

### Estructura de las Ramas
El proyecto tiene 3 ramas principales, la rama ```main```, la rama ```developer``` y la rama ```test```. 
* La rama ```main``` es de dónde saldrán los release (que se verán reflejados en las tags) y la que se modificará únicamente cuando las pruebas sobre la rama de desarrollo hayan sido ejecutadas correctamente.
* La rama ```developer``` es dónde se harán los merge de las ramas que solucionan los bugs y errores específicos de las nuevas funcionalidades del proyecto.
* La rama ```test``` es la rama que duplicará a developer y en la que se generarán las pruebas.
> De la rama ```test``` se hace el merge a la rama ```main``` para el release de una nueva versión de la aplicación.

Se deberán crear nuevas ramas por cada uno de los requisitos o tareas a realizar.
> El propósito es mantener siempre una versión estable y poder realizar cambios con prioridad en caso de requerirlo.

La estuctura de estas ramas son para aquellas que solucionan bugs, errores específicos o crean nuevas funcionalidades, manejando la sigueinte nomenclatura ```type/name```:
* Se escriben en **lowerCamelCase**.
* El tipo se divide en:
  - add: Se generan una nuevas funcionalidades.
  - fix: Se realizan correciones de Bugs.
  - hotFix: Se hacen correcciones de bugs que no pasan por pruebas sino que van directamente a la rama ```main``` para ser desplegados.
  - delete: Se eliminan funciones o archivos.
  - docs: Se generan cambios en la documentación.
* El nombre debe ser corto, sin dar muchos detalles.

> Nota: Como sugerencia, tratar de no tener mas de una o dos creadas en tu repositorio local.

### Agregar Cambios
Una vez realizados los cambios en la rama local se podra realizar el envío de cambios con los sigueintes pasos:
- Verificar que se encuentra en la rama con los cambios.
```
git status
```
> También hará un resumen de los cambios a subir en caso de tenerlos.

- 
Los archivos que se agreguen y el mensaje con el que se suben los cambios, debe ser específico y detallar todas las modificaciones, mejoras o aspectos a tener en cuenta con el nuevo código.
- Se recomienda agregar manual el archivo con los cambios en vez de utilizar el comando git add .
- Al agregar los cambios utilizar este comando: git add -p nombrearchivo.html, este comando te permitirá agregar solamente los cambios del archivo que tienen que ver con el commit que se está realizando.
#### Mensajes Commit
Para comentar los cambios se debe escribir el comando:
```
git commit -m "Encabezado" -m "Detalle"
```
o únicamente: (para mensajes más largos que requieren del editor de texto de git para escribir el mensaje).
```
git commit
```

### Solicitud de Integración de Cambios

## Versionamiento

