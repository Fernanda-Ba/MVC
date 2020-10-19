
# Metodos HTTP
<p align="center">
    <img src="https://miro.medium.com/max/1018/0*XB5zwH2FMnsOh7tc.png" width="420" height="300"/>
    <img src="https://blog.makeitreal.camp/assets/images/http-messages.jpg" width="420" height="300"/>
</p>

## Introducción

HTTP define un conjunto de métodos de petición para indicar la acción que se desea realizar para un recurso determinado. Aunque estos también pueden ser sustantivos, estos métodos de solicitud a veces son llamados HTTP verbs. Cada uno de ellos implementan una semántica diferente, pero algunas características similares son compartidas por un grupo de ellos.

Los mensajes HTTP, son los medios por los cuales se intercambian datos entre servidores y clientes. Hay dos tipos de mensajes: peticiones, enviadas por el cliente al servidor, para pedir el inicio de una acción; y respuestas, que son la respuesta del servidor. 

Los mensajes HTTP están compuestos de texto, codificado en ASCII, y pueden comprender múltiples líneas.

>https://developer.mozilla.org/es/docs/Web/HTTP/Methods

## Desarrollo

Los metodos de peticion son los siguientes:

<p align="center">
    <img src="https://yosoy.dev/wp-content/uploads/2017/12/HTTP.jpg" width="420" height="300"/>
    
</p>

**1. GET**

Solicita una representación de un recurso específico. Las peticiones que usan el método GET sólo deben recuperar datos.

**Ejemplo de GET**

- GET /index.html HTTP/1.1  
- User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
- Host: www.yosoy.dev
- Accept-Language: es-mx
- Accept-Encoding: gzip, deflate
- Connection: Keep-Alive

A lo que el servidor respondería algo parecido a:

Ejemplo respuesta del servidor:
- HTTP/1.1 200 OK
- Date: Wed, 08 Nov 2017 12:28:53 GMT
- Server: Apache/2.2.14 (Win32)
- Last-Modified: Mon, 22 Jul 2014 19:15:56 GMT
- ETag: "34aa387-d-1568eb00"
- Vary: Authorization,Accept
- Accept-Ranges: bytes
- Content-Length: 88
- Content-Type: text/html
- Connection: Closed

>https://yosoy.dev/peticiones-http-get-post-put-delete-etc/
>https://developer.mozilla.org/es/docs/Web/HTTP/Methods

**2. HEAD**

Pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.

**Ejemoplo de HEAD**

- GET /index.html HTTP/1.1  
- User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
- Host: www.yosoy.dev
- Accept-Language: es-mx
- Accept-Encoding: gzip, deflate
- Connection: Keep-Alive

A lo que el servidor responde:

- HTTP/1.1 200 OK
- Date: Mon, 27 Jul 2009 12:28:53 GMT
- Server: Apache/2.2.14 (Win32)
- Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT
- ETag: "34aa387-d-1568eb00"
- Vary: Authorization,Accept
- Accept-Ranges: bytes
- Content-Length: 88
- Content-Type: text/html
- Connection: Closed

>https://yosoy.dev/peticiones-http-get-post-put-delete-etc/
>https://developer.mozilla.org/es/docs/Web/HTTP/Methods

**3. POST**

Se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.

**Ejemplo de POST**

Se enviará información de formulario al servidor, que será procesada por un process.cgi

- POST /cgi-bin/process.cgi HTTP/1.1
- User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
- Host: www.yosoy.dev
- Content-Type: text/xml; charset=utf-8
- Content-Length: 88
- Accept-Language: es-mx
- Accept-Encoding: gzip, deflate
- Connection: Keep-Alive

>https://yosoy.dev/peticiones-http-get-post-put-delete-etc/
>https://developer.mozilla.org/es/docs/Web/HTTP/Methods

**4. PATCH**

Es utilizado para aplicar modificaciones parciales a un recurso.

**Ejemplo de PATCH**

Petición

- PATCH /file.txt HTTP/1.1 
- Host: www.example.com
- Content-Type: application/example
- If-Match: "e0023aa4e"
- Content-Length: 100

