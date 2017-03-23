---
layout: default
---

Autor: Rodrigo Sebastián Márquez, Mentor de Programá tu Futuro, Sede CMD.
Basado en el tutorial de [Django Girls](https://argentinaenpython.com/django-girls/gitbook/).

# [](#header-1)Índice

- 1  Introducción
- 2  Requerimientos y conocimientos previos
- 3 ¿Por qué un tutorial de un sitio simple en Django?
- 4 GNU/Linux
- 5 Tu Propia página con Django
  - 5,1 Preparando el entorno
  - 5,2 Creando un entorno virtual
  - 5,3 Instalación de Django
  - 5,4 Comenzamos a armar nuestro sitio
  - 5,5 Configuraciones
  - 5,6 Corriendo el servidor
- 6 Objetos y modelos en Django
  - 6,1 Modelo post
  - 6,2 El modelo en la base de datos
- 7 Administrador de django

# [](#header-1)Introducción

![](https://raw.githubusercontent.com/ghrosema/PaginaDjango/master/docs/assets/IMG/220px-Django_logo.svg.png)

Django es un entorno de trabajo (framework en inglés), libre y escrito en el popular lenguaje de
programación Python.

Su funcionamiento nos permite empezar a comprender un concepto muy importante para el
desarrllo de software: el patrón de diseño modelo-vista-controlador.

Django se desarrolló para administrar sitios de noticias pero debido a su versatilidad se transformó
en un framework de propósito general.

[Django en wikipedia](https://es.wikipedia.org/wiki/Django_(framework)).

***

# [](#header-1)Requerimientos y conocimientos previos

*  Alguna instalación GNU/Linux, puede ser una máquina virtual.
*  Conocimientos en instalación de sistemas operativos o virtualización.
*  Manejo del sistema de archivos. Creación de archivos y carpetas. Manejo del árbol de directorios.
*  Concepto de archivo de texto plano y modelo cliente-servidor.

***

# [](#header-1)¿Por qué un tutorial para crear un sitio simple en Django?

La intención de este tutorial es permirtir una aproximación al popular framework. A partir de este
sitio básico se pueden generar sitios a medida. Además es una oportunidad más para conocer el
lenguaje python. Django es ampliamente solicitado en el mercado laboral.

# [](#header-1)GNU/Linux

Para este tutorial emplearemos el sistema operativo GNU/Linux Debian. El sistema respeta las
libertades del usuario y promueve la solidaridad social de las comunidades de usuarios. Puede
utilizarse sin que esto implique el pago o la violación de licencias. Es nuestro deber como
funcionarios públicos utilizar herramientas que estén al alcance de todos los ciudadanos.

# [](#header-1)Tu propio Blog con Django:

## [](#header-2)Preparando el entorno:

El primer paraso para preparar nuestro entorno es instalar la versión correspondiente del lenguaje
Python. Para eso utilizaremos el famoso gestor de paquete de las distribuciones basadas en
GNU/Linux Debian: apt. Lo haremos a través de la terminal y con permisos de administrador:

$ sudo apt-get install python3.5

>La terminal es un prompt o línea de comandos que puede hayarse en el
menú de la mayoría de los escritorios. Allí se ingresan los comandos y al presionar la tecla enter se ejecutan. Será una
herramienta indispensable.
>[Introducción a la línea de comandos por la FLOSS](http://write.flossmanuals.net/introduccion-a-la-linea-de-
comandos/comandante/).
>[Introducción a la línea de comandos de Django Girls](https://argentinaenpython.com/django-girls/gitbook/intro_to_command_line/).

![](https://raw.githubusercontent.com/ghrosema/PaginaDjango/master/docs/assets/IMG/matt-icons_utilities-terminal-300px.png)

Comprobamos que la instalación sea efectiva ejecuntado.

$ python3 --version
python 3.5.1

Siendo la primera línea nuestro comando y la segunda la salida.

## [](#header-2)Preparando el entorno:

Los entornos virtuales son herramientas muy importatentes a la hora de desarrollar aplicaciones
web o a la hora de trabajar con distintas versiones de una o más librerías. Aprenderemos a crear uno
para trabajar con python de forma que nuestro entorno de desarrollo se aisle del resto del sistema.

>Nota: Si no llegas a comprender la necesidad de generar un
entorno virtual deber perdirle a tu mentor que te amplie y
ejemplifique las razones para hacerlo.

![](https://raw.githubusercontent.com/ghrosema/PaginaDjango/master/docs/assets/IMG/alien-city-scene-300px.png)


Instalamos venv

$ sudo apt-get install python3-venv

Crearemos un directorio y nos movemos hacía él:

$ mkdir PaginaDjango
$ cd PaginaDjango

>Recuenda que los sistemas GNU/Linux, así como todos los Unix-like, son sensibles a las
mayúsculas (case sensitive en inglés).

Ahora utilizaremos el módulo venv de python3 y elegiremos un nombre para nuestro entrono:

$ python3 -m venv MiEntorno

Se creará una nueva subcarpeta dentro de la carpeta DjangoBlog llamanda MiEntorno y contendrá
algunas carpetas que permiten el funcionamiento de entorno aislado. Dentro de una de esas carpetas
, ../PaginaDjangoBlog/MiEntorno/bin/ , tenemos el script de activación del entorno virtual. Lo
corremos utilizandpo el comando source:

$ source MiEntorno/bin/activate

Ahora nuestro prompt o símbolo de sistema cambiará y nos indicará el nombre del entrono virtual
entre parentésis (MiEntorno)
Estamos listos para la inslación de Django.

## [](#header-2)Instalación de Django

Cuando activamos el entorno virtual ya estamos en condiciones de instalar versión que necesitemos
de forma aislada del resto del sistema. La intalación se realizará en nuestro entorno virtual. Para ello
utilizaremos el gestor de paquetes “pip”.

(MiEntorno) ~$ pip install django==1.8

## [](#header-2)Comenzamos a armar nuestro sitio

Pana iniciar el proyecto correremos algunos scripts (Python es un lenguaje de scripts)
proporcionanos por Django para generar un esqueleto de directorios y archivos necesarios.

(MiEntorno) ~/DjangoPagina$ django-admin startproject misitio .

>Importante: Tres aspectos a tener en cuenta con el anterior comando. El primero es el entorno
virtual activado. Lo confirmamos observando el prompt de la terminal. El segundo punto es la
carpeta sobre la cual ejecutamos el comando. Nótese que nos econtramos sobre la primera
carpeta que creamos. Y el tercer punto importante es, justamente, el carácter de punto al final
del comando. En los sistemas Unix-like ese es el comodín para indicar que la acción se realize
sobre el directorio en el cual nos encontramos.

Nuestro árbol de directorios debería ser el siguiente:

(MiEntorno) ~/DjangoPagina$ ls
manage.py MiEntorno/ misitio/

## [](#header-2)Configuraciones

Vamos a editar archivos de texto plano. Deberías elegir alguno de muchas opciones disponibles
siendo gedit y leafpad los que funcionan en modo gráfico y es común que estén instalalados por
defecto y nano o vim las opciones modo texto que también suelen estar instaladas por defecto.
Nostros usaremos nano.

(MiEntorno) ~/DjangoPagina$ nano misitio/settings.py

Y dentro de ese archivo modificaremos el parameto TIME_ZONE =’UTC’ por
TIME_ZONE=’America/Argentina/Buenos_Aires/’ . Estamos configurando el uso horario. De más
está decir que si te encuentras en otro lugar o estás desarrollando para otro país deberias verficar
[Base de datos de usos horarios en wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) para encotrar el uso que corresponda.
Hay muchos otros parámetros para modificar. Investiga según tus necesidades.

Vamos a agregar una ruta a los archivos estáticos, por ejemplo los archivos CSS. Agregaremos un
línea al final del archivo con el siguiente parámetro.

STATIC_ROOT = os.path.join(BASE_DIR, 'static')

Y guardamos.

Nuestro sitio necesita una base de datos para gestionar contenidos, usuario, fechas, etc.
Utilizaremos la opción por defecto: sqlite3. Para crear la base de datos ejecutamos

(MiEntorno) ~/DjangoPagina$ python3 manage.py migrate

La salida nos confirma con muchos OK, OK, OK.
Bien. El esqueleto de nuestro sitio está creado. Veamos los resultados.

## [](header-2)Corriendo el servidor

![](https://raw.githubusercontent.com/ghrosema/PaginaDjango/master/docs/assets/IMG/Client-server-model.svg.png)

Nosotros estamos trabajando el lado del servidor de nuestra página. El cliente será un explorador
web que conectará a nuestro servidor y hará la petición. Igual que cuando navegamos por internet
pero todo funcionando local en nuestra computadora.

>Para ampliar los conocimientos sobre el [modelo cliente-servidor](https://es.wikipedia.org/wiki/Cliente-servidor)

Corremos el comando

(MiEntorno) ~/DjangoPagina$ python3 manage.py runserver

La salida nos indicará que nuestro server está a la escucha en la ip y puerto [http://127.0.0.1:8000/](http://127.0.0.1:8000/). Allí nos dirijimos con nuestro navegador.

Debariamos ver algo así:

![](https://raw.githubusercontent.com/ghrosema/PaginaDjango/master/docs/assets/IMG/scrot1.png)

Ya tienes tu sitio Django funcionando. Vamos a agregar algunos contenidos.


# [](#header-1)Objetos y modelos en Django


En el paradigma de la Programación Orientada a Objetos (POO) debemos pensar cada entidad de
nuestra pagina como un objeto con determinadas propiedades y determinadas funcionalidades.

> [Programación Orientada a Objetos en Wikipedia](https://es.wikipedia.org/wiki/Programaci%C3%B3n_orientada_a_objetos)

En nuestro caso, generaremos una o más publicaciones con sus atributos, como son el título, el
autor, la fecha, la hora, etc. y con sus métodos. Por ejemplo “publicar”.

Usaremos el modelo de blog. Para ello crearemos una aplicación separada dentro de nuestra carpeta
principal.

(MiEntorno) ~/DjangoPagina$ python3 manage.py startapp blog

Y se creará la correspondiente carpeta. Debemos indicarle a Django que fue creada y puede
utilizarla. Para ello volvemos a editar settings.py en misitio. Buscamos la línea INSTALLED_APPS y agreamos a ‘blog’. Quedaría así:

INSTALLED_APPS = []
'django.contrib.admin',
'django.contrib.auth',
'django.contrib.contenttypes',
'django.contrib.sessions',
'django.contrib.messages',
'django.contrib.staticfiles',
'blog',

Bien. Al fin es hora de escribir código fuente en python. Te brindamos un modelo que, con un poco
de paciencia, podrás modificar adaptándolo a tus necesidades.

## [](#header-2)Modelo Post

Vamos a modificar el archivo models.py que se encuentra dentro de la carpeta blog.

>Como vamos escribir código fuente es conveniente utilizar algún ide que reconozca la sintaxis de python. Recomendamos editra. [Editra](http://editra.org/) es libre y encuentra en los repositorios de la mayoría de las distribuciones.

Pasamos el código del archivo. Escribe a mano, clona o descarga el proyecto de github pero no copies y pegues. Y si lo hacés y nada funciona comprueba el identado de Python:

```python
from django.db import models
# Create your models here.
from django.utils import timezone
class Post(models.Model):
	author = models.ForeignKey('auth.User')
	title = models.CharField(max_length=200)
	text = models.TextField()
	created_date = models.DateTimeField(default=timezone.now)
	published_date = models.DateTimeField(blank=True, null=True)

	def publish(self):
		self.published_date = timezone.now()
		self.save()
	def __str__(self):
		return self.title
```

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](another-page).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# [](#header-1)Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## [](#header-2)Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### [](#header-3)Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### [](#header-4)Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### [](#header-5)Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### [](#header-6)Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
