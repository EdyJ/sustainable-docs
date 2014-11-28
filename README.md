### sustainable-docs

Our notes on making sustainable docs for software projects.

# Winner: **[MkDocs](http://www.mkdocs.org/)**

- Los ficheros se escriben en Markdown.
- Permite extensiones de Markdown tanto oficiales como externas.
- Genera html estático basado en Bootstrap.
- Permite previsualización casi-en-vivo al escribir.
- Apariencia elegante y fácil de configurar.
- La estructura de ficheros puede ir en el propio GIT del objeto a documentar.

Apropiado para un dominio o subdominio propio, ya que va todo estático. Si no hay una integración seamless en Wordpress, usaremos vehiclephysics.com

[Extensiones Markdown incluidas por defecto](https://pythonhosted.org/Markdown/extensions/index.html)

[Extensiones Markdown externas](
https://github.com/waylan/Python-Markdown/wiki/Third-Party-Extensions)

## Instalación de MkDocs

1. Instalar **[Python 2.x 32bits](https://www.python.org/)**. Requiere su carpeta propia para leer y escribir. Para entendernos, Python viene a ser como un NodeJS que ejecuta cosas, instala sus packages, etc.
2. [Instalar pip](https://pip.pypa.io/en/latest/installing.html). Es equivalente al _npm_ de NodeJS.
3. Añadir tanto la carpeta de Python como Python\Scripts al path. pip es un ejecutable, y mkdocs también. Ambos van en Python\Scripts, se ejecutan desde la consola normal de Windows.
4. [Instalar Mkdocs](http://www.mkdocs.org/#installation): **pip install mkdocs**
5. Verificar instalación: **mkdocs help** debe mostrar la ayuda de MkDocs.
6. Seguir el [Getting Started](http://www.mkdocs.org/#installation) para ver cómo empezar.

## Soporte para fórmulas matemáticas de LaTex

**1.** Añadir al fichero mkdocs.yml:

    extra_javascript: ['https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML','js/mathjaxhelper.js']

Crear el fichero js/mathjaxhelper.js y ponerlo en el proyecto. Contenido:

    MathJax.Hub.Config({
        "tex2jax": { inlineMath: [ [ '$', '$' ] ] }
    });

Este helper permite expresiones inline usando $ $. Mathjax ya detecta $$ $$ por defecto.

**2.** Instalar la extensión [python-markdown-mathjax](https://github.com/mayoff/python-markdown-mathjax). Evita que markdown parsee el interior de las fórmulas. Añadir la extensión al fichero mkdocs.yml:

    markdown_extensions: [mathjax]

## Soporte para iconos de Bootstrap / FontAwesome

[Extensión markdown-icons](https://github.com/MadLittleMods/markdown-icons)

    markdown_extensions: [iconfonts(prefix=fa)]

FontAwesome está incluído por defecto. Para usar Glyphicons habría que copiar la fuente en la carpeta fonts del theme y cambiar el prefijo a glyphicons.

## Soporte para barras de progreso

[ProgressBar](http://facelessuser.github.io/PyMdown/Extensions/ProgressBar.html)

## Opciones externas para soporte al cliente

[User Echo](http://userecho.com), ejemplo: foro de soporte para [SublimeText](http://sublimetext.userecho.com/forum/2079-general/)

## Editor para ficheros Markdown

El [SublimeText 3](http://www.sublimetext.com) tiene pintaza.

[Personalización de los colores para sintax highlight](http://stackoverflow.com/a/18091547/2519774)

Para editar los colores, usar [ColorSchemeEditor](https://github.com/bobef/ColorSchemeEditor)
