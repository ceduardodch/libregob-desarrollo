# HERRAMIENTAS DE DESARROLLO DEL PROYECTO LIBREGOB.

El desarrollo está diseñado para funcionar en cualquier equipo que permita utilizar una versión de docker superior o igual a 17.6, las pruebas se realizan sobre Ubuntu 16.04, concretamente sobre [Microwatt OS v10](http://planetwatt.com/new/index.php/downloads/). La compatibilidad con entornos Windows o distribuciones distintas no está garantizada y no se receptarán correcciones de errores para estas plataformas.

Usted puede clonar el proyecto directamente o hacer una bifurcación (fork), si desea contribuir al proyecto, recomendamos la bifurcación.

Una vez que hemos bifurcado el proyecto en Minka, procedemos a clonarlo en nuestra computadora local, de preferencia, debemos usar el protocolo https:

`git clone https://minka.gob.ec/suusuariodeminka/libregob-desarrollo.git`

Y agregamos el repositorio upstream para poder mantenernos actualizados.

```
cd libregob-desarrollo
git remote add upstream https://minka.gob.ec/fabricadesoftwarelibre/libregob-desarrollo.git
```

La manera más sencilla de utilizar el proyecto, sin modificaciones, el clonar el proyecto LibreGOB en su directorio home, en la ruta ~/Repositorios/fabricadesoftwarelibre/ puede seguir las instrucciones indicadas en el archivo README del proyecto LibreGOB.

