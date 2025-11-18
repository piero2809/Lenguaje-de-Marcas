
HTML (HyperText Markup Language) es el lenguaje de marcas utilizado para crear y estructurar el contenido de páginas web. Permite definir textos, imágenes, enlaces, listas, secciones, encabezados y otros elementos que el navegador interpreta y muestra al usuario. Normalmente se emplea junto con CSS, que se encarga del diseño visual. Este lenguaje se utiliza en el desarrollo web para construir la estructura base de sitios y aplicaciones, siendo esencial para cualquier proyecto en Internet. 

HTML es un lenguaje que sirve para crear y organizar lo que aparece en una página web. Usa etiquetas, que son como instrucciones que el navegador entiende para mostrar textos, imágenes, listas y cualquier cosa que queramos poner. Cada etiqueta tiene su función y ayuda a que todo quede bien colocado y fácil de leer.

Algunas etiquetas muy comunes son:

``<html>`` → marca el inicio de toda la página

``<head>`` → donde va la información interna, como el título

``<body>`` → todo lo que el usuario puede ver

``<h1>, <h2>…`` → para los títulos y subtítulos

``<p>``→ para los párrafos

``<img>`` → para poner imágenes

``<ul> y <li>`` → para hacer listas

Además de HTML, usamos CSS para darle estilo a la web: colores, tamaños, cómo se colocan los elementos, etc. En el ejemplo del currículum, el CSS sirve para dividir la página en dos columnas y hacer que todo se vea más ordenado y bonito.

Gracias a combinar HTML y CSS, podemos crear páginas simples como un currículum online que sea funcional, claro y visualmente más atractivo.


