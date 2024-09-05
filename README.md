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

## Servidor en el puerto 8000

Modifica el código para que el servidor escuche solo en el puerto 8000 y al
iniciar muestre la información del puerto en el que está escuchando. Lanza el
servidor y verifica que está escuchando enviando una petición GET con curl,
desde otra terminal.

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

## HTML dinámico

Modifica el código para que el servidor regrese un documento HTML que dependa
de la ruta y query string de la petición. Por ejemplo para esta petición en
curl:

```bash
curl http://localhost:8080/proyecto/web-uno?autor=luis
```

El servidor debería dar como respuesta:

```html
<h1>Proyecto: web-uno Autor: luis</h1>
```

## Home Page

Ahora vamos a crear un sitio web dinámico. En lugar de regresar documentos HTML almacenados
en el servidor, vamos a regresar documentos HTML generados en el momento. Como primer paso vamos a
regressar solo la página de inicio. El html de esta página esta en el archivo `home.html`.
El sitio es el home page de una estudiante de la materia de programación web. Modifica el código
del arvhivo para que el servidor regrese el contenido del archivo `home.html` en la ruta `/`.
Si quieres ver el archivo lo puedes abrir dircectamente en un navegador.

Nota: Como nuestro servdor todavía no regresa archivos estáticos, no se puede implementar una hoja
de estilo CSS. Por lo tanto, no te preocupes si la página se ve un poco fea (no es malo y depende de gustos).

En caso de que el usuario solicite una ruta distinta el servidor debe regresar un error 404. Si todavía
no hemos visto como regresar errores HTTP, puedes regresar un documento HTML con un mensaje de error.

Si tu servidor esta funcionando correctamente, al solicitar la ruta `/` con curl deberías ver el contenido.
También puedes abrir un navegador y poner la dirección `http://localhost:8080` en la barra de direcciones.

Si llegaste hasta aquí haz un commit con el mensaje "Home Page".

## Sitio Web Dinámico

Ahora vamos a regresar documentos almacenados en memoria dependiendo del la ruta solicitada.
Si te fijas en el archimo `home.html`, veras que hay varios hipervinculos a distintas rutas.
Dependiendo de la ruta que el usuario solicite, el servidor debe regresar el html correspondiente.
Como ejemplo de la información de un proyecto se incluye el archivo `1.html`.

Una manera sencilla de implementar este sitio sencillo es almacenar el html correspondiente en un diccionario:

```python
contenido = {
    '/': """<html>...</html>""",
    '/proyecto/web-uno': """
<html>
  <h1>Proyecto: web-uno</h1>
</html>""",
    '/proyecto/web-dos': """<html>...</html>""",
    '/proyecto/web-tres': """<html>...</html>""",
}
```

Dependiendo del valor de la ruta solicitada, el servidor debe regresar el contenido correspondiente utilzando
la ruta como la llave en el diccionario.

Debes utilizar la funcionalidad de diccionarios de Python para implementar esta funcionalidad.
Recuerda que en un diccionario puedes almacenar también métodos, por lo que la funcionalidad que
pueded implmentar es muy variada.

Si llegaste hasta aquí haz un commit con el mensaje "Sitio Web Dinámico".
