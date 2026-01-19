
Nuestro proyecto grupal es en base a la idea de una tienda de cosas retro, llamada Retroplay, para poder generar el catalogo de productos y reservarlos, en este examen nos enfocaremos en el html y css del proyecto. Para ordenarnos utilizamos un diagrama de flujo para saber que pagina tenia que redireccionar a que otra tambien usamos un css fuera de la pagina para mantener el codigo limpio y ordenado.


### Funcionalidad y Estilo Visual

Aquí explico un poco las decisiones que tomamos para que la web funcione y se vea bien

#### 1. Arquitectura Técnica (HTML y PHP)

Queríamos que la navegación fuera fluida, así que implementamos varias cosas clave:

- **Manejo de Sesiones:** Usamos `session_start()` de PHP, que es vital para que el carrito no se pierda cuando cambias de página.
- **HTML Semántico:** Intentamos usar las etiquetas correctas (`main`, `section`, `nav`) para que el código sea ordenado y más accesible.
- **Sincronización:** Hicimos un pequeño sistema para conectar el `localStorage` con la sesión de PHP. Básicamente, esto asegura que lo que ves en tu pantalla es lo que realmente está guardado, sin errores raros.

#### 2. Diseño Visual (CSS)

El objetivo principal era que la página se adaptara a todo, desde móviles hasta ordenadores de escritorio.

- **Estilo Retro:** Para darle personalidad, metimos una fuente "pixel art" que encontramos en DaFont.
- **Flexbox:** Lo usamos mucho para alinear cosas, especialmente los iconos del menú y el contenido dentro de las tarjetas de los juegos.
- **Grid y Responsividad:** Esta fue la parte más difícil. Usamos CSS Grid con la propiedad `repeat(auto-fit, minmax(180px, 1fr))`. Esta línea fue la salvación para que los productos se ordenen solos automáticamente según el espacio disponible, sin romper el diseño.

> **Sobre el código:**
> Como seguimos un diseño muy consistente, la mayoría de páginas comparten la misma estructura. Para no repetir código innecesariamente, abajo dejo el ejemplo de `inicio.php` con su CSS, que es donde mejor se aprecian estos detalles de Grid y Flexbox.

## 3.-Aplicación práctica - 25% de la nota del ejercicio
#### Login
##### Codigo
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LogIn | RetroPlay</title>
    <link rel="stylesheet" href="css/estilo.css">
</head>

<body>
    <h1>RetroPlay</h1>
    <div class="formulario">
        <h2>Inicio de sesión</h2>
        <form method="post" action="../../back/Procesar/procesar.php">
            <!--Al tener "campo" en común se puede aplicar el css a ambas-->
            <div class="usuario campo">
                <input type="text" name="nickname" placeholder="Usuario" required>
            </div>
            <div class="contrasena campo">
                <input type="password" name="contrasena" placeholder="Contraseña" required>
            </div>
            <input type="hidden" name="accion" value="login">
            <input type="submit" value="Entrar">
            <div class="recordar">¿No tienes cuenta?</div>
            <div class="registrarse">
                <!--Los dos puntos en la ruta es para que suba una carpeta(explicado con perplexity)-->
                <a href="../registro/registro.html">Crear una cuenta</a>
            </div>
        </form>
</body>

</html>
```
##### CSS
```css

/*--FUENTES DE TEXTO--*/
@font-face {
    font-family: "titulo" ;
    src: url("fonts/04B_30__.TTF");
}
@font-face {
    font-family: "negrita" ;
    src: url("fonts/ari-w9500-bold.ttf");
}
@font-face {
    font-family: "normal" ;
    src: url("fonts/ari-w9500.ttf");
}

