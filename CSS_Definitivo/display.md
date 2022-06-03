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
```
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