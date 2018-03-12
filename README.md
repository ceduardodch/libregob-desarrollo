# HERRAMIENTAS DE DESARROLLO DEL PROYECTO LIBREGOB.

Este repositorio contiene herramientas de desarrollo que facilitan la adopción del proyecto [LibreGOB](http://libregob.org), antes de continuar con las herramientas de desarrollo, por favor, lea la información del [repositorio principal](https://minka.gob.ec/fabricadesoftwarelibre/libregob).

Una vez instaladas las dependiencias y clonado el repositorio principal, procedemos a bifurcar el repositorio y lo clonamos en nuestro equipo local, de preferencia, debemos usar el protocolo https y dentro del directorio `~/Repositorios/fabricadesoftwarelibre` que creamos anteriormente.


```console
foo@bar:~$ cd ~/Repositorios/fabricadesoftwarelibre
foo@bar:~$ git clone https://minka.gob.ec/suusuariodeminka/libregob-desarrollo.git
```

Y agregamos el repositorio upstream para poder mantenernos actualizados.

```console
foo@bar:~$ cd libregob-desarrollo
foo@bar:~$ git remote add upstream https://minka.gob.ec/fabricadesoftwarelibre/libregob-desarrollo.git
```

Si hemos seguido las instrucciones para clonar el repositorio LibreGOB al pie de la letra, podrémos iniciar nuestro entorno de desarrollo con el comando docker-compose, este comando lo debemos ejecutar dentro de la carpeta librebog-desarrollo:

```console
foo@bar:~$ docker-compose -f desarrollo.yml up
```

Podrémos acceder a nuestra instancia local de LibreGOB desde el navegador, en la dirección `localhost:8069`, la contraseña de administración es `libregob`.

Si hemos decidido clonar el repositorio en una carpeta distinta, deberemos edidar el archivo `desarrollo.yml` y deberemos modificar la ruta de los volúmenes del servicio `libregob` para que coincida con nuestra ruta.

Al terminar, deberemos cerrar nuestro servicio con las teclas Ctrl+C y/o terminarlo completamente con el comando docker-compose:

```console
foo@bar:~$ docker-compose -f desarrollo.yml down

```

## Depuración (debug).

El proyecto libregob incluye un [depurador](https://minka.gob.ec/fabricadesoftwarelibre/libregob-desarrollo). Cuando usted inicia el servicio con docker-compose, el sistema se conecta automáticamente.

Para el lenguage de programación [Python](https://www.python.org/) se encuentra disponible el depurador [wdb](https://github.com/Kozea/wdb), mismo que podrémos utilizar incluyendo las siguientes líneas en el punto donde deseemos iniciar la depuración:

```python
    import wdb
    wdb.set_trace()
```

O, si deseamos que el depurador inicie automáticamente una instancia de depuración al encontrar una excepción, podemos realizarlo con el siguiente código:

```python
    from wdb import trace
    with trace():
        codigo_a_revisar
        ...
        ...
```

Reiniciamos el servicio `libregob` y ejecutamos la función a depurar. Cuando se inicie una sesión de depuración se abrirá una ventana nueva en el navegador, en la cual usted podrá trabajar.

NOTA: Es posible que en Firefox la sesión de depuración no se cierre automáticamente al terminar, esto es debido a una configuración del navegador, para solucionarlo visite `about:config` y establezca: `dom.allow_scripts_to_close_windows` a `true`
