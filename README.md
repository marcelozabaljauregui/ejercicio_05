# Ejercicio 05

Investigar que hacen y para que se usan los siguientes comandos dentro de un Dockerfile:

* HEALTHCHECK
* ONBUILD
* VOLUME

Escribir la respuesta en el repositorio personal en ejercicio_05/README.md

## HEALTHCHECK

Instrucción que le permite al docker comprobar el estado de un contenedor para detectar si este sigue funcionando.
Decimos que tiene 3 estados:
* starting
* healthy
* unhealthy

Ejemplo de uso:

´´´
HEALTHCHECK --interval=5m --timeout=3s CMD curl -f http://localhost/ || exit 1
´´´

## ONBUILD

Se utiliza para cuando la imagen es utilizada como base para otra imagen.
La sentencia ONBUILD se ejecutara cuando la imagen que la invoque inmediatamente despues de la sentencia FROM.

Ejemplos:

´´´
ONBUILD ADD . /app/src
ONBUILD RUN /usr/local/bin/python-build --dir /app/src
´´´

## VOLUME

Cuando lo utilizamos dentro del Dockerfile la carpeta es mapeada al directorio por defecto del hosts.
Si se utiliza en el docker run -v esta tendra presedencencia a lo que indica el Dockerfile




