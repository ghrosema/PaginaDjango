---
layout: default
---

Autor: Rodrigo Sebastián Márquez, Mentor de Programá tu Futuro, Sede CMD.
_Basado en el tutorial de _ [Django Girls](https://argentinaenpython.com/django-girls/gitbook/).

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

![](https://github.com/ghrosema/PaginaDjango/blob/master/docs/assets/IMG/220px-Django_logo.svg.png)

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
