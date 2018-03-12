# HERRAMIENTAS DE DESARROLLO DEL PROYECTO LIBREGOB.

Este repositorio contiene herramientas de desarrollo que facilitan la adopción del proyecto [LibreGOB](http://libregob.org), antes de continuar con las herramientas de desarrollo, por favor, lea la información del [repositorio principal](https://minka.gob.ec/fabricadesoftwarelibre/libregob).

Una vez instaladas las dependiencias y clonado el repositorio principal, procedemos a bifurcar el repositorio y lo clonamos en nuestro equipo local, de preferencia, debemos usar el protocolo https y dentro del directorio `~/Repositorios/fabricadesoftwarelibre` que creamos anteriormente.


```
foo@bar:~$ cd ~/Repositorios/fabricadesoftwarelibre
foo@bar:~$ git clone https://minka.gob.ec/suusuariodeminka/libregob-desarrollo.git
```

Y agregamos el repositorio upstream para poder mantenernos actualizados.

```
foo@bar:~$ cd libregob-desarrollo
foo@bar:~$ git remote add upstream https://minka.gob.ec/fabricadesoftwarelibre/libregob-desarrollo.git
```

Si hemos seguido las instrucciones para clonar el repositorio LibreGOB al pie de la letra, podrémos iniciar nuestro entorno de desarrollo con el comando docker-compose, este comando lo debemos ejecutar dentro de la carpeta librebog-desarrollo:

```
foo@bar:~$ docker-compose -f desarrollo.yml up
```

Podrémos acceder a nuestra instancia local de LibreGOB desde el navegador, en la dirección `localhost:8069`, la contraseña de administración es `libregob`.

Si hemos decidido clonar el repositorio en una carpeta distinta, deberemos edidar el archivo `desarrollo.yml` y deberemos modificar la ruta de los volúmenes del servicio `libregob` para que coincida con nuestra ruta.

Al terminar, deberemos cerrar nuestro servicio con las teclas Ctrl+C y/o terminarlo completamente con el comando docker-compose:

```
foo@bar:~$ docker-compose -f desarrollo.yml down
```
