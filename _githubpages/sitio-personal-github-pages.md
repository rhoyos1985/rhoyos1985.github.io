---
autor: "Richard Hoyos"
layout: post
title: "Creando un Sitio Personal en GitHub - GitHub-Pages"
date: 2017-11-19
description:  "Una guía paso a paso de como crear una pagina personal en github."
image: /assets/images/githubpages/gpindex.png
---

Esta guía muestra de manera sencilla la forma en la que se puede crear una página personal usando GitHub Pages. Supone que sabes un poco sobre control de versión, Git y Github. Usaremos un poco de Markdown de una forma básica no es necesario ser un experto. La idea con esta guía es aprender haciendo; el código utilizado en esta guía quedara disponible en [este](https://github.com/hypnostec/hypnostec.github.io/archive/master.zip) repositorio de GitHub.

### GitHub Pages

Github Pages permite alojar sitios web estáticos de forma gratuita, permite alojar páginas personales, de organización o de proyectos desde un repositorio de GitHub.
Con GitHub Pages los archivos cuyo contenido son HTML o Markdown se pueden ver como cualquier otro sitio web. Podemos crear y publicar páginas de GitHub en línea de manera muy sencilla ya que GitHub viene con un potente generador de sitios estáticos llamado Jekyll del cual hablaremos en el siguiente post.

### Iniciando con GitHub Pages

- Crea el repositorio de tu proyecto. Ingresa a tu cuenta de GitHub y presiona click en **New repository** de tu página principal.

  ![Image](/assets/images/githubpages/newrepository.png)

- Indicamos el nombre del repositorio `username.github.io`, reemplace `username` por el nombre de usuario de GitHub. Seleccionamos la opción **Initialize this repository with a README** crear el archivo `README` en el repositorio.

  ![Image](/assets/images/githubpages/newname.png)

- Cree una página index.html seleccionando la opción **Create new file** que aparece del lado derecho de la pantalla y escribiendo el nombre en el input que aparece al lado del `username`.

  ![Image](/assets/images/githubpages/newfile.png)
  ![Image](/assets/images/githubpages/indexhtml.png)

    Dentro de la página coloque el siguiente código:

       <!DOCTYPE html>
        <html>
            <head>
                <title>hypnostec.github.io</title>
            </head>
            <body>
               <p>Hola mundo!</p>
            </body>
        </html>

- Hacemos Commit al archivo index.html. En la parte inferior de la página, agregamos una descripción de los cambios y presionamos el botón **Commit new file** para confirmar el archivo.

 ![Image](/assets/images/githubpages/commit.png)

 ¡Felicitaciones! Terminamos nuestra GitHub Pages. Podemos verla en [http://username.github.io](#)