### A continuación se realizará el ejercicio
```
<!DOCTYPE html>
<html lang="es">

<head>
    <title> Curriculum </title>
    <meta charset="utf-8">
    <style>
        html {
            background: gray;
            font-family: sans-serif;
            font-size: 11px;
        }

        body {
            max-width: 21.59cm;
            background: white;
            margin: auto;
            display: flex;
            padding: 0px;
        }

        #izquierda img {
            width: 100%;
            display: block;
            border-radius: 50%;
        }

        #izquierda {
            flex: 1.4;
            background: #e9e9eb;
            padding: 28px 20px 32px;
            display: flex;
            flex-direction: column;
            gap: 32px;
        }

        #izquierda h3 {
            font-size: 13px;
            letter-spacing: 1.6px;
            margin: 2px 0 8px;
        }

        #izquierda ul {
            margin: 0;
            padding-left: 16px;
        }

        #izquierda li {
            margin: 6px 0;
        }

        #izquierda article * {
            font-size: 14px;
        }


        #derecha {
            flex: 2.2;
            padding: 42px 56px;
            background-color: aliceblue;
        }

        #derecha h1 {
            font-size: 30px;
            letter-spacing: 2px;
            margin: 0 0 4px;
        }

        #derecha h2 {
            font-size: 16px;
            color: #444;
            margin: 0 0 4px;
        }

        #derecha p {
            color: #333;
            margin: 0 14px;
        }


        #derecha article {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        #derecha article img {
            width: 50px;
            height: 50px;
        }

        #derecha article * {
            padding: 2px;
            margin: 0px;
        }

        #derecha li {
            letter-spacing: 1px;
            line-height: 1.6;
        }
    </style>
</head>

<body>
    <section id="izquierda">
        <img src="https://i.pinimg.com/736x/54/bc/65/54bc659557ef880232871d63796d4beb.jpg">
        <article id="sobremi">
            <h3>Sobre Mí</h3>
            <ul>
                <li>Profesional en formación con experiencia en atención al cliente y servicio, desarrollada en empresas
                    del sector retail. Reconocido por la capacidad para trabajar bajo presión, la orientación al detalle
                    y las habilidades de comunicación, con interés en combinar competencias tecnológicas con una
                    atención al cliente de calidad.</li>
            </ul>
        </article>

        <article Id="contacto">
            <h3>Contacto</h3>
            <ul>
                <li>📞 Teléfono: +34 652 210 540</li>
                <li>✉️ Email: pierofl2005@gmail.com</li>
                <li>📍 Ubicación: Burjassot, Valencia(46100)</li>
                <li><a href="https://www.linkedin.com/in/piero-funes-larios-44360a166" target="_blank"
                        rel="noopener">LinkedIn</a></li>

            </ul>
        </article>

    </section>

    <section id="derecha">
        <h1>Piero Funes Larios</h1>
        <h2>Estudiante de Desarrollo de aplicaciones web(DAW)</h2>

        <div id="experiencia">
            <h3>Experiencia profesional</h3>
            <article>
                <img src="https://static.jocarsa.com/logos/teal.png">
                <div class="texto">
                    <h4>Soporte técnico y atención al cliente</h4>
                    <h5>01/2023 - 04/2023 - Servicios industriales KIP EIRL</h5>
                    <p>Implementación de equipos de realidad virtual para proyectos de la empresa. Asistencia en soporte
                        técnico básico y asesoría al cliente en el uso de tecnología.</p>
                </div>
            </article>

            <article>
                <img
                    src="https://media.licdn.com/dms/image/v2/D4D0BAQHjfykQ2ewEPg/company-logo_200_200/company-logo_200_200/0/1707481354058/frutos_secos_liao_sl_logo?e=2147483647&v=beta&t=qWSScCZRK3gNZc-P5GtZ6YrI6Du-l2rYgIfytiwcLCk">
                <div class="texto">
                    <h4>Barista</h4>
                    <h5>08/2025 - 10/2025 - Liaopastel</h5>
                    <p>Atención personalizada, creando una experiencia agradable y cercana para cada cliente. Gestión de
                        pedidos y caja con agilidad y buena vibra.</p>
                </div>
            </article>

            <article>
                <img src="https://www.freepnglogos.com/uploads/coffee-logo-png-22.png">
                <div class="texto">
                    <h4>Barista</h4>
                    <h5>08/24 - 03/2025 - Starbucks</h5>
                    <p>Preparación de bebidas y atención personalizada a clientes en un entorno dinámico. Gestión de
                        pedidos y manejo de caja cumpliendo protocolos de calidad. Trabajo en equipo asegurando un
                        servicio eficiente y cordial.</p>
                </div>
            </article>

        </div>
        <div id="formación">
            <h3>Formación</h3>
            <article>
                <img src="https://portaldefp.com/wp-content/uploads/2023/04/logo-ceac.jpeg">
                <div class="texto">
                    <h4>Desarrollo de aplicaciones web (DAW)</h4>
                    <h5>09/2025 - Actualidad - CEAC FP</h5>

                </div>
            </article>

        </div>

        <div id="competencias_profesionales">
            <h3>Competencias profesionales</h3>
            <ul>
                <li>Microsoft Office (Intermedio)</li>
                <li>Mantenimiento preventivo de computadoras</li>
                <li>Comunicación asertiva</li>
                <li>Orientación al cliente</li>
                <li>Trabajo en equipo</li>
                <li>Adaptabilidad</li>
                <li>Gestión de tiempo</li>
            </ul>
        </div>
        <div id="idiomas">
            <h3>Idiomas</h3>
            <ul>
                <li>Español - Nativo</li>
                <li>Ingles - Intermedio (No certificado)</li>
            </ul>
        </div>

        <div id="voluntariado">
            <h3>Voluntariado</h3>
            <h4>Sonrisas 95 (Voluntariado social)</h4>
            <p>Apoyo en actividades benéficas para comunidades de bajos recursos. Organización de campañas y entrega de
                donaciones.</p>
        </div>
    </section>

</body>

</html>

```

En conclusión, HTML es la base de cualquier página web porque se encarga de toda su estructura y contenido. Con la ayuda de CSS podemos darle estilo y hacer que la web se vea mucho mejor para el usuario. En esta práctica hemos puesto en acción lo aprendido: etiquetas, organización del contenido y diseño básico, para crear un currículum online sencillo pero funcional.