- [description of changes]

Respuesta

- HTTP/1.1 204 No Content
- Content-Location: /file.txt
- ETag: "e0023aa4f"

>https://developer.mozilla.org/es/docs/Web/HTTP/Methods/PATCH
>https://developer.mozilla.org/es/docs/Web/HTTP/Methods

**5. PUT**

Reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.

**Ejemplo de PUT**

Se solicita al servidor que guarde el cuerpo de la entidad dada en index.htm en la raíz del servidor:

- PUT /index.htm HTTP/1.1
- User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
- Host: www.yosoy.dev
- Accept-Language: es-mx
- Connection: Keep-Alive
- Content-type: text/html
- Content-Length: 182

Y el servidor por su parte, responde con lo siguiente al cliente (habiendo ya guardado el cuerpo de la entidad en el archivo index.htm):

- HTTP/1.1 201 Created
- Date: Mon, 27 Nov 2017 12:28:53 GMT
- Server: Apache/2.2.14 (Win32)
- Content-type: text/html
- Content-length: 30
- Connection: Closed

>https://yosoy.dev/peticiones-http-get-post-put-delete-etc/
>https://developer.mozilla.org/es/docs/Web/HTTP/Methods

**6. DELETE**

Borra un recurso en específico

**Ejemplo de DELETE**

Se le solicitará al servidor eliminar el archivo hello.htm en la ruta raíz del servidor:

- DELETE /hello.htm HTTP/1.1
- User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
- Host: www.yosoy.dev
- Accept-Language: es-mx
- Connection: Keep-Alive

El servidor por su parte responderá eliminando dicho archivo y respondiendo al cliente lo siguiente:

- HTTP/1.1 200 OK
- Date: Mon, 27 Jul 2009 12:28:53 GMT
- Server: Apache/2.2.14 (Win32)
- Content-type: text/html
- Content-length: 30
- Connection: Closed
  
 >https://yosoy.dev/peticiones-http-get-post-put-delete-etc/
 >https://developer.mozilla.org/es/docs/Web/HTTP/Methods
 
**7. OPTIONS**

 Es utilizado para describir las opciones de comunicación para el recurso de destino.
 
 **Ejemplo  de OPTIONS**
 
 Se necesita saber cuáles métodos de solicitud soporta el servidor de nuestra profesora, podemos utilizar curl y una solicitud OPTIONS:
 
 - curl -X OPTIONS https://yosoy.dev -i
 
 Para lo cual el servidor podría contestar algo como lo siguiente:

- HTTP/1.1 200 OK
- Date: Wed, 8 Nov 2017 12:28:53 GMT
- Server: Apache/2.2.14 (Win32)
- Allow: GET,HEAD,POST,OPTIONS,TRACE
- Content-Type: httpd/unix-directory

>https://yosoy.dev/peticiones-http-get-post-put-delete-etc
>https://developer.mozilla.org/es/docs/Web/HTTP/Methods

## Mensajes de las peticiones HTTPs

<p align="center">
    <img src="https://mdn.mozillademos.org/files/13827/HTTPMsgStructure2.png" width="420" height="300"/>
    
</p>

Los códigos de estado de respuesta HTTP indican si se ha completado satisfactoriamente una solicitud HTTP específica. Las respuestas se agrupan en cinco clases:

- Respuestas informativas (100–199),
- Respuestas satisfactorias (200–299),
- Redirecciones (300–399),
- Errores de los clientes (400–499),
- y errores de los servidores (500–599).

Los códigos de estado se definen en la sección 10 de RFC 2616. Puedes obtener las especificaciones actualizadas en RFC 7231.

## Respuestas informativas

- 100 Continue

Esta respuesta provisional indica que todo hasta ahora está bien y que el cliente debe continuar con la solicitud o ignorarla si ya está terminada.

<p align="center">

  <img src="https://www.mecambioamac.com/wp-content/uploads/2011/01/Captura-de-pantalla-2011-01-09-a-las-10.25.14.png" width="420" height="300"/>

