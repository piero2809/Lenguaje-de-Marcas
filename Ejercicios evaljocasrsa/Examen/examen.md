
En el mundo del desarrollo web, los lenguajes de marcas son fundamentales para estructurar y presentar contenido en la web. `HTML` es uno de los lenguajes de marcas más utilizado para crear páginas web, permitiendo a los desarrolladores definir la estructura y el como se presenta la pagina web. A la ves se usa`CSS` para agregar estilos y diseño a las paginas web.

Primero se estructura el documento con las etiquetas basicas de HTML, como `<html>`, `<head>`, y `<body>`. Dentro de Head se estribe el titulo, el charset que usará y se agrega la etiqueta style para agregar estilo a las imagenes y al texto presentado. Luego, dentro del `body` se crea la etiqueta `header` para crear la cabecera de pagina, después, se escribe la etiqueta  `main`, dentro de ella se crean varias etiquetas `article` para cada uno de los proyectos que irían en el pseudoportafolio. Se agrega texto e imagenes dentro de cada `article` para representar cada proyecto. Finalmente, se crea la etiqueta `footer` para agregar un pie de pagina con información de derechos de autor.

```
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <title>Examen</title>
    <style>
        html,
        body {
            background: rgb(92, 88, 148);
            font-family: sans-serif;
        }

        header,
        main,
        footer {
            background: rgb(96, 170, 154);
            padding: 20px;
            width: 800px;
            margin: auto;
            text-align: center;
        }

        main {
            display: grid;
            grid-template-columns: auto auto auto;
            gap: 20px;
        }

        article img {
            width: 200px;
            height: 200px;
        }
    </style>
</head>

<body>
    <header>
        <h1>Portafolio examen</h1>
        <h2>Gestor de proyectos DAM DAW</h2>
        <h3>Piero Funes</h3>
    </header>
    <main>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>
        <article>
            <p>nombre</p>
            <h3>Titulo</h3>
            <p>Descripcion</p>
            <p>Fecha</p>
            <img
                src="https://tse3.mm.bing.net/th/id/OIP.ZDVq-76UPggSR5zN5WGVrwHaHa?cb=ucfimg2ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3">
        </article>

    </main>
    <footer>
        <p>(C) 2025 Piero Funes Larios</p>
    </footer>
</body>

</html>
```

En conclusión, Los lenguajes de marcas como HTML y CSS son herramientas esenciales en el desarrollo de paginas web. HTML permite darle estructura a la informacion y CSS permite darle estilo. Juntos, forman un arma poderosa para crear paginas web atractivas y funcionales.