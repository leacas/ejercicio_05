# ejercicio_05

HEALTHCHECK
Trata sobre la verificación de estado de un contenedor en ejecución. Con este comando 
es posible validar si nuestra aplicación sigue o no funcionando en nuestro contenedor.
 
Ejemplo de uso en un Dockerfile:
 - Agregue esta línea al Dockerfile antes de la última línea (CMD).
	- HEALTHCHECK CMD curl --fail http://localhost/ || exit 1

-----------------------------------------------------------------------------------------------------

ONBUILD
Permite establecer disparadores dentro de una imagen y que los mismos se ejecutan posteriormente, 
cuando la imagen se utilice como base para otra.

Ejemplo de uso en un Dockerfile: 
 - ONBUILD RUN [command]

La ventaja de crear imágenes OnBuild es que nuestro Dockerfile es mucho más simple y se puede reutilizar 
el codigo, por lo tanto mejora los tiempos de compilación.

Las siguientes exepciones no pueden utilizarse:
- ONBUILD FROM
- ONBUILD MAINTAINER
- ONBUILD ONBUILD

-----------------------------------------------------------------------------------------------------
VOLUME
Los volúmenes de Docker se crean y asignan cuando se inician los contenedores. Los volúmenes de datos 
le permiten asignar un directorio de host a un contenedor para compartir datos.

Este mapeo es bidireccional, permite persistir los datos en el host.

El montaje de volúmenes otorga al contenedor acceso completo de lectura y escritura al directorio. 
Puede especificar permisos de solo lectura en el directorio agregando los permisos :ro al montaje.

Ejemplo de uso en un Dockerfile: 
 - VOLUME /myvolume