</p>

- 101 Switching Protocol

Este código se envía en respuesta a un encabezado de solicitud Upgrade por el cliente e indica que el servidor acepta el cambio de protocolo propuesto por el agente de usuario.

<p align="center">

  <img src="https://www.personalcomputerfixes.com/wp-content/uploads/2011/02/101error.png" width="420" height="300"/>

</p>

- 102 Processing (WebDAV)

Este código indica que el servidor ha recibido la solicitud y aún se encuentra procesandola, por lo que no hay respuesta disponible.

<p align="center">

  <img src="https://lh3.googleusercontent.com/proxy/w0jayMKx4p644FyuoIlyaPlbiq_3-w2riN6bhQ5Y_o8odk2KDl9ljzPVSp1asJ6bPe71Q0Lwadh6yy93h5ndefaVnMNKqkSa_ENzxEe-g9qbkRO9_QDM" width="420" height="300"/>

</p>

- 103 Early Hints

Este código de estado está pensado principalmente para ser usado con el encabezado Link, permitiendo que el agente de usuario empiece a pre-cargar recursos mientras el servidor prepara una respuesta.

<p align="center">

  <img src="https://mirillis.com/res/old/gfx/tutorials/errors/mirillis-action-critical-error-103.jpg" width="420" height="300"/>

</p>

**Ejemplos**

1. 2017-04-24T23:51:45.728-0500 I STORAGE [initandlisten] exception in initAndListen: 29 Data directory C:\data\db\ not found., terminating
2.  103 File not open

 Reported by the following functions : Close, Read, Write, 
 Seek, EOf, FilePos, FileSize, Flush, BlockRead, and BlockWrite 
 if the file is not open.
3. Código de error de la API: 100 Descripción del error de la API: Parámetro no válido Mensaje de error: La URL de redirect_uri no está formateada correctamente
4. Proxy o desbloqueador detectado

Desactiva estos servicios y reintenta descargar contenido. (DLS.103)
5. Error 103 de Google Play

Problema: Este error se produce cuando intentas instalar una aplicación que no es compatible con el dispositivo y cuando intentas instalar la aplicación en otro dispositivo compatible arroja el error 103

## Respuestas satisfactorias

GET: El recurso se ha obtenido y se transmite en el cuerpo del mensaje.

HEAD: Los encabezados de entidad están en el cuerpo del mensaje.

PUT o POST: El recurso que describe el resultado de la acción se transmite en el cuerpo del mensaje.

TRACE: El cuerpo del mensaje contiene el mensaje de solicitud recibido por el servidor.

- 200 OK

La solicitud ha tenido éxito. El significado de un éxito varía dependiendo del método HTTP

<p align="center">

  <img src="https://2.bp.blogspot.com/_foq8NUs1mI4/TPm2goSXE3I/AAAAAAAAADU/ZFpfrbFKEQw/s1600/1.PNG" width="420" height="300"/>

</p>

- 201 Created

La solicitud ha tenido éxito y se ha creado un nuevo recurso como resultado de ello. Ésta es típicamente la respuesta enviada después de una petición PUT.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-201_netflix-error-201.png" width="420" height="300"/>

</p>

- 202 Accepted

La solicitud se ha recibido, pero aún no se ha actuado. Es una petición "sin compromiso", lo que significa que no hay manera en HTTP que permite enviar una respuesta asíncrona que indique el resultado del procesamiento de la solicitud. Está pensado para los casos en que otro proceso o servidor maneja la solicitud, o para el procesamiento por lotes.

<p align="center">

  <img src="https://contasic.org/web/image/45114" width="420" height="300"/>

</p>

- 203 Non-Authoritative Information

La petición se ha completado con éxito, pero su contenido no se ha obtenido de la fuente originalmente solicitada, sino que se recoge de una copia local o de un tercero. Excepto esta condición, se debe preferir una respuesta de 200 OK en lugar de esta respuesta.

