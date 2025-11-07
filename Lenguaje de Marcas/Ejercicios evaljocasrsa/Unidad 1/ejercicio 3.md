
En el mundo del desarrollo web, el lenguaje **HTML** permite crear la estructura basica de la pagina web utilizando marcas o etiquetas que organizan el contenido. **CSS** añade estilo visual, controlando colores, fuentes, margenes, etc.

**HTML** funciona usando etiquetas para crear la estructura del texto, mostrando el texto organizado respecto a las etiquetas, luego se agrega colores, tipografía, margenes, y fondo con **CSS** dentro de la etiqueta ``<style>`` 


#### A continuación se realiza el siguiente ejercicio.
```
<!DOCTYPE html>
<html lang ="es">
    <head>
        <meta charset="utf-8">
        <title>Mi titulo</title>
        <style>
            body{background: rgb(147, 218, 218);
            font-family:'Courier New', Courier, monospace;
            color: blue; 
            margin: 20px
            }
            h1{color: brown;
            font-size: 300%;
            }
            p{font-size: 150%;
            }
            ul{background: rgb(161, 160, 237);
            padding: 50px;
            width: 150px;
            }
            li{color: rgb(23, 11, 136);
            }
        </style>
    </head>
    <body>        
        <h1>Mi pagina web</h1>
        <p>Mis hobbies</p>
        <ul>
            <li>Jugar videojuegos</li>
            <li>Jugar Basketball</li>
            <li>Leer</li>
        </ul>
    </body>
</html>
```
Cabe recalcar que es mucho mejor para futuras aplicaciones web, que el apartado ``<style>`` se ponga en un archivo CSS separado.

En resumen, el uso de HTML junto con CSS sirve para la creación de paginas web, mostrando con HTML el como hacer la estructura, y con CSS el estilo de la pagina.