body{
    /*imagen de fondo*/
    background-image: url(img/espacio.gif);
    background-size: cover;
    
    font-family: "normal";
    margin: 0;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.recordar{font-family: "negrita";}
h1{
    font-family: "titulo";
    font-size: 50px;
    text-align: center;
    margin-bottom: 20px;
    /*Degradado*/
    background: linear-gradient(to right, #1df1fd,#e910ee,#532c85);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
}
h2{
    font-family: "negrita";
    font-size: 30px;
}
/*--FORMULARIO--*/
.formulario{
    background: white;
    width: 300px;        /* o el tamaño que quieras */
    padding: 20px;
    border-radius: 8px;
    text-align: center;
    /*Sombreado*/
    box-shadow: 0 4px 10px  rgba(43, 17, 79, 0.6);
}
.campo input{
    margin-bottom: 12px;
    height: 40px;
    border-radius: 20px;
    border: none;
    background: rgb(232, 224, 248);
    font-size: 16px;
    width: 100%; 
}/* "%" hace que ocupe x porcentaje en base a lo que ocupa el formulario*/
input{
    font-family: "normal";
    height: 30px;
    width: 50%;
    border-radius: 12px;
    margin-bottom: 25px;
}
.campo input::placeholder{text-align: center;color:rgb(179, 151, 232);}

```
#### Registro
##### Codigo
```html
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RetroPlay | Registro</title>
    <link rel="stylesheet" href="css/estilo.css">
</head>

<body>
    <h1>RetroPlay</h1>
    <div class="formulario">
        <h2>Crear una cuenta</h2>
        <form method="post" action="../../back/Procesar/procesar.php">
            <!--Al tener "campo" en común se puede aplicar el css a ambas-->
            <div class="nickname campo">
                <input type="text" name="nickname" placeholder="Usuario" required>
            </div>
            <div class="contrasena campo">
                <input type="password" name="contrasena" placeholder="Contraseña" required>
            </div>
            <div class="correo campo">
                <input type="text" name="correo" placeholder="Correo" required>
            </div>
            <div class="telefono campo">
                <input type="text" name="telefono" placeholder="Teléfono" required>
            </div>
            <input type="hidden" name="accion" value="registro">
            <input type="submit" value="Insertar">
        </form>
</body>

</html>
```
##### CSS
```css
h1 {
    color: blue
}
@font-face {
  font-family: "negrita"; /*Nombrar la fuente para usarla*/
  src: url(../css/fonts/ari-w9500-bold.ttf);/*QUÉ fuente*/
}
@font-face {
  font-family: "fina";
  src: url(../css/fonts/ari-w9500.ttf);
}
/*--FUENTES DE TEXTO--*/
@font-face {
    font-family: "titulo";
    src: url("fonts/04B_30__.TTF");
}

@font-face {
    font-family: "negrita";
    src: url("fonts/ari-w9500-bold.ttf");
}

@font-face {
    font-family: "normal";
    src: url("fonts/ari-w9500.ttf");
}

body {
    /*imagen de fondo*/
    background-image: url(img/espacio.gif);
    background-size: cover;

    font-family: "normal";
    margin: 0;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.recordar {
    font-family: "negrita";
}

h1 {
    font-family: "titulo";
    font-size: 50px;
    text-align: center;
    margin-bottom: 20px;
    /*Degradado*/
    background: linear-gradient(to right, #1df1fd, #e910ee, #532c85);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
}

h2 {
    font-family: "negrita";
    font-size: 30px;
}

/*--FORMULARIO--*/
.formulario {
    background: white;
    width: 300px;
    /* o el tamaño que quieras */
    padding: 20px;
    border-radius: 8px;
    text-align: center;
    /*Sombreado*/
    box-shadow: 0 4px 10px rgba(43, 17, 79, 0.6);
}

.campo input {
    margin-bottom: 12px;
    height: 40px;
    border-radius: 20px;
    border: none;
    background: rgb(232, 224, 248);
    font-size: 16px;
    width: 100%;
}

/* "%" hace que ocupe x porcentaje en base a lo que ocupa el formulario*/
input {
    font-family: "normal";
    height: 30px;
    width: 50%;
    border-radius: 12px;
    margin-bottom: 25px;
}

.campo input::placeholder {
    text-align: center;
    color: rgb(179, 151, 232);
}
```
#### Inicio
##### Codigo
```php
<?php
session_start();
// Incluir el archivo de conexión a la base de datos.
include '../../back/Conexion_BD/conexion.php';

// Capturar mensaje flash (si existe) y eliminarlo de la sesión.
$flash = '';
if (isset($_SESSION['flash'])) {
  $flash = $_SESSION['flash'];
  unset($_SESSION['flash']);
}

// VERIFICACIÓN DE CONEXIÓN
// Verificamos si la variable $conexion existe y es válida.
if (!isset($conexion) || !$conexion) {
  echo '<h2 style="color:red">Error: no se pudo conectar a la base de datos.</h2>';
  // Si el modo debug está activo, mostramos el error específico de MySQL.
  if (isset($_GET['debug'])) {
    echo '<pre style="color:red">' . htmlspecialchars(mysqli_connect_error()) . '</pre>';
  }
  echo '</body></html>';
  // Detenemos la ejecución si no hay base de datos.
  exit;
}
?>
<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>RetroPlay | Inicio</title>
  <link rel="stylesheet" href="css/estilo.css">
</head>

<body>
  <!-- Navegación -->
  <nav>
    <a href="../inicio/inicio.php">
      <img src="css/img/productos.png" alt="Acceso a mi cuenta">
    </a>
    <a href="../mi_cuenta/mi_cuenta.php">
      <img src="css/img/mi_cuenta.png" alt="Acceso a mi cuenta">
    </a>
    <a href="../mis_reservas/reservas.php">
      <img src="css/img/reservas.png" alt="Ver reservas">
    </a>
    <a href="../carrito/carrito.php">
      <img src="css/img/carrito.png" alt="Ver carrito de compras">
    </a>
  </nav>

  <?php if (!empty($flash)) { echo "<div id='flash' style='position:fixed;right:20px;top:20px;background:#333;color:#fff;padding:10px;border-radius:6px;z-index:9999'>" . htmlspecialchars($flash) . "</div><script>setTimeout(()=>{var e=document.getElementById('flash'); if(e) e.remove();},2000);</script>"; } ?>

  <!-- Contenido principal -->
  <main>
    <h2>Videojuegos</h2>
    <section id="videojuegos">
      <?php
      // SECCIÓN DE VIDEOJUEGOS
      
      // Consulta SQL para seleccionar todos los productos donde la categoría sea 'videojuego'.
      // LOWER() convierte la categoría a minúsculas para evitar problemas de mayúsculas/minúsculas.
      $sql_v = "SELECT * FROM producto WHERE LOWER(categoria) = 'videojuego'";

      // Ejecutar la consulta contra la base de datos.
      $res_v = mysqli_query($conexion, $sql_v);

      // Verificar si la consulta falló.
      if (!$res_v) {
        if (isset($_GET['debug'])) {
          echo "<p style='color:red'>Error consulta videojuegos: " . htmlspecialchars(mysqli_error($conexion)) . "</p>";
        }
      } else {
        // Verificar si no se encontraron productos.
        if (mysqli_num_rows($res_v) === 0 && isset($_GET['debug'])) {
          echo "<p style='color:orange'>Aviso: no se encontraron videojuegos.</p>";
        }

        // Bucle while: recorre cada fila devuelta por la base de datos.
        while ($p = mysqli_fetch_assoc($res_v)) {

          // Lógica para determinar la imagen del producto.
          // Si el campo 'imagen' no está vacío, usamos ese nombre.
          $filename = isset($p['imagen']) && trim($p['imagen']) !== '' ? basename($p['imagen']) : '';

          if ($filename !== '') {
            $img_path = "css/img/videojuegos/{$filename}";
            // Verificamos si el archivo de imagen realmente existe en el servidor.
            if (!file_exists(__DIR__ . '/' . $img_path)) {
              if (isset($_GET['debug'])) {
                echo "<p style='color:orange'>Aviso: imagen no encontrada: " . htmlspecialchars($img_path) . "</p>";
              }
              // Imagen por defecto si no existe el archivo.
              $img_path = 'css/img/videojuegos/nintendogs.jpg';
            }
          } else {
            // Imagen por defecto si no hay nombre de imagen en la BD.
            $img_path = 'css/img/videojuegos/nintendogs.jpg';
          }

          // Renderizar el HTML de cada artículo (producto).
          echo "<article>";
          // Mostramos la imagen del producto.
          echo "<img src=\"{$img_path}\" alt=\"" . htmlspecialchars($p['titulo']) . "\">";
          // Mostramos el título.
          echo "<h3>" . htmlspecialchars($p['titulo']) . "</h3>";
          echo "<h4>Disponibilidad</h4>";
          // Mostramos el precio.
          echo "<p>" . htmlspecialchars($p['precio']) . " por semana</p>";
          // Botón de 'Añadir al carrito' con atributos data-* para que JavaScript los lea.
          echo '<a href="#" class="add-to-cart" data-id="' . htmlspecialchars($p['id'], ENT_QUOTES) . '" data-title="' . htmlspecialchars($p['titulo'], ENT_QUOTES) . '" data-price="' . htmlspecialchars($p['precio'], ENT_QUOTES) . '" data-img="' . htmlspecialchars($img_path, ENT_QUOTES) . '">Añadir al carrito</a>';
          echo "</article>";
        }
      }
      ?>
    </section>

    <h2>Consolas</h2>
    <section id="consolas">
      <?php

      // SECCIÓN DE CONSOLAS

      // Consulta SQL para seleccionar consolas.
      $sql_c = "SELECT * FROM producto WHERE LOWER(categoria) = 'consola'";

      // Ejecutar consulta.
      $res_c = mysqli_query($conexion, $sql_c);

      // Comprobar errores.
      if (!$res_c) {
        if (isset($_GET['debug'])) {
          echo "<p style='color:red'>Error consulta consolas: " . htmlspecialchars(mysqli_error($conexion)) . "</p>";
        }
      } else {
        // Comprobar si está vacío.
        if (mysqli_num_rows($res_c) === 0 && isset($_GET['debug'])) {
          echo "<p style='color:orange'>Aviso: no se encontraron consolas.</p>";
        }

        // Recorrer los resultados.
        while ($p = mysqli_fetch_assoc($res_c)) {
          // Lógica de imagen (similar a videojuegos pero buscando en carpeta consolas).
          $filename = isset($p['imagen']) && trim($p['imagen']) !== '' ? basename($p['imagen']) : '';

          if ($filename !== '') {
            $img_path = "css/img/consolas/{$filename}";
            // Verificación de existencia del archivo.
            if (!file_exists(__DIR__ . '/' . $img_path)) {
              if (isset($_GET['debug'])) {
                echo "<p style='color:orange'>Aviso: imagen no encontrada: " . htmlspecialchars($img_path) . "</p>";
              }
              $img_path = 'css/img/nintendogs.jpg'; // Imagen fallback (puede que quieras cambiarla a una genérica de consola)
            }
          } else {
            $img_path = 'css/img/nintendogs.jpg';
          }

          // Renderizar HTML.
          echo "<article>";
          echo "<img src=\"{$img_path}\" alt=\"" . htmlspecialchars($p['titulo']) . "\">";
          echo "<h3>" . htmlspecialchars($p['titulo']) . "</h3>";
          echo "<h4>Disponibilidad</h4>";
          echo "<p>" . htmlspecialchars($p['precio']) . " por semana</p>";
          // Botón 'Añadir al carrito'.
          echo '<a href="#" class="add-to-cart" data-id="' . htmlspecialchars($p['id'], ENT_QUOTES) . '" data-title="' . htmlspecialchars($p['titulo'], ENT_QUOTES) . '" data-price="' . htmlspecialchars($p['precio'], ENT_QUOTES) . '" data-img="' . htmlspecialchars($img_path, ENT_QUOTES) . '">Añadir al carrito</a>';
          echo "</article>";
        }
      }
      ?>
    </section>
  </main>

  <script>
    // Añadir al carrito: guarda producto en localStorage y muestra notificación (sin redirigir)
    function showToast(msg) {//mensaje flotante
      var existing = document.getElementById('copilot-toast');
      if (existing) { clearTimeout(existing._timeout); existing.remove(); }
      var d = document.createElement('div'); d.id = 'copilot-toast'; d.textContent = msg;
      d.style.position = 'fixed'; d.style.right = '20px'; d.style.top = '20px'; d.style.background = '#333'; d.style.color = '#fff'; d.style.padding = '10px 14px'; d.style.borderRadius = '6px'; d.style.boxShadow = '0 2px 8px rgba(0,0,0,0.2)'; d.style.zIndex = 9999; d.style.opacity = 1; d.style.transition = 'opacity 0.3s';
      document.body.appendChild(d);
      d._timeout = setTimeout(function () { d.style.opacity = '0'; setTimeout(function () { if (d.parentNode) d.parentNode.removeChild(d); }, 300); }, 2000);
    }

    document.addEventListener('click', function (e) {
      if (e.target.matches('.add-to-cart')) {// si clicka en el carrito hace:
        e.preventDefault();
        var el = e.target;
        var product = {
          id: el.dataset.id,
          title: el.dataset.title,
          price: parseFloat((el.dataset.price || '').replace(',', '.')) || 0,
          img: el.dataset.img,
          qty: 1
        };
        var cart = JSON.parse(localStorage.getItem('cart') || '[]');
        var existing = cart.find(function (it) { return it.id === product.id; });
        if (existing) { existing.qty = (existing.qty || 1) + 1; }
        else { cart.push(product); }
        localStorage.setItem('cart', JSON.stringify(cart));
        showToast('Producto añadido al carrito');
      }
    });
  </script>

</body>

</html>
```
##### Codigo CSS
```css
@font-face {
  font-family: "negrita";
  src: url(../css/fonts/ari-w9500-bold.ttf);
}
@font-face {
  font-family: "fina";
  src: url(../css/fonts/ari-w9500.ttf);
}

/*Elimina los márgenes y rellenos por defecto*/
html, body {
  width: 100%;/*Hace que la web ocupe  todo el ancho*/
  margin: 0;
  padding: 0;
  font-family: "fina";
}

/* Estructura general */
body {
  flex-direction: column;
  min-height: 100vh;/*Obliga al cuerpo a medir el 100% de la altura de la ventana*/
}
h2{text-align: center;font-family: "negrita";}

/* NAVEGACIÓN */
nav {
  height: 80px;
  padding: 0 30px;
  background: #7d50a1;

  display: flex;/*Modo flexible*/
  justify-content: flex-end;/*Empuja iconos a derecha*/
  align-items: center;/*Centra iconos en vertical*/
  gap: 20px; /*Espacio entre elementos*/

  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);/*Sombreado suave hacia abajo*/
}

/* "ENLACES" NAVEGACIÓN */
nav a {
  width: 48px;
  height: 48px;

  display: flex;/*Centrar el icono en el cuadrado */
  justify-content: center;
  align-items: center;

  border-radius: 10px;/*redondeo bordes*/
  background: rgba(255, 255, 255, 0.15);/***CAMBIAR COLOR????***/

  transition: background 0.25s, transform 0.2s;/*Hace la transición más lenta*/
}

nav a:hover {/*CUANDO PASAS EL RATÓN POR ENCIMA HACE:  */
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

/* Imágenes del nav */
nav a img {
  width: 28px;
  height: 28px;
}

/* Contenido principal */
main {
  flex: 1;/*Ocupa el espacio q sobra*/
  padding: 30px;
  background: #d9c3f5;
  color: #333;
  overflow-y: auto;

  display: flex;
  flex-direction: column;/*Organiza las secciones una debajo de otra*/
  gap: 40px;/*Separación entre videojuegos y consolas*/
}

/* Grids de productos */
/*Esto va a hacer q se vea bien en móvil y pc*/
section {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 20px;
}

/* Tarjeta de producto */
article {
  padding: 10px;
  text-align: center;
  background: #fff;
  border: 1px solid #d0c0e0;
  border-radius: 8px;
}

/* Imágenes de producto */
article img {
  display: block;
  width: 100px;
  height: 100px;
  margin: 0 auto 10px;
  padding: 5px;

  object-fit: contain;
  background: #f0f0f0;
}

/* Botón */
article a {
  display: inline-block;
  margin-top: 5px;
  padding: 8px 12px;

  background: #7d50a1;
  color: #fff;
  text-decoration: none;
  border-radius: 5px;

  transition: background 0.3s;
}

article a:hover {
  background: #63327c;
}

```
#### mi_cuenta
##### Codigo
```php
<?php
// Iniciar el manejo de sesiones. Esto es necesario para acceder a las variables $_SESSION.
session_start();

// Verificar si el usuario NO ha iniciado sesión comprobando si 'user_id' no existe.
if (!isset($_SESSION['user_id'])) {
  // Si no hay sesión activa, redirigir al usuario al formulario de login.
  header('Location: ../login/login.html');
  // Detener la ejecución del script para evitar que se cargue el resto de la página.
  exit;
}

// Incluir el archivo de conexión a la base de datos.
include '../../back/Conexion_BD/conexion.php';

// Obtener id del usuario desde la sesión (como entero)
$id = isset($_SESSION['user_id']) ? intval($_SESSION['user_id']) : 0;

// Consulta simple (estilo alumno)
$sql = "SELECT nickname, correo, telefono FROM usuarios WHERE id = $id";
$res = mysqli_query($conexion, $sql);
if ($res && mysqli_num_rows($res) > 0) {
  $user = mysqli_fetch_assoc($res);
} else {
  $user = ['nickname' => '', 'correo' => '', 'telefono' => ''];
}
?>
<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>RetroPlay | Mi Cuenta</title>
  <link rel="stylesheet" href="css/estilo.css">
</head>

<body>
  <nav>
    <a href="../inicio/inicio.php">
      <img src="css/img/productos.png" alt="Acceso a mi cuenta">
    </a>
    <a href="../mi_cuenta/mi_cuenta.php">
      <img src="css/img/mi_cuenta.png" alt="Acceso a mi cuenta">
    </a>
    <a href="../mis_reservas/reservas.php">
      <img src="css/img/reservas.png" alt="Ver reservas">
    </a>
    <a href="../carrito/carrito.php">
      <img src="css/img/carrito.png" alt="Ver carrito de compras">
    </a>
  </nav>

  <main>
    <h2>Información Personal</h2>
    <section id="datos-personales">

      <article>
        <form method="post" action="../../back/Procesar/procesar.php">
          <label>Usuario
            <input type="text" name="nickname" value="<?= htmlspecialchars($user['nickname']) ?>" required>
          </label>
          <label>Correo
            <input type="email" name="correo" value="<?= htmlspecialchars($user['correo']) ?>" required>
          </label>
          <label>Teléfono
            <input type="text" name="telefono" value="<?= htmlspecialchars($user['telefono']) ?>">
          </label>
          <label>Nueva contraseña (opcional)
            <input type="password" name="new_password" placeholder="Dejar en blanco para mantener">
          </label>
          <input type="hidden" name="accion" value="update_profile">
          <input type="submit" value="Actualizar">
        </form>
        <p><a href="../login/logout.php">Cerrar sesión</a></p>
      </article>

    </section>

  </main>
</body>

</html>
```
##### CSS
```css
@font-face {
  font-family: "negrita"; /*Nombrar la fuente para usarla*/
  src: url(../css/fonts/ari-w9500-bold.ttf);/*QUÉ fuente*/
}
@font-face {
  font-family: "fina";
  src: url(../css/fonts/ari-w9500.ttf);
}

/* Fuente básica por defecto (añadida para quitar Times New Roman) */
html, body {
  width: 100%;
  margin: 0;
  padding: 0;
  font-family: "fina";
}

/* Layout principal */
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Navegación superior */
nav {
  height: 80px;
  padding: 0 30px;
  background: #7d50a1;

  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 20px;

  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
}

/* Enlaces del nav */
nav a {
  width: 48px;
  height: 48px;

  display: flex;
  justify-content: center;
  align-items: center;

  border-radius: 10px;
  background: rgba(255, 255, 255, 0.15);

  transition: background 0.25s, transform 0.2s;
}

nav a:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

/* Iconos del nav */
nav a img {
  width: 28px;
  height: 28px;
}

/* Contenido principal */
main {
  flex: 1;
  padding: 30px;
  background: #d9c3f5;
  color: #333;
  overflow-y: auto;

  display: flex;
  flex-direction: column;
  gap: 40px;
}

/* Grids de productos */
section {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 20px;
}

/* Tarjeta de producto */
article {
  padding: 10px;
  text-align: center;
  background: #fff;
  border: 1px solid #d0c0e0;
  border-radius: 8px;
}

/* Imágenes de producto */
article img {
  display: block;
  width: 100px;
  height: 100px;
  margin: 0 auto 10px;
  padding: 5px;

  object-fit: contain;
  background: #f0f0f0;
}

/* Botón */
article a {
  display: inline-block;
  margin-top: 5px;
  padding: 8px 12px;

  background: #7d50a1;
  color: #fff;
  text-decoration: none;
  border-radius: 5px;

  transition: background 0.3s;
}

article a:hover {
  background: #63327c;
}

/*AÑADIDOS PARA DAR FORMATO AL TEXTO*/
h2 {
  color: #7d50a1;
  margin-bottom: 10px;
  font-family: "negrita";
}

/* Título del producto dentro de la tarjeta */
article h3 {
  font-size: 1.1rem;
  margin: 10px 0 5px 0;
  color: #333;
}

/* Subtítulo (Disponibilidad / Fechas) */
article h4 {
  font-size: 0.9rem;
  font-weight: normal;
  color: #666;
  margin: 0 0 10px 0;
  font-family: "fina";
}

/* Precio / Estado */
article p {
  font-weight: bold;
  color: #7d50a1; /* Morado */
  margin: 0 0 10px 0;
}
```
#### Carrito
##### Codigo
```php
<?php
session_start();
// Cargamos el carrito de la sesión (si existe)
$server_cart = isset($_SESSION['cart']) ? $_SESSION['cart'] : [];
?>
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Carrito | RetroPlay</title>
  <link rel="stylesheet" href="css/estilo.css">
</head>

<body>
    <!-- Navegación -->
  <nav>
    <a href="../inicio/inicio.php">
      <img src="css/img/productos.png" alt="Acceso a mi cuenta">
    </a>
    <a href="../mi_cuenta/mi_cuenta.php">
      <img src="css/img/mi_cuenta.png" alt="Acceso a mi cuenta">
    </a>
    <a href="../mis_reservas/reservas.php">
      <img src="css/img/reservas.png" alt="Ver reservas">
    </a>
    <a href="../carrito/carrito.php">
      <img src="css/img/carrito.png" alt="Ver carrito de compras">
    </a>
  </nav>

  <main>
    <!-- Contenido del carrito -->
    <h2>Tu Carrito</h2>
    <section id="cart-list"></section>
    <div id="cart-footer"><strong>Total: <span id="total">0.00</span> €</strong> <button id="checkout">Reservar</button></div>
  </main>

<script>
var serverCart = <?php echo json_encode($server_cart, JSON_HEX_TAG); ?> || [];

// Mostrar un mensaje simple en la esquina (toast)
function showToast(msg){
  var d = document.createElement('div');
  d.id = 'copilot-toast';
  d.textContent = msg;
  d.style.position = 'fixed'; d.style.right = '20px'; d.style.top = '20px'; d.style.background = '#333'; d.style.color = '#fff'; d.style.padding = '10px 14px'; d.style.borderRadius = '6px'; d.style.zIndex = 9999;
  document.body.appendChild(d);
  setTimeout(function(){ if (d.parentNode) d.parentNode.removeChild(d); }, 2000);
}

// Unir carrito local con carrito del servidor (suma cantidades)
function mergeCarts(local, server){
  var merged = [];
  for (var i = 0; i < local.length; i++) {
    merged.push({ id: local[i].id, title: local[i].title, price: local[i].price, img: local[i].img, qty: local[i].qty || 1 });
  }
  for (var j = 0; j < server.length; j++) {
    var found = false;
    for (var k = 0; k < merged.length; k++) {
      if (merged[k].id == server[j].id) { merged[k].qty = (merged[k].qty || 1) + (server[j].qty || 1); found = true; break; }
    }
    if (!found) merged.push({ id: server[j].id, title: server[j].title, price: server[j].price, img: server[j].img, qty: server[j].qty || 1 });
  }
  return merged;
}

function renderCart(){
  var list = document.getElementById('cart-list');
  var cart = JSON.parse(localStorage.getItem('cart') || '[]');
  if (!cart.length) { list.innerHTML = '<p>El carrito está vacío.</p>'; document.getElementById('total').textContent = '0.00'; return; }
  var html = '';
  var total = 0;
  for (var i = 0; i < cart.length; i++) {
    var item = cart[i];
    var price = parseFloat(String(item.price || '').replace('€','').replace(',','.')) || 0;
    total += price * (item.qty || 1);
    html += '<article><img src="' + (item.img || 'css/img/nintendogs.jpg') + '" alt="' + (item.title||'') + '"><h3>' + (item.title||'') + '</h3><p>' + price + ' € — Cantidad: ' + (item.qty||1) + '</p><a href="#" data-id="' + item.id + '" class="remove">Eliminar</a></article>';
  }
  list.innerHTML = html;
  document.getElementById('total').textContent = total.toFixed(2);
}

function updateCartServer(cart, cb){
  var fd = new FormData(); fd.append('accion','update_cart'); fd.append('cart', JSON.stringify(cart));
  fetch('../../back/Procesar/procesar.php', { method: 'POST', body: fd }).then(function(r){ return r.json(); }).then(function(res){ if (cb) cb(res); }).catch(function(){ if (cb) cb({ success: false }); });
}

// Eventos
document.addEventListener('DOMContentLoaded', function(){
  try {
    var local = JSON.parse(localStorage.getItem('cart') || '[]');
    var merged = mergeCarts(local, serverCart);
    localStorage.setItem('cart', JSON.stringify(merged));
    updateCartServer(merged, function(){ renderCart(); });
  } catch(e) { renderCart(); }

  document.body.addEventListener('click', function(e){
    if (e.target && e.target.className === 'remove'){
      e.preventDefault();
      var id = e.target.getAttribute('data-id');
      var cart = JSON.parse(localStorage.getItem('cart') || '[]');
      var newCart = [];
      for (var i = 0; i < cart.length; i++) { if (cart[i].id != id) newCart.push(cart[i]); }
      localStorage.setItem('cart', JSON.stringify(newCart));
      updateCartServer(newCart, function(){ renderCart(); showToast('Producto eliminado del carrito'); });
    }
  });

  document.getElementById('checkout').addEventListener('click', function(){
    var cart = JSON.parse(localStorage.getItem('cart') || '[]');
    if (!cart.length) { showToast('El carrito está vacío'); return; }
    if (!confirm('¿Confirmar reserva de ' + cart.length + ' productos?')) return;

    var items = [];
    for (var i = 0; i < cart.length; i++) { items.push({ id: cart[i].id, qty: cart[i].qty || 1 }); }

    var fd = new FormData(); fd.append('accion','create_reserva'); fd.append('reservas', JSON.stringify(items));
    fetch('../../back/Procesar/procesar.php', { method: 'POST', body: fd }).then(function(r){ return r.json(); }).then(function(data){
      if (data && data.success) {
        localStorage.setItem('cart','[]');
        updateCartServer([], function(){ showToast('¡Reserva registrada!'); setTimeout(function(){ window.location.href='../mis_reservas/reservas.php?reserved=1'; }, 900); });
      } else { alert('Error al crear reserva: ' + (data && data.error ? data.error : 'Error desconocido')); }
    }).catch(function(){ alert('Error de red. Inténtalo de nuevo.'); });

  });
});
</script>

</body>
</html>
```
##### CSS
```css
/* Importar fuentes */
@font-face {
  font-family: "negrita"; /*Nombrar la fuente para usarla*/
  src: url(../css/fonts/ari-w9500-bold.ttf);/*QUÉ fuente*/
}
@font-face {
  font-family: "fina";
  src: url(../css/fonts/ari-w9500.ttf);
}

/* Reset y Base */
/* "*" aplica a TODOS los elementos de HTML*/
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: "fina";
  display: flex;
  flex-direction: column;
  min-height: 100vh;/*para ocultar el mínimo de */
  color: #333;
}

/* Flex Center Helper (para ahorrar líneas en nav y artículos) */
nav, nav a, article { display: flex; }

/* Navegación */
nav {
  height: 80px; /*altura*/
  padding: 0 30px;
  background: #7d50a1;
  justify-content: flex-end;
  align-items: center;
  gap: 20px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
}

nav a {
  width: 48px;  /*ancho*/
  height: 48px; /*altura*/
  justify-content: center;
  align-items: center;
  border-radius: 10px;
  background: rgba(255,255,255,0.15);
  transition: 0.2s;
}

nav a:hover { background: rgba(255,255,255,0.3); transform: translateY(-2px); }
nav a.active { background: rgba(255,255,255,0.4); border: 1px solid rgba(255,255,255,0.6); }
nav a img { width: 28px; height: 28px; }

/* Contenido Principal */
main {
  flex: 1;
  padding: 30px;
  background: #d9c3f5;
  display: flex;
  flex-direction: column;
  gap: 40px;
  overflow-y: auto;
}

h2 { color: #7d50a1; font-family: "negrita"; font-size: 30px; margin-bottom: 10px; }

section {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 20px;
}

/* Tarjetas de Producto */
article {
  padding: 15px;
  background: #fff;
  border: 1px solid #d0c0e0;
  border-radius: 8px;
  flex-direction: column;
  justify-content: space-between;
  text-align: center;
}

article img {
  width: 100px;
  height: 100px;
  margin: 0 auto 10px;
  object-fit: contain;
  background: #f0f0f0;
  border-radius: 4px;
  padding: 5px;
}

article h3 { font-size: 1.1rem; margin: 5px 0; }
article h4 { font-size: 0.9rem; font-weight: normal; color: #666; margin-bottom: 8px; }
article p { font-weight: bold; color: #7d50a1; font-size: 1.1rem; margin-bottom: 10px; }

/* Botones */
article a, #checkout{
  background: #7d50a1;
  color: #fff;
  border-radius: 5px;
  cursor: pointer;
  transition: 0.3s;
  text-decoration: none;
}

article a {
  display: inline-block;
  padding: 8px 12px;
}

article a:hover, #checkout:hover{
  background: #63327c;
}

/* Footer Carrito */
#cart-footer {
  margin-top: 20px;
  padding: 20px;
  background: #fff;
  border-radius: 10px;
  text-align: right;
  box-shadow: 0 -4px 10px rgba(0,0,0,0.05);
}

#cart-footer strong {
  font-family: "negrita";
  font-size: 25px;
  margin-right: 20px;
}

#checkout {
  border: none;
  padding: 12px 25px;
  font-family: "negrita";
  font-size: 1rem;
}

#checkout:hover{
  transform: scale(1.05);
}

