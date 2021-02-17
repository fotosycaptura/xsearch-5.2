
---
[1. Spanish](#spanish)
[2. English](#english)

---

## Spanish

>Este es un script que encontré hace años, y que lo conservé desde entonces. Al día de hoy, que me puse a buscar información no encontré nada relacionado con el autor o el sitio web. 
Dado que es código libre, lo publico por si a alguien le interesa.
Notar que tanto el correo de contacto como la dirección original no existen. Por si acaso, ya estais advertidos.
Esta es la versión traducida del manual en ingles.

# XSearch 5.2
## Manual del usuario
## Visión General
El script XSearch es un potente motor de búsqueda javascript. Esta versión 5 es una versión mejorada de las versiones anteriores v4.x. Uno de los cambios principales es que no es compatible con los navegadores 3.0. Hay algunos otros cambios menores y algunas cosas se han dejado de lado porque no mucha gente lo usó. Si aún desea la funcionalidad de las versiones anteriores, descargue la versión 4.3 del sitio web dynamic-core.net. Tenga en cuenta que XSearch5 es mucho más rápido y más personalizable que las versiones anteriores.

## Explicación de archivos incluídos.
* db.js
Este archivo contiene la base de datos tal como la utiliza XSearch para buscar.

* manual.htm
Es este archivo que estás leyendo.

* xsearch.css
Un archivo de hoja de estilo en cascada, utilizado para definir el formato del texto en XSearch.

* xsearch-5.2.js
El motor de JavaScript XSearch5.2 (el núcleo) del buscador.

* xsearch-5.2.htm
El archivo html de ejemplo, que le mostrará un motor XSearch5 en funcionamiento.

## Creando la Base de Datos
_ADVERTENCIA: Actualizado para la versión 5.2, el archivo db.js ahora se crea de otra manera, ¡por favor lea!_

Este capítulo explicará cómo puede llenar la base de datos de XSearch con sus propias direcciones URL y palabras clave.
El archivo db.js contiene la definición de la base de datos que necesita XSearch. XSearch se construye utilizando Javascript, esto tiene la ventaja de que todos pueden usarlo sin la necesidad de un cgi-bin u otras opciones del lado del servidor. La desventaja de usar Javascript es que es imposible buscar a través de estructuras de directorios y archivos en el servidor. Así que tendrás que crear la base de datos manualmente para cada página de tu sitio web.

## Entradas 
Cada entrada de la base de datos XSearch (registro) se crea utilizando tres matrices de texto. La primera de estas matrices contendrá un enlace de trabajo al archivo html de destino, la segunda matriz contiene un conjunto de palabras clave y, finalmente, la tercera matriz contiene una descripción de la entrada actual de la base de datos. Xsearch agrega una nueva función llamada add () que puede usar para agregar la información del registro a la base de datos:
> add(url,keywords,description)

Ejemplo:

```
add("<a href='http://www.dynamic-core.net'>dynamic-core.net </a>","grandioso motor de búsqueda dhtml xsearch creado en javascript","Esta es la página principal de dynamic-core.net, incluyendo la página de inicio de XSearch5.0")
```
Como puede ver en el ejemplo anterior, es muy sencillo crear un nuevo registro. 

## Hoja de Estilo de XSearch (CSS)

El archivo xsearch.css contiene los estilos utilizados por el motor XSearch5 para mostrar las diferentes líneas de texto. Al modificar este archivo, puede cambiar el aspecto de cada línea de texto utilizada en el motor XSearch. Esta es una gran mejora con respecto a los antiguos motores XSearch que solo podían cambiar el color de las fuentes.

* h3
Pequeño texto de encabezado utilizado para la línea "mostrando resultados ..." en la parte superior de la página de resultados

* p
Utilizado para la salida de texto normal, como ejemplo, vea la página Sin resultados y luego la línea que dice: "Su búsqueda ... no coincide ..."

* li
Utilizado en la página Sin resultados, para enumerar las opciones para un mejor resultado de búsqueda.

* xtitle
Se utiliza para mostrar el enlace en cada registro de los resultados.

* xresult
Se utiliza para mostrar la descripción de cada registro.

* xlocation
Se utiliza para mostrar el enlace en texto (debajo de la descripción)

* xsmall
Esto se utiliza para el texto de la página "Anterior" y "Siguiente".

## Configuración de parámetros

El archivo db.js contiene algunas variables que deben configurarse para que la búsqueda funcione correctamente.

* searchname
Al igual que con las versiones anteriores de xsearch, esta variable define el nombre de archivo de búsqueda. Este es básicamente el nombre del archivo actual.

* usebannercode
Esta variable también se usó en versiones anteriores, define si desea mostrar el código del banner, configúrelo en verdadero o falso.

* ButtonCode
Esto ha cambiado desde la versión anterior. Xsearch5 no usa una imagen para buscar. Puede poner cualquier código que desee, por ejemplo, si quiere que se vea como las versiones anteriores de xsearch haga esto:

```
ButtonCode = "<img border="0" src="searchbutton.gif">"
```

templateBody() , templateEnd() and bannerCode() para más información sobre estas funciones, lea el artículo: configurando su propio buscador.

Dicho artículo fue escrito para las versiones antiguas de XSearch, pero las funciones, templateBody(), templateEnd() y bannerCode() no ha cambiado.

## Haciéndolo funcionar

Finalmente, tendrá que crear un archivo HTML que vincule el motor XSearch5 y la base de datos de esta manera:
_Advertencia: el orden de inclusión de los dos archivos es muy importante, asegúrese de que el archivo xsearch-5.js esté vinculado primero, y el archivo db.js en segundo lugar. De lo contrario, aparecerán algunos mensajes de error._

```
<html>
<head>
<title>Xsearch 5</title>
<script language="Javascript" src="xsearch-5.2.js"></script>
<script language="Javascript" src="db.js"></script>
<body bgColor="#ffffff">
<script language="Javascript">
    initXsearch()
</script>
</body>
</html>
```

## Información de Contacto

Si tiene alguna pregunta después de este manual, consulte las preguntas frecuentes de XSearch y los artículos de la base de conocimientos (http://www.dynamic-core.net) antes de enviarme un correo. La mayoría de los problemas ya se han explicado en uno de esos archivos. Si aún no puede hacer que funcione, puede enviarme un correo electrónico: <pascal@dynamic-core.net> 

_Last modified 2000-07-20_

---
# English
>This is a script that I found years ago, and have kept it ever since. As of today, when I started looking for information, I did not find anything related to the author or the website.  
I publish it in case anyone is interested.
Note that both the contact email and the original address do not exist. Just in case, you have already been warned. 


# XSearch 5.2
## User manual
## Overview
The XSearch script is a powerfull javascript search engine. This version5 is an improved version of the older v4.x versions. One of the main changes is that it's not compatible with 3.0 browsers. There are some other minor changes and some things have been left out because not many people used it. If you still want the functionality of the previous versions please download version4.3 from the dynamic-core.net website http://www.dynamic-core.net. Note that XSearch5 is much faster, and more customizeable then the older versions.

## Files explained
The following files are supplied with XSearch5:

* db.js
This file contains the database as it is used by XSearch to search through.
* manual.htm
This file you'r reading.
* xsearch.css
A cascading style sheet file, used to define the markup of the text in XSearch.
* xsearch-5.2.js
The XSearch5.2 javascript engine (the core).
* xsearch-5.2.htm
The example html file, that will show you a working XSearch5 engine.

## Creating the Database
_WARNING: Updated for version5.2, the db.js file is now created in another way, please read!_

This chapter will explain how you can fill the XSearch database with your own url's and keywords.

The db.js file contains the definition of the database needed by XSearch. XSearch is build using Javascript, this has the advantage that everybody can use it without the need for a cgi-bin or other server side options. The disadvantage of using Javascript is that it's impossible to search through directory structures and files on the server. So you'll have to create the database manually for every page in your website.

## Entries
Every XSearch database entry (record) is created using three text array's. The first of these arrays will contain a working link to the target html file, the second array contains a set of keywords, and finally the third array contains a description of the current database entry. Xsearch adds a new function called add() you can use this to add the record information to the database:

>add(url,keywords,description)

example:

```
add("<a href='http://www.dynamic-core.net'>dynamic-core.net</a>","great dhtml xsearch javascript search engine","This is the homepage of dynamic-core.net, including the XSearch5.0 homepage")
```

As you can see in the above example, it's very simple to create a new record.

## XSearch CSS style sheet
The xsearch.css file, contains the styles used by the XSearch5 engine to display the different text lines. By modifying this file, you can change the look of every text line used in the XSearch engine. This is a big improvement over the old XSearch engines that could only change the color of the fonts.

* h3
Small header text used for the "showing results ... " line at the top of the results page.
* p
Used for output of normal text, as example see the No results page, and then the line that says: "Your search ... did not match..."
* li
Used on the No results page, to list the options for a better searching-result.
* xtitle
Used to display the link in every record of the results.
* xresult
Used to show the description of every record.
* xlocation
Used to display the link in text (below the description)
* xsmall
This is used for the "Previous" and "Next" page text.
Configuration parameters

The db.js file contains a few variables that need to be set to make the search work correctly.

* searchname
As with the previous xsearch versions, this variable defines the xsearch filename. This is basiclly the current file name.
* usebannercode
This variable was also used in previous versions, it defines if you want to show the banner code, set it to true or false.
* ButtonCode
This has changed from the previous version. Xsearch5 doesn't use an image to search. You can put in any code you want, for example, if you want to make it look like the previous xsearch versions do this:
`ButtonCode = "<img src='searchbutton.gif' border=0>"`
templateBody() , templateEnd() and bannerCode() for more information on these functions, read the article: Setting up your own search engine. That article was written for the older versions of XSearch, but the templateBody(), templateEnd() and bannerCode() workings haven't changed.

## Making it work
Finally you'll have to create a HTML file that links the XSearch5 engine and the database like this:

_Warning: The order of linking the two files is very important, make sure the xsearch-5.js file is linked first, and the db.js file second.. otherwise you'll get some error messages._

```
<html>
<head>
<title>Xsearch 5</title>
<script language="Javascript" src="xsearch-5.2.js"></script>
<script language="Javascript" src="db.js"></script>
<body bgColor="#ffffff">
<script language="Javascript">
    initXsearch()
</script>
</body>
</html>
```

## Contact information
If you have any questions after this manual, please browse through the old XSearch FAQ and knowledge base articles (http://www.dynamic-core.net) before mailing me. Most problems have already been explained in one of those files. If you still can't get it to work you can mail me: <pascal@dynamic-core.net>

_Last modified 2000-07-20_