<p align="center">

  <img src="https://preview.redd.it/qs89pmezq7s41.png?width=1026&format=png&auto=webp&s=56eb5e10b7d851db37b9008da1eebe3718fba2e8" width="420" height="300"/>

</p>

- 204 No Content

La petición se ha completado con éxito pero su respuesta no tiene ningún contenido, aunque los encabezados pueden ser útiles. El agente de usuario puede actualizar sus encabezados en caché para este recurso con los nuevos valores.

<p align="center">

  <img src="https://i.stack.imgur.com/mxtpd.png" width="420" height="300"/>

</p>

- 205 Reset Content

La petición se ha completado con éxito, pero su respuesta no tiene contenidos y además, el agente de usuario tiene que inicializar la página desde la que se realizó la petición, este código es útil por ejemplo para páginas con formularios cuyo contenido debe borrarse después de que el usuario lo envíe.

<p align="center">

  <img src="https://community.adobe.com/legacyfs/online/1776008_Screenshot%202019-06-20%20at%2014.41.12.jpg" width="420" height="300"/>

</p>

- 206 Partial Content

La petición servirá parcialmente el contenido solicitado. Esta característica es utilizada por herramientas de descarga como wget para continuar la transferencia de descargas anteriormente interrumpidas, o para dividir una descarga y procesar las partes simultáneamente.

<p align="center">

  <img src="https://www.errorvault.com/en/images/browser-status-codes_error-206_partial-content.png" width="420" height="300"/>

</p>

- 207 Multi-Status (WebDAV)

Una respuesta Multi-Estado transmite información sobre varios recursos en situaciones en las que varios códigos de estado podrían ser apropiados. El cuerpo de la petición es un mensaje XML.

<p align="center">

  <img src="https://vox.veritas.com/connect/sites/default/files/users/user-3810261/error.JPG" width="420" height="300"/>

</p>

- 208 Multi-Status (WebDAV)

El listado de elementos DAV ya se notificó previamente, por lo que no se van a volver a listar.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-208_tor-error-208.png" width="420" height="300"/>

</p>

- 226 IM Used (HTTP Delta encoding)

El servidor ha cumplido una petición GET para el recurso y la respuesta es una representación del resultado de una o más manipulaciones de instancia aplicadas a la instancia actual.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-226_filezilla-error-226.png" width="420" height="300"/>

</p>

## Redirecciones

- 300 Multiple Choice

Esta solicitud tiene más de una posible respuesta. User-Agent o el usuario debe escoger uno de ellos. No hay forma estandarizada de seleccionar una de las respuestas.

<p align="center">

  <img src="https://www.get-itsolutions.com/wp-content/uploads/2018/02/Sql-server-error-300.png" width="420" height="300"/>

</p>

- 301 Moved Permanently

Este código de respuesta significa que la URI  del recurso solicitado ha sido cambiado. Probablemente una nueva URI sea devuelta en la respuesta.

<p align="center">

  <img src="https://i.ytimg.com/vi/mVj6kaWggqg/maxresdefault.jpg" width="420" height="300"/>

</p>

- 302 Found

Este código de respuesta significa que el recurso de la URI solicitada ha sido cambiado temporalmente. Nuevos cambios en la URI serán agregados en el futuro. Por lo tanto, la misma URI debe ser usada por el cliente en futuras solicitudes.

<p align="center">

  <img src="https://i.stack.imgur.com/b2y4a.jpgg" width="420" height="300"/>

</p>

- 303 See Other

El servidor envía esta respuesta para dirigir al cliente a un nuevo recurso solicitado a otra dirección usando una petición GET.

<p align="center">

  <img src="https://help.autodesk.com/sfdcarticles/img/0EM3A000000Sbyw" width="420" height="300"/>

</p>

- 304 Not Modified

Esta es usada para propósitos de "caché". Le indica al cliente que la respuesta no ha sido modificada. Entonces, el cliente puede continuar usando la misma versión almacenada en su caché.