#checkout:active{
  transform: scale(0.95);
}
```
#### mis_reservas
##### Codigo
```php
<?php
session_start();
include '../../back/Conexion_BD/conexion.php';

if (!isset($_SESSION['user_id'])) {
  header('Location: ../login/login.html');
  exit;
}

$uid = intval($_SESSION['user_id']);
$sql = "SELECT id, fecha FROM reservas WHERE usuario_id = $uid ORDER BY fecha DESC";
$res = mysqli_query($conexion, $sql);
?>
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Reservas | RetroPlay</title>
  <link rel="stylesheet" href="css/estilo.css">
</head>
<body>
  <nav>
    <a href="../inicio/inicio.php"><img src="css/img/productos.png" alt="Acceso a mi cuenta"></a>
    <a href="../mi_cuenta/mi_cuenta.php"><img src="css/img/mi_cuenta.png" alt="Acceso a mi cuenta"></a>
    <a href="../mis_reservas/reservas.php"><img src="css/img/reservas.png" alt="Ver reservas"></a>
    <a href="../carrito/carrito.php"><img src="css/img/carrito.png" alt="Ver carrito de compras"></a>
  </nav>

  <main>
    <h2>Reservas Activas</h2>

    <section id="reservas-activas">
      <?php
      if (!mysqli_num_rows($res)) {
        echo '<p>No tienes reservas registradas en el servidor.</p>';
      } else {
        while ($r = mysqli_fetch_assoc($res)) {
          echo '<section class="reserva">';
          echo '<h3>Reserva #' . htmlspecialchars($r['id']) . ' — ' . htmlspecialchars($r['fecha']) . '</h3>';
          echo '<div class="items">';

          $rid = intval($r['id']);
          $sql2 = "SELECT p.id, p.titulo, p.precio, p.imagen FROM lineareservas lr JOIN producto p ON lr.producto_id = p.id WHERE lr.reservas_id = $rid";
          $res2 = mysqli_query($conexion, $sql2);

          while ($p = mysqli_fetch_assoc($res2)) {
            $img = !empty($p['imagen']) ? 'css/img/videojuegos/' . htmlspecialchars(basename($p['imagen'])) : 'css/img/nintendogs.jpg';
            echo '<article><img src="' . $img . '" alt="' . htmlspecialchars($p['titulo']) . '"><h4>' . htmlspecialchars($p['titulo']) . '</h4><p>' . htmlspecialchars($p['precio']) . '</p></article>';
          }

          echo '</div></section>';
        }
      }
      ?>
    </section>

  </main>
