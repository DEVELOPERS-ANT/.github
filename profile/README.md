
# Desarrolladores de Software Antioqueña de Porcinos S.A.S.  

> En esta organización encontrará los repositorios de la empresa Antioquena de Porcinos S.A.S.

> Administrada por 'Área de Desarrollo de Software'.

> [![My Skills](https://skillicons.dev/icons?i=visualstudio,dotnet,cs,aws,azure,docker,redis,github,git,vscode,py,anaconda,tensorflow,html,js,css,nodejs,angular,react,tailwind,vite,postman,stackoverflow,windows,vercel)](https://skillicons.dev)


## Menú
* [Información General](#información-general)
* [Uso de los Repositorios](#uso-de-los-repositorios)
  - [Clonar un Repositorio](#clonar-un-repositorio)
  - [Estructura de las Ramas](#estructura-de-las-ramas)
  - [Crear una Rama Local](#crear-una-rama-local)
  - [Agregar Cambios](#agregar-cambios)
  - [Solicitud de Integración de Cambios](#solicitud-de-integración-de-cambios)
* [Versionamiento](#versionamiento)

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

### Crear una Rama Local
Para crear una rama local para los cambios sigue estos pasos:
1. Cambia a una rama base de la que se duplicaran los cambios.
```
git checkout <base-branch-name>
```
2. Crea y cambia a la nueva rama
```
git checkout -b <new-branch-name>
```
> Nota: Como sugerencia, tratar de no tener mas de una o dos creadas en tu repositorio local.

### Agregar Cambios
Para agregar cambios dentro de los repositorios se recomienda seguir estos pasos para garantizar un flujo organizado de los cambios:
1. En tu PC dentro de la carpeta local del repositorio crea una rama (en base a una principal) para manejar los cambios locales:
```
git add .
```
2. Verificar que se encuentra en la rama con los cambios:
```
git status
```
> También hará un resumen de los cambios a subir en caso de tenerlos.

3. Agregar los archivos con los cambio:
```
git add .
```

4. Realizar el comentario para agregar a la subida de cambios:
```
git commit -m "Encabezado" -m "Detalle"
```
  o únicamente: (para mensajes quizás más largos que requieren un editor de texto de git para escribir el mensaje).
```
git commit
```
> Los archivos que se agreguen y el mensaje con el que se suben los cambios, debe ser específico y detallar todas las modificaciones, mejoras o aspectos a tener en cuenta con el nuevo código.

> Se recomienda agregar manual el archivo con los cambios en vez de utilizar el comando git add .

5. Subir los cambios: 
```
git push
```
6. (Adicional) En caso de necesitarlo, realizar un 'Pull Request' o Solicitud de Integración de Cambios, para agregar los de cambios a una rama principal.
   
> Cualquiera podrá realizar la solicitud pero únicamente la podrá confirmar y ejecutar un usuario con permisos para hacerlo.

### Solicitud de Integración de Cambios
Esta también llamada 'Pull Request' es la herramienta que le permitira a los repositorios mantener en estabilidad las versiones de los aplicativos, únicamente manteniendo cambios necesarios dentro de las ramas principales y aquellas con solicitudes o cambios no tan prioritarios en ramas alternas secundarias.
Para hacerlo se necesita:

1. Haber realizado la subida de cambios en la rama secundaria dentro del repositorio.
2. En el repositorio de Github abrir la pestaña de 'Pull requests' y dar click en 'New pull request'
3. Se desplegaran las opciones de ```base:``` y ```compare:``` para las ramas destino y origen (en ese orden), con las que definiremos de donde a donde se migraran los cambios.
4. Al seleccionar las ramas se hará una verificación de cambios, esta verificación definirá si está todo listo para hacer la unión de ramas o si se requiere un paso adicional.
5. Luego de la verificación y teniendo lista la unión, dar clicl en "View Pull Request", allis se nos mostrará el resumen de cambios.
6. (Opcional) En caso de requerirlo y tener los permisos para hacerlo, podrá dar click en 'Merge pull Request' para unificar las ramas con los cambios.

> Si eran cambios provenientes de una rama secundaria se podrá elminar dicha rama luego de haber hecho la unión. 

## Versionamiento
Las versiones están esandarizadas por medio de 'Pipelines' que se encargan automáticamente de generarlas en base a políticas establecidas y bajo ciertas condiciones:
- Versión de Pruebas: Esta versión se generará al realizar una unión de cambios (merge) por medio de 'pull request' o al subir directamente cambios a la rama de 'test'.
- Versión Productiva: Esta versión se generará al realizar una unión de cambios (merge) por medio de 'pull request' o al subir directamente cambios a la rama de 'main'.

La estrategia elegida para el versionamiento de las aplicaciones es la **Numeración Semántica**, y se basa de una numeración de 3 dígitos: **X.Y.Z (Mayor.Menor.Parche)**.
1. ***La versión mayor (X)*** se incrementa cuando se realizan cambios que rompen la compatibilidad hacia atrás con versiones anteriores. Esto significa que las modificaciones en el comportamiento del software pueden afectar la forma en que los usuarios interactúan con él.
2. ***La versión menor (Y)*** se incrementa cuando se añaden nuevas características o funcionalidades al software de una manera compatible con las versiones anteriores. Esto indica que se han agregado capacidades nuevas sin romper la estructura existente.
3. ***El número de parche (Z)*** se incrementa cuando se realizan correcciones de errores o soluciones para problemas de manera retrocompatible. Estos cambios no deberían alterar la funcionalidad existente ni la interfaz de programación.

> Se pretende que cada versión tenga su propia **etiqueta o tag** y **release** en el repositorio, para tener un control de versiones ordenado, que permita correctamente rastrear versiones específicas del código.

