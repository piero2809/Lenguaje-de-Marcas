
En el ambito del desarrollo web el lenguaje XML se utiliza para mantener un orden y jerarquia en la informacion. A diferencia de HTML, no define el diseño de la información sino el como se estructura y a

XML funciona mediante etiquetas personalizadas que cada persona puede definir libremente segun lo que se necesite, Cada etiqueta contiene valores asociados. En este caso se define la estructura básica ``<personaje>`` y con ella atributos como ``<nombre>``,``<edad>``, etc. 


A continuacion se realiza el ejercicio:
```
<?xml version ="1.0" encoding = "UTF-8"?>

<!--En este docuemnto voy a describir a un ser humano-->

    <personaje>
    <!--Aqui irán las etiquetas-->

        <nombre id="propio">Piero Funes</nombre>
        <nombre id="mote">PF</nombre>

        <edad medida="años">20</edad>
        
        <profesion>Programador</profesion>

    </personaje>


</xml>

```
Un error común en el codigo que me pasó al hacer este ejercicio fue que se me olvidó cerrar la etiqueta edad, sin embargo lo detecte y lo corregí, tambien se me olvidó poner el igal luego de id=mote


En resumen, el lenguaje XML permite estructurar los datos de una manera jerarquizada, facilitando la versatilidad entre sistemas. En este ejercicio se describen las caracteristicas de un personaje mediante las etiquetas personalizadas.