</body>
</html>
```
##### CSS
```css
@font-face {
  font-family: "negrita"; /*Nombrar la fuente para usarla*/
  src: url(../css/fonts/ari-w9500-bold.ttf);/*QUÉ fuente*/
}
@font-face {
  font-family: "fina";
  src: url(../css/fonts/ari-w9500.ttf);
}

/* Fuente básica por defecto (añadida para quitar Times New Roman) */
html, body {
  width: 100%;
  margin: 0;
  padding: 0;
  font-family: "fina";
}

/* Layout principal */
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Navegación superior */
nav {
  height: 80px;
  padding: 0 30px;
  background: #7d50a1;

  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 20px;

  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
}

/* Enlaces del nav */
nav a {
  width: 48px;
  height: 48px;

  display: flex;
  justify-content: center;
  align-items: center;

  border-radius: 10px;
  background: rgba(255, 255, 255, 0.15);

  transition: background 0.25s, transform 0.2s;
}

nav a:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

/* Iconos del nav */
nav a img {
  width: 28px;
  height: 28px;
}

/* Contenido principal */
main {
  flex: 1;
  padding: 30px;
  background: #d9c3f5;
  color: #333;
  overflow-y: auto;

  display: flex;
  flex-direction: column;
  gap: 40px;
}

/* Grids de productos */
section {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 20px;
}