<p align="center">

  <img src="https://lh3.googleusercontent.com/proxy/GxhKB137qvPuL47GqGzm9D1Sw_rzywx1HlRORK4zxT2YtbWFEEJGIPWeFKQAz0GDkZevVjcWVQVFPAW_LfPjMKRHgOOACDK-zj1CIej6dTO0qLjpa4vddmtjz7vzcC35bzoqdXXBTOCDEEVuro1S1ZP7XTphmKuu4rx1QQAjIWg65vqzqd2A9gvOiiRGpwY1zzrswjm3HTsWNnFqzQRiKhJVfA8wTg" width="420" height="300"/>

</p>

- 305 Use Proxy 

Fue definida en una versión previa de la especificación del protocolo HTTP para indicar que una respuesta solicitada debe ser accedida desde un proxy. Ha quedado obsoleta debido a preocupaciones de seguridad correspondientes a la configuración de un proxy.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-305_avast-error-305.png" width="420" height="300"/>

</p>

- 306 unused

Este código de respuesta ya no es usado más. Actualmente se encuentra reservado. Fue usado en previas versiones de la especificación HTTP1.1.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-306_babylon-error-306.png" width="420" height="300"/>

</p>

- 307 Temporary Redirect

El servidor envía esta respuesta para dirigir al cliente a obtener el recurso solicitado a otra URI con el mismo método que se usó la petición anterior. Tiene la misma semántica que el código de respuesta HTTP 302 Found, con la excepción de que el agente usuario no debe cambiar el método HTTP usado: si un POST fue usado en la primera petición, otro POST debe ser usado en la segunda petición.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-307_avira-error-307.png" width="420" height="300"/>

</p>

- 308 Permanent Redirect

Significa que el recurso ahora se encuentra permanentemente en otra URI, especificada por la respuesta de encabezado HTTP Location:. Tiene la misma semántica que el código de respuesta HTTP 301 Moved Permanently, con la excepción de que el agente usuario no debe cambiar el método HTTP usado: si un POST fue usado en la primera petición, otro POST debe ser usado en la segunda petición.

<p align="center">

  <img src="https://orcz.com/images/thumb/1/16/Esoerror308.jpg/400px-Esoerror308.jpg" width="420" height="300"/>

</p>

## Errores de cliente

- 400 Bad Request

Esta respuesta significa que el servidor no pudo interpretar la solicitud dada una sintaxis inválida.

<p align="center">

  <img src="https://www.profesionalreview.com/wp-content/uploads/2019/10/Error-400-Bad-Request-1-e1570271965709-1280x720.png" width="420" height="300"/>

</p>

- 401 Unauthorized

Es necesario autenticar para obtener la respuesta solicitada. Esta es similar a 403, pero en este caso, la autenticación es posible.

<p align="center">

  <img src="https://ak.picdn.net/shutterstock/videos/1021918498/thumb/1.jpg" width="420" height="300"/>

</p>

- 402 Payment Required

Este código de respuesta está reservado para futuros usos. El objetivo inicial de crear este código fue para ser utilizado en sistemas digitales de pagos. Sin embargo, no está siendo usado actualmente.

<p align="center">

  <img src="https://vra4u.files.wordpress.com/2020/04/error_402.jpeg?w=1108" width="420" height="300"/>

</p>

- 403 Forbidden

El cliente no posee los permisos necesarios para cierto contenido, por lo que el servidor está rechazando otorgar una respuesta apropiada.

<p align="center">

  <img src="https://ayudahosting.online/wp-content/uploads/2018/12/error-403.png" width="420" height="300"/>

</p>

- 404 Not Found

El servidor no pudo encontrar el contenido solicitado. Este código de respuesta es uno de los más famosos dada su alta ocurrencia en la web.

<p align="center">

  <img src="https://assets.prestashop2.com/sites/default/files/styles/blog_750x320/public/wysiwyg/http_code_404_error.jpg?itok=jg7KKK_c" width="420" height="300"/>

</p>

- 405 Method Not Allowed

El método solicitado es conocido por el servidor pero ha sido deshabilitado y no puede ser utilizado. Los dos métodos obligatorios, GET y HEAD, nunca deben ser deshabilitados y no deberían retornar este código de error.

