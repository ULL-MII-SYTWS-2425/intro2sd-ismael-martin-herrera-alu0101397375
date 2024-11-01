[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=16598544)

# Práctica 9 - "Introduction to Systems Development" and Static Generators

Ismael Martín Herrera - _alu0101397375@ull.edu.es_

## Índice

1. [Introducción](#introducción)
2. [Desarrollo](#desarrollo)
3. [Conclusión](#conclusión)
4. [Referencias](#referencias)

## Introducción

La práctica 9 de la asignatura tiene como objetivo conocer como funciona un generador de sitios web estáticos, concretamente Jekyll, y desplegar dicho sitio web en los servicios de hosting como GitHub Pages y Netlify.

## Desarrollo

### Primeros pasos

Lo primero de todo ha sido configurar ciertos aspectos del fichero ``_config.yml``: 

*Baseurl*: contiene el nombre del repositorio, en este caso, ``/intro2sd-ismael-martin-herrera-alu0101397375/``. 

![alt text](my_resources/baseurl.png)

*Author*: contiene toda la información sobre el autor del site, tal y como se observa en las imágenes siguientes, además de author también he modificado el atributo ``name`` del fichero ``_config.yml``. 

![alt text](my_resources/author.png)

![alt text](my_resources/name.png)

*Social*: contiene mis redes sociales. 

![alt text](my_resources/social.png)

*Footer*: contiene una serie de links a las redes sociales.

![alt text](my_resources/redes.png)

*Minimal_mistakes_skin*: se cambia a plum para cambiar los colores del sitio web.

![alt text](my_resources/minimal_mistakes.png)

A continuación se muestra una imagen con el resultado tras modificar todos los citados parámetros. 

![alt text](my_resources/resultado_config.png)

Asimismo, a parte de realizar dichas modificaciones, también he eliminando del sitio web ciertos elementos para simplificarlo, y dejando únicamente en la barra de navegación los apartados "Sample posts" y "Collections", además de eliminar todas las colecciones y post que estaban en el repositorio. 

### Pruebas con liquid y markdown

He realizado algunas pruebas con liquid y markdown que pueden observarse mejor en el post "informe" publicado en el sitio web. 

[Informe desplegado](https://ull-mii-sytws-2425.github.io/intro2sd-ismael-martin-herrera-alu0101397375/post%20formats/informe/)


### Creación de una colección

Tal y como se plantea en el enunciado de la práctica he eliminado las colecciones que estaban previamente y he incorporado una personalizada, en este caso son tres post dedicados a lenguajes de programación, y que he llamado "programming". 

![alt text](my_resources/colecction.png)

Para ello he especificado en el atritbuto collections del fichero ``_config.yml`` la nueva colección y he añadido al repositorio un directorio de nombre ``_programming``, en el que se encuentran todos los post de esta nueva colección. Además, también he configurado la nueva colección en la parte de defaults del ``_config.yml``.

![alt text](my_resources/defaults.png)

En la imagen siguiente puede observarse que en el apartado de colecciones del sitio web, se muestran los 3 post que he creado dentro de esta nueva colección. 

![alt text](my_resources/my_collection.png)

### Uso de data files

En el enunciado de la práctica se pide además hacer uso de un data file guardado en el directorio ``_data`` del que obtener ciertos datos, en este caso yo he optado por un fichero de tipo JSON y que guarda la información sobre la población y tipología de cada municipio de Canarias y que se muestra en formato tabla en el post "Municipios". 

### Página de error 404

Además, de todo lo anterior he personalizado también la página de error 404, en este caso incorporando la llamada a una API que muestra fotos de gatos de manera aleatoria, cada vez que se carga esta página. 

```js
---
title: "Page Not Found"
excerpt: "Page not found. Your pixels are in another canvas."
sitemap: false
permalink: /404.html
---

Sorry, but the page you were trying to view does not exist.

<div>
    <div id="imageDiv"></div>

</div>

<script>

    function fetchImage(){
        fetch('https://api.thecatapi.com/v1/images/search?limit=1').then(
            response => response.json()).then(data => {
                console.log(data)
                const imageDiv = document.getElementById('imageDiv')
                const img = document.createElement('img')
                img.src = data[0].url
                img.style.width = '300px'
                imageDiv.appendChild(img)
            })
    }

    fetchImage();

</script>
```

Y cuyo resultado es el siguiente. 

![alt text](my_resources/resultado_404.png)

### Mi página de GitHub

En la práctica se pedía además desarrollar una página persona en GitHub, en este caso, yo ya tenía una página simple que hace uso del repositorio especial público cuyo nombre es el nombre de usuario de GitHub y en este caso lo que he hecho es desplegarlo también en GitHub Pages. 

![alt text](my_resources/mi_perfil.png)

![alt text](my_resources/perfil_ghpages.png)

### Resumen del capítulo

Además de todos los aspectos más técnicos previos, también se pedía realizar un post con un resumen de la lectura que se pide en el enunciado de la práctica. Por lo que en mi caso he creado un nuevo post en el directorio correspondiente con el nombre ``2024-10-24-resumen.md`` y que contiene el siguiente resumen. 


El desarrollo de sistemas engloba una serie de pasos a seguir. En primer lugar, realizar un estudio de factibilidad para analizar si el proyecto puede valer la pena. En segundo lugar, la obtención de los requisitos. Posteriormente, el diseño de la solución, la programación del sistema y el testeo del mismo. Y por último su implementación. Asimismo, también existen un conjunto de disciplinas adicionales que intervienen en el proceso de desarrollo de sistemas. Desde la gestión de proyectos, en la que el “project manager” planifica las tareas y moviliza los recursos necesarios. Pasando por el análisis del negocio, encargado de estudiar la situación del mismo, así como sus necesidades, y que por tanto facilita la obtención de los requisitos del propio sistema. Y por otro lado, la arquitectura de sistemas, la programación, el testeo, la gestión de la configuración del sistema y el control de calidad. 

Actualmente, el desarrollo de sistemas también se ha visto afectado por dos tendencias crecientes, la deslocalización y la subcontratación. Respecto a la deslocalización, muchas organizaciones han visto que en muchas ocasiones utilizar los recursos en determinados países, distintos al de la propia compañía, como pueden ser el caso de India o países post soviéticos, es más barato. Y además, de buena calidad, como es el caso precisamente de India, país en el que su sistema educativo fomenta a los graduados en carreras tecnológicas. Sin embargo, esta deslocalización también lleva implícitas algunas desventajas como pueden ser los problemas de comunicación, entre otras cuestiones por los husos horarios, o el idioma. Y por otro lado, la subcontratación, aunque puede tener su relación con la deslocalización no tiene por qué, e implica que ciertas organizaciones delegan la gestión de sus sistemas de TI a otras empresas, delegando a su vez el riesgo que implican, pero a cambio de un importante presupuesto y de la pérdida de control sobre sus propios sistemas. 


![alt text](my_resources/resumen.png)

### Despliegues

Asimismo, una vez creado el sitio web con Jekyll, tal y como se pide en el enunciado de la práctica he desplegado el mismo mediante dos servicios de hosting gratuitos. Por un lado GitHub pages, para lo que he creado una rama concreta con el nombre ``gh-pages`` y que genera automáticamente una action que despliega el sitio web, en el siguiente [enlace](https://ull-mii-sytws-2425.github.io/intro2sd-ismael-martin-herrera-alu0101397375/).

![alt text](my_resources/despliege_gh-pages.png)

Y por otro lado, he realizado el despliegue en Netlfy [enlace](https://incredible-otter-e4776d.netlify.app/). 

## Referencias


[[1] Enunciado de la práctica](https://ull-mii-sytws.github.io/practicas/intro2sd.html#lectura-introduction-to-systems-development)