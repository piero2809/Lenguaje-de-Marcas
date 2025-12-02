XML es un lenguaje diseñado para almacenar y transportar datos de forma estructurada y legible tanto por humanos como por máquinas.
Se utiliza ampliamente en la comunicación entre sistemas, configuración de aplicaciones y almacenamiento de información jerárquica.


Un archivo XML se compone de etiquetas personalizadas que nosotros mismos definimos para describir los datos. Cada etiqueta tiene una apertura y un cierre, y dentro se colocan los valores o más elementos relacionados.

El documento comienza con la línea
`<?xml version="1.0" encoding="UTF-8"?>`,
que indica la versión del formato y la codificación de texto utilizada.

En este caso, el elemento principal es `<persona>`, dentro del cual se agrupan distintos apartados como `<nombre>`, `<telefonos>` o `<emails>`.
Esto permite organizar la información de forma jerárquica, haciendo más fácil su lectura y manipulación.


```
<?xml version="1.0" encoding="UTF-8"?>
<persona>
  <nombre>Piero </nombre>
  <apellido1>Funes</apellido1>
  <apellido2>Larios</apellido2>
  <telefonos>
    <movil>62242525</movil>
    <fijo>96372151</fijo>
  </telefonos>
  <emails>
    <personal>pierofl2005@gmail.com</personal>
    <empresa>piero@jocarsa.com</empresa>
  </emails>
</persona>
'''

Este ejercicio demuestra cómo XML permite organizar información de forma clara y estructurada, manteniendo una relación lógica entre los datos.
Gracias a su flexibilidad, se utiliza ampliamente para intercambiar información entre aplicaciones o almacenar configuraciones de manera universal y comprensible.