<p align="center">

  <img src="https://i.stack.imgur.com/ZhvVa.png" width="420" height="300"/>

</p>

- 406 Not Acceptable

Esta respuesta es enviada cuando el servidor, después de aplicar una negociación de contenido servidor-impulsado, no encuentra ningún contenido seguido por la criteria dada por el usuario.

<p align="center">

  <img src="https://www.hostingflow.com/wp-content/uploads/406-not-acceptable.jpg" width="420" height="300"/>

</p>

- 407 Proxy Authentication Required

Esto es similar al código 401, pero la autenticación debe estar hecha a partir de un proxy.

<p align="center">

  <img src="https://qph.fs.quoracdn.net/main-qimg-3fcf3951ee483760eecb5f319c13d337.webp" width="420" height="300"/>

</p>

- 408 Request Timeout

Esta respuesta es enviada en una conexión inactiva en algunos servidores, incluso sin alguna petición previa por el cliente. Significa que el servidor quiere desconectar esta 
conexión sin usar. Esta respuesta es muy usada desde algunos navegadores, como Chrome, Firefox 27+, o IE9, usa mecanismos de pre-conexión HTTP para acelerar la navegación. También hay que tener en cuenta que algunos servidores simplemente desconecta la conexión sin enviar este mensaje.

<p align="center">

  <img src="https://miracomosehace.com/wp-content/uploads/2020/08/Navegador-error-408.jpg" width="420" height="300"/>

</p>

- 409 Conflict

Esta respuesta puede ser enviada cuando una petición tiene conflicto con el estado actual del servidor.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-409_pidgin-error-409-conflict.png" width="420" height="300"/>

</p>

- 410 Gone

Esta respuesta puede ser enviada cuando el contenido solicitado ha sido borrado del servidor.

<p align="center">

  <img src="https://www.errorvault.com/en/images/browser-status-codes_error-410_gone.png" width="420" height="300"/>

</p>

- 411 Length Required

El servidor rechaza la petición porque el campo de encabezado Content-Length no esta definido y el servidor lo requiere.

<p align="center">

  <img src="https://www.drupal.org/files/issues/Screenshot_1.png" width="420" height="300"/>

</p>

- 412 Precondition Failed

El cliente ha indicado pre-condiciones en sus encabezados la cual el servidor no cumple.

<p align="center">

  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQs9J9Zsypp63-MzteHps7B0LpkVcdYLbAQ3A&usqp=CAU" width="420" height="300"/>

</p>

- 413 Payload Too Large

La entidad de petición es más larga que los límites definidos por el servidor; el servidor puede cerrar la conexión o retornar un campo de encabezado Retry-After.

<p align="center">

  <img src="https://bobcares.com/wp-content/uploads/413_request_entity_too_large_error.jpg" width="420" height="300"/>

</p>

- 414 URI Too Long

La URI solicitada por el cliente es más larga de lo que el servidor está dispuesto a interpretar.

<p align="center">

  <img src="https://i2.wp.com/deepinthecode.com/wp-content/uploads/2018/11/Error414.png?fit=615%2C336&ssl=1" width="420" height="300"/>

</p>

- 415 Unsupported Media Type

El formato multimedia de los datos solicitados no está soportado por el servidor, por lo cual el servidor rechaza la solicitud.

<p align="center">

  <img src="https://www.sagecity.com/resized-image/__size/320x240/__key/communityserver-discussions-components-files/40/pastedimage1554852184543v1.png" width="420" height="300"/>

</p>

- 416 Requested Range Not Satisfiable

El rango especificado por el campo de encabezado Range en la solicitud no cumple; es posible que el rango está fuera del tamaño de los datos objetivo del URI.

<p align="center">

  <img src="https://www.maccast.com/wp-content/uploads/2006/10/emc_error.jpg" width="420" height="300"/>

</p>

- 417 Expectation Failed

Significa que la expectativa indicada por el campo de encabezado Expect solicitada no puede ser cumplida por el servidor.

