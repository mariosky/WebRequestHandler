# WebRequestHandler

Esta es una actividad de la materia de programación web. El repositorio es una plantilla,
y para empezar la actividad debes crear tu propio repositorio a partir de este.

La actividad consiste en implementar un servidor web utilizando las librerías estándar
de Python. El servidor debe ser capaz de recibir peticiones GET y POST,
y responder las respuestas HTTP que se especifican a continuación.

Para realizar la actividad debes modificar la clase WebRequestHandler
que se encuentra en el archivo web.py de este repositorio.
Cada vez que realices uno de los pasos de la actividad, debes hacer un commit con un mensaje
explicando lo que hiciste.

1. Modifica el código para que el servidor escuche solo en el puerto 8000 y al iniciar muestre
   la información del puerto en el que está escuchando. Lanza el servidor y verifica que está
   escuchando enviando una petición GET con curl, desde otra terminal.

El comando curl debe ser similar a este:

```bash
curl -v http://localhost:8080/
```

Fíjate que estamos usando el flag -v para que curl muestre información detallada de la petición.

Muestra en el mensaje del commit únicamente los siguientes datos:

Del request:

1. El valor del header `Host` y `User-Agent`.
2. El valor de la ruta solicitada.

Del response:

1. El valor del header `Content-Type`.
2. El valor de los headers `Server` y `Date`.

3. Modifica el código para que el servidor regrese un documento HTML que dependa de
   la ruta y query string de la petición. Por ejemplo para esta petición en curl:

```bash
curl http://localhost:8080/proyecto/web-uno?autor=luis
```

Daría como respuesta:

```html
<h1>Proyecto: web-uno Autor: luis</h1>
```
