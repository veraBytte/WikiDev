# DISPLAY CSS

## Display Flex

Tambien conocido como FlexBox, facilita en gran medida el tema de organizar los distintos contendores del HTML

La propiedad flex genera que los contenedores, se comporten de manera distinta e incluso hace que los contenedores hijos que tenga un contenedor padre, con la propiedad de "Display Flex" puedan ajustarce de manera distinta.

#### Ejemplo

###### HTML
```
    <main class="container">
    <div class="box box1">
      <p>box1</p>
    </div>
    <div class="box box2">
      <p>box2</p>
    </div>
    <div class="box box3">
      <p>box3</p>
    </div>
    <div class="box box4">
      <p>box4</p>
    </div>
    <div class="box box5">
      <p>box5</p>
    </div>
    <div class="box box6">
      <p>box6</p>
    </div>
  </main>
```
###### CSS
```CSS
    *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
  
html{
  font-size: 62.5%;
}
body{
  font-size: 1.6rem;
}
.container{
  display: flex;
  border: 0.3rem solid black;
}
.box{
  width: 10rem;
  height: 10rem;
}
.box1{
  background-color: blue;
}
.box2{
  background-color: rgb(0, 234, 255);
}
.box3{
  background-color: rgb(255, 0, 208);
}
.box4{
  background-color: rgb(225, 255, 0);
}
.box5{
  background-color: rgb(0, 255, 51);
}
.box6{
  background-color: rgb(255, 0, 0);
}
```
Como podemos observar el codigo esta construido con un contenedor padre "Main .container" Que tiene 6 hijos div con clases .box .box1

El contenedor padre tiene display flex por lo que automaticamente el comportamiento de los hijos cambia y conviven en el mismo lugar

~~Siempre debemos tener un contenedor principal para usar flex~~

###### Propiedades
1. **Justify Content** : Me alinia los contenedores en el eje x
2. **Align-Itmes** : Me alinia los contenedores en el eje y

>**Nota**: que cuando es una columna, justify-content cambia a vertical y align-items a horizontal.

>**Nota**:cuando estableces la dirección a una fila invertida o columna, el inicio y el final también se invierten.




  * **Stretch** : En caso de que los contenedores no tengan una altura definida estos se estiraran hasta los limites de su contenedor padre     

    ```
    .container{
        display: flex;
        border: 0.3rem solid black;
        align-itmes: stretch
    }
    .box{
        width: 10rem;
    }
    ``` 
  * **Baseline** :Caso contratio a stretch

3. Flex tambien tiene una propiedad interesante para indicarle en que orden organize los contenedores y esto lo utilizamos con la propiedad *order*

4. **Flex-grow** :Con esta indicacion le decimos a nuestros contenedor que crezcan para rellenar los espacios en blanco, que se encuentren

**Ejercicio**
``` 
.container{
  display: flex;
  flex-wrap: wrap;
  height: 50vh;
  align-items: center;
  border: 0.3rem solid black;
}
.box{
  height: 10rem;
  flex-basis: 10rem;
  flex-grow: 1;
}
``` 
 5. **align-self :** Otra propiedad que puedes aplicar a elementos individuales es align-self. Esta propiedad acepta los mismos valores de align-items y sus valores son usados para un elemento específico.

 6. **flex-flow :** Las dos propiedades flex-direction y flex-wrap son usadas a menudo en conjunto con la propiedad abreviada flex-flow, Por ejemplo, puedes usar flex-flow para establecer filas y envolverlas.

```css
.container{
  display: flex;
  flex-flow: column wrap
  /*direccion wrap*/
}
```

7.  **align-content :** Esta propiedad acepta los siguientes valores:
* flex-start: Las líneas se posicionan en la parte superior del contenedor.
* flex-end: Las líneas se posicionan en la parte inferior del contenedor.
* center: Las líneas se posicionan en el centro (verticalmente hablando) del contenedor.
* space-between: Las líneas se muestran con la misma distancia entre ellas.
* space-around: Las líneas se muestran con la misma separación alrededor de ellas.
* stretch: Las líneas se estiran para ajustarse al contenedor.

Esto puede ser confuso, pero align-content determina el espacio entre las líneas cunado hacemos un wrap, mientras que align-items determina como los elementos en su conjunto están alineados dentro del contenedor. Cuando hay solo una línea, align-content no tiene efecto.

align-items es para una sola «línea» y es aplicado a cada elemento, mientras align-content aplica para las líneas (no exactamente a los elementos) cuando hay más de una.

## Dimensionamiento Flexible

Volvamos ahora a nuestro primer ejemplo y veamos cómo podemos controlar qué proporción de espacio ocupan los elementos flexibles. Inicia tu copia local de flexbox0.html o toma una copia de flexbox1.html como nuevo punto de partida (consúltalo en vivo).

Primero, añade la regla siguiente al final de tu CSS:

article {
  flex: 1;
}

Este es un valor de proporción sin unidades que especifica la cantidad de espacio disponible sobre el eje principal que ocupa cada elemento flexible. En este caso, damos a cada elemento <article> un valor de 1, lo que significa que todos ocuparán una cantidad igual del espacio libre restante después de que se hayan establecido elementos como el área de relleno y el margen. Es una proporción, lo que significa que dar a cada elemento flexible un valor de 400000 tendría exactamente el mismo efecto.

Ahora añade la regla siguiente debajo de la anterior:

article:nth-of-type(3) {
  flex: 2;
}
Copy to Clipboard
Al actualizar verás que el tercer <article> ocupa ahora el doble del ancho disponible que los otros dos; ahora hay cuatro unidades de proporción disponibles en total. Los primeros dos elementos flexibles tienen una cada uno, por lo que ocupan 1/4 del espacio disponible cada uno. El tercero tiene dos unidades, por lo que ocupa 2/4 del espacio disponible (o 1/2).

También puedes especificar un valor de tamaño mínimo dentro del valor flexible. Actualiza las reglas para tu artículo de la manera siguiente:

article {
  flex: 1 200px;
}

article:nth-of-type(3) {
  flex: 2 200px;
}
Copy to Clipboard
Esto establece básicamente que «a cada elemento flexible se le da primero 200px del espacio disponible. Después de eso, el resto del espacio disponible se reparte de acuerdo con las unidades de proporción». Actualiza y observa de qué modo se reparte ahora el espacio.