<p align="center">

  <img src="https://www.cronicasgeek.com/wp-content/uploads/2018/12/C%C3%B3mo-solucionar-el-error-417-3.jpg" width="420" height="300"/>

</p>

- 418 I'm a teapot

El servidor se rehúsa a intentar hacer café con una tetera.

<p align="center">

  <img src="https://soyunatetera.com/wp-content/uploads/2018/07/error-418-im-a-teapot-650x320.png" width="420" height="300"/>

</p>

- 421 Misdirected Request

La petición fue dirigida a un servidor que no es capaz de producir una respuesta. Esto puede ser enviado por un servidor que no está configurado para producir respuestas por la combinación del esquema y la autoridad que están incluidos en la URI solicitada

<p align="center">

  <img src="https://communities.bentley.com/resized-image.ashx/__size/550x0/__key/communityserver-wikis-components-files/00-00-00-02-44/ora_2D00_29278.png" width="420" height="300"/>

</p>

- 422 Unprocessable Entity (WebDAV)

La petición estaba bien formada pero no se pudo seguir debido a errores de semántica.

<p align="center">

  <img src="https://echecks.zendesk.com/hc/article_attachments/360001310828/blobid0.png" width="420" height="300"/>

</p>

- 423 Locked (WebDAV)

El recurso que está siendo accedido está bloqueado.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-423_error-423-openoffice.png" width="420" height="300"/>

</p>

- 424 Failed Dependency (WebDAV)

La petición falló debido a una falla de una petición previa.

<p align="center">

  <img src="https://ayudaexcel.com/foro/uploads/monthly_2018_04/ERROR424.png.c4cd11de444034860837b742f0551c56.png" width="420" height="300"/>

</p>

- 426 Upgrade Required

El servidor se rehúsa a aplicar la solicitud usando el protocolo actual pero puede estar dispuesto a hacerlo después que el cliente se actualice a un protocolo diferente. El servidor envía un encabezado Upgrade en una respuesta para indicar los protocolos requeridos.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-426_windows-xp-error-code-426.png" width="420" height="300"/>

</p>

- 428 Precondition Required

El servidor origen requiere que la solicitud sea condicional. Tiene la intención de prevenir problemas de 'actualización perdida', donde un cliente OBTIENE un estado del recurso, lo modifica, y lo PONE devuelta al servidor, cuando mientras un tercero ha modificado el estado del servidor, llevando a un conflicto.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-428_windows-8-error-428.png" width="420" height="300"/>

</p>

- 429 Too Many Requests

El usuario ha enviado demasiadas solicitudes en un periodo de tiempo dado.

<p align="center">

  <img src="https://errortools.com/wp-content/uploads/2014/05/run-time-error-429.png" width="420" height="300"/>

</p>

- 431 Request Header Fields Too Large

El servidor no está dispuesto a procesar la solicitud porque los campos de encabezado son demasiado largos. La solicitud PUEDE volver a subirse después de reducir el tamaño de los campos de encabezado solicitados.

<p align="center">

  <img src="https://community.servicenow.com/7937e99edb460414f7fca851ca961994.iix" width="420" height="300"/>

</p>

- 451 Unavailable For Legal Reasons

El usuario solicita un recurso ilegal, como alguna página web censurada por algún gobierno.

<p align="center">

  <img src="https://i0.wp.com/clipset.com/wp-content/uploads/2015/12/freedom-of-speech-error1.png?resize=550%2C268&ssl=1" width="420" height="300"/>

</p>

## Errores de servidor

- 500 Internal Server Error

El servidor ha encontrado una situación que no sabe cómo manejarla.

<p align="center">

  <img src="https://www.redeszone.net/app/uploads-redeszone.net/2019/04/Error-500-Google.jpg" width="420" height="300"/>

</p>

- 501 Not Implemented

El método solicitado no está soportado por el servidor y no puede ser manejado. Los únicos métodos que los servidores requieren soporte (y por lo tanto no deben retornar este código) son GET y HEAD.