/* Tarjeta de producto */
article {
  padding: 10px;
  text-align: center;
  background: #fff;
  border: 1px solid #d0c0e0;
  border-radius: 8px;
}

/* Imágenes de producto */
article img {
  display: block;
  width: 100px;
  height: 100px;
  margin: 0 auto 10px;
  padding: 5px;

  object-fit: contain;
  background: #f0f0f0;
}

/* Botón */
article a {
  display: inline-block;
  margin-top: 5px;
  padding: 8px 12px;

  background: #7d50a1;
  color: #fff;
  text-decoration: none;
  border-radius: 5px;

  transition: background 0.3s;
}

article a:hover {
  background: #63327c;
}

/*AÑADIDOS PARA DAR FORMATO AL TEXTO*/
h2 {
  color: #7d50a1;
  margin-bottom: 10px;
  font-family: "negrita";
}

/* Título del producto dentro de la tarjeta */
article h3 {
  font-size: 1.1rem;
  margin: 10px 0 5px 0;
  color: #333;
}

/* Subtítulo (Disponibilidad / Fechas) */
article h4 {
  font-size: 0.9rem;
  font-weight: normal;
  color: #666;
  margin: 0 0 10px 0;
  font-family: "fina";
}

/* Precio / Estado */
article p {
  font-weight: bold;
  color: #7d50a1; /* Morado */
  margin: 0 0 10px 0;
}
```
## 4.-Conclusión breve - 25% de la nota del ejercicio
Este proyecto ha servido para consolidar todo lo aprendido sobre estructura y diseño web. Hemos logrado crear una interfaz retro pero moderna, utilizando HTML para ordenar el contenido y CSS avanzado para asegurar que se adapte a cualquier dispositivo. 