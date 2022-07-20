# Propiedades de Grid

https://lenguajecss.com/css/maquetacion-y-colocacion/grid-css/

### Basicas

* Display Grid : Le dice al contenedor padre, que va a ser una grilla

```css
display: grid;
```

* Filas y Columnas

```css
grid-template-columns : 20px 20px 20px 20px;
grid-template-rows : 20px 20px 20px 20px;
```

Cada valor indica un espacio en la grilla en este caso seria una grid de 4x4, cada celda tendra una tamaño de 20px

![Imagen Representativa filas y columnas](https://static.platzi.com/media/user_upload/www.canva.com_design_DAEPC3ca3BQ_Dldv9zjYSIE0LBb-BzEQng_view_utm_content%3DDAEPC3ca3BQ%26utm_campaign%3Ddesignshare%26utm_medium%3Dlink%26utm_source%3Dsharebutton-8762400f-64f9-4b0f-af71-66a794857a4f.jpg)

> Esto lo podemos acortar par aque sea mucho mas rapido y sencillo con la propiedad **"grid-template"** de la siguiente forma

```css
grid-template: repeat(4,20px) / repeat(4,20px)
    /*Filas / Columnas*/
```

* Espaciado : Para esto nosotros utilizamos la propiedad "gap"

```css
column-gap : 5px;
row-gap : 5px;
gap : 5px 5px;
/*Filas / Columnas*/
```

Tambien cuando estamos utilizando css grid tenemos una nueva unidad de medida y estas son los fr o fraccion

Una fr equivale a una fraccion por lo tanto si las utilizamos en las columnas, nos las dividira en 2 partes iguales

```css
.container{
    display: grid;
    grid-template-columns: repeat(2 , 1fr);
    }
```

> Tip: esto tambien se puede hacer xon los rows pero para eso nesecitamos tener un alto definido en el contendor

* Areas : Estas son un conjunto de celdas dentro de la grid 
![Visual studio code logo](https://static.platzi.com/media/user_upload/www.canva.com_design_DAEPC3ca3BQ_Dldv9zjYSIE0LBb-BzEQng_view_utm_content%3DDAEPC3ca3BQ%26utm_campaign%3Ddesignshare%26utm_medium%3Dlink%26utm_source%3Dsharebutton%20%281%29-80d0810a-99e2-49d9-91c3-40034583f693.jpg)
Las cuales definimos de la siguiente manera

```css
grid-template-areas: "header header  header header  header"
                     "main   main    .      sidebar sidebar" 
                     "main   main    .      sidebar sidebar" 
                     "footer footer  footer footer  footer";
```

## Alineamiento

Cuando estamos intentando alinear los elementos con grid hay que tener en cuenta que no podmeos alinear distintos contenedores en distintas posciones respecto al padre 

![Imagen de alineamiento](https://static.platzi.com/media/user_upload/%C3%B1o-e69efa2d-7bcb-4339-a33d-8efb81c3c710.jpg)

### Propiedades

| Propiedad|Eje         | 
| ---------|------------|
| Justify  |inline/row  |
| align    |block/column|

**Primer grupo**
: Alinean lo que esta por dentro de la grid
* justify-items 
* align-items
* place-items

```css
.container{
    justify-items: start | end | center | stretch;
    align-items: start | end | center | stretch;
    /*Combinacion delas dos anteriores*/
    place-items : <align-items> <justify-items>;
}
```

**Segundo grupo**
: Alinea la grid en su contenedor
* justify-content
* align-content
* place-content

```css
.container{
    justify-content: start | end | center | stretch;
    justify-content: space-around | space-between | space-evenly;
    align-content: start | end | center | stretch;
    align-content: space-around | space-between | space-evenly;
    /*Combinacion delas dos anteriores*/
    place-content : <align-content> <justify-content>;
}
```

**space-around:** Deja espacio entre cada item, pero los espacios de las orillas izquierda y derecha son menores que los del centro.

**space-between:** Solo hay espacio en la parte central y las orillas no tienen ningún espacio.

**space-evenly:** Los espacios son iguales en todos lados (en el centro y en las orillas).


![](https://static.platzi.com/media/user_upload/Screenshot%202021-03-01%20at%2008.19.07-0229b35a-adf1-41bc-a0b0-874f98a67944.jpg)
![](https://static.platzi.com/media/user_upload/Screenshot%202021-03-01%20at%2008.18.41-b9c8bd01-9e40-4438-b02e-0ef4d226f30c.jpg)


---
## Automatizacion de tracks

Muchas veces cuando estamos trabajando del lado del front-end normalmente hacemos uso del api, para traernos los datos del back y representarlos de forma visual, al hacer esto no es necesario modificar nuestra grilla manualmente sino que se puede automatizar

```css
.container{
    grid-auto-flow: row | column | row dense | column dense;
}
/* Agrega automaticamente columnas */
/* Agrega automaticamente Filas */
```

**DENSE:** Sirve para autocompletar con los ultimos elementos los posibles huecosque hallan quedado en la cuadricula

https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow

```css
.container{
    grid-auto-columns: 60px;
    /* Define el tamaño de columnas que se agregaran automaticamente*/
    grid-auto-rows: 60px;
    /* Define el tamaño de las filas que se agregaran automaticamente */
}
```
https://developer.mozilla.org/es/docs/Web/CSS/grid-auto-columns

---

Tambien utilizamos propiedades para indicar en que posicion de la grilla queremos que empiezen los elementos, eso lo hacemos con las siguientes propiedades

```css
.item1{
    grid-column-start: 2 /*La segunda celda de la grilla sera el punto de partida para posicionar los elementos*/;
    grid-row-start: 3 /*La tercera celda de la grilla sera el punto de partida para posicionar los elementos*/;
}
```

## Funciones 

#### repeat()
La función CSS repeat() representa un fragmento repetido de la lista de la pista, permitiendo un gran número de columnas o renglones que exhiben un patrón recurrente para ser escrito de una forma más compacta

 Utilizamos esta funcion para indicar que se repita alguna caracteristica de un elemento, ejemplo:

```css
.container{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    /*Suena muy redundante*/
    grid-template-columns: repeat(3, 1fr);
    /*EL primer valor nos indica
    el numero de veces que queremos se repita y el segundo
    la medida del elemento*/
}
```
#### minmax()
En función Css minmax() el min representa el tamaño mínimo que va a tener cada uno de los elementos de la grid y el max nos indica el valor máximo de los elementos de la grid. Esto nos sirve para que el contenido se vea bien en determinados tamaños.

```css
.container{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    /*Suena muy redundante*/
    grid-template-columns: repeat(3, minmax(200px, 300px));
    /*Tendar un ancho maximo de 300px y minimo de 200px*/
}
```

#### Fit content

__auto-fit__

Con la función de auto-fit() ADAPTA las columnas DISPONIBLES ACTUALMENTE en el espacio expandiéndolas para que ocupen cualquier espacio disponible. El navegador hace eso después de LLENAR ese espacio adicional con columnas adicionales (como con el autocompletar) y luego colapsar las vacías.

__auto-fill__

Con la función de auto-fill() LLENA la fila con tantas columnas como pueda caber. Por lo tanto, crea columnas implícitas cada vez que cabe una nueva columna, porque está tratando de LLENAR la fila con tantas columnas como sea posible. Las columnas recién agregadas pueden estar vacías, pero seguirán ocupando un espacio designado en la fila.

---
**Estas funciones con perfectas para el responsive design.**

La función fit-content() organiza un contenido en especifico el cual lo reserva y el resto seria auto.

![](https://static.platzi.com/media/user_upload/Captura-15b8646d-3199-454f-9035-64ea947e79de.jpg)

Lo que hace es establecer un ancho máximo o algo así, necesita tener obligatorimente contenido adentro que lo haga crecer, no funciona por sí solo

En ese caso funciona como el width: auto; junto con el width-max, en donde se dice que el ancho del elemento depende de su contenido, pero sin rebasar un ancho establecido en el width-max