<p align="center">

  <img src="https://i.ytimg.com/vi/-osWmEIeisc/maxresdefault.jpg" width="420" height="300"/>

</p>

- 502 Bad Gateway

Esta respuesta de error significa que el servidor, mientras trabaja como una puerta de enlace para obtener una respuesta necesaria para manejar la petición, obtuvo una respuesta inválida.

<p align="center">

  <img src="https://www.webempresa.com/wp-content/uploads/2020/05/error-502.png" width="420" height="300"/>

</p>

- 503 Service Unavailable

El servidor no está listo para manejar la petición. Causas comunes puede ser que el servidor está caído por mantenimiento o está sobrecargado. Hay que tomar en cuenta que junto con esta respuesta, una página usuario-amigable explicando el problema debe ser enviada. Estas respuestas deben ser usadas para condiciones temporales y el encabezado HTTP Retry-After: debería, si es posible, contener el tiempo estimado antes de la recuperación del servicio. El webmaster debe también cuidar los encabezados relacionados al caché que son enviados junto a esta respuesta, ya que estas respuestas de condición temporal deben usualmente no estar en el caché.

<p align="center">

  <img src="https://msegceporticoprodassets.blob.core.windows.net/asset-blobs/4056246_en_2" width="420" height="300"/>

</p>

- 504 Gateway Timeout

Esta respuesta de error es dada cuando el servidor está actuando como una puerta de enlace y no puede obtener una respuesta a tiempo.

<p align="center">

  <img src="https://softwareyapps.com/wp-content/uploads/2017/12/error-504.png" width="420" height="300"/>

</p>

- 505 HTTP Version Not Supported

La versión de HTTP usada en la petición no está soportada por el servidor.

<p align="center">

  <img src="https://www.errorvault.com/en/images/browser-status-codes_error-505_http-version-not-supported.png" width="420" height="300"/>

</p>

- 506 Variant Also Negotiates

El servidor tiene un error de configuración interna: negociación de contenido transparente para la petición resulta en una referencia circular.

<p align="center">

  <img src="https://latecnologiaatualcance.com/wp-content/uploads/error-message-5.jpg" width="420" height="300"/>

</p>

- 507 Insufficient Storage

El servidor tiene un error de configuración interna: la variable de recurso escogida está configurada para acoplar la negociación de contenido transparente misma, y no es por lo tanto un punto final adecuado para el proceso de negociación.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-507_filemaker-error-507.png" width="420" height="300"/>

</p>

- 508 Loop Detected (WebDAV)

El servidor detectó un ciclo infinito mientras procesaba la solicitud.

<p align="center">

  <img src="https://pbs.twimg.com/media/CVQlr3kXIAEPUY4.png" width="420" height="300"/>

</p>

- 510 Not Extended

Extensiones adicionales para la solicitud son requeridas para que el servidor las cumpla.

<p align="center">

  <img src="https://www.errorvault.com/en/images/runtime-errors_error-510_turbotax-error-0510.png" width="420" height="300"/>

</p>

- 511 Network Authentication Required

El código de estado 511 indica que el cliente necesita autenticar para ganar acceso a la red.

<p align="center">

  <img src="https://support.jda.com/servlet/rtaImage?eid=ka4f2000000gZdo&feoid=00N39000004nZLP&refid=0EM39000000N43G" width="420" height="300"/>

</p>

>https://developer.mozilla.org/es/docs/Web/HTTP/Status


## Conclusión

Los metodos HTTP son aquellos con los que el cliente hace  las peticiones sobre el servidor HTTP, es decir, que nos ayudan a especificar la acción que se requiere realizar en un elemento determinado y aunque estas peticiones tienen distintas semánticas, también tienen muchas similitudes en las mismas que evitan que este grupo se extienda demasiado.

Los códigos de estado HTTP transmiten el estado de nuestra página web a Google, evitando problemas derivados con posicionamiento web. 

Es positivo identificar los tipos de error básicos para tener control sobre las acciones hechas en nuestra página. 

Las páginas de error HTTP son personalizables para resultar más amigables y corporativas al usuario final.
