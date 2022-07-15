# Propiedades de Grid

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

> Esto lo podemos acortar par aque sea mucho mas rapido y sencillo con la propiedad **"grid-template"** de la siguiente forma

```css
grid-template: repeat(4,20px) / repeate(4,20px)
    /*Filas / Columnas*/
```

* Espaciado : Para esto nosotros utilizamos la propiedad "gap"

```css
gap : 5px 5px;
/*Filas / Columnas*/
```

* Areas : Estas son un conjunto de celdas dentro de la grid 
![Visual studio code logo](https://static.platzi.com/media/user_upload/www.canva.com_design_DAEPC3ca3BQ_Dldv9zjYSIE0LBb-BzEQng_view_utm_content%3DDAEPC3ca3BQ%26utm_campaign%3Ddesignshare%26utm_medium%3Dlink%26utm_source%3Dsharebutton%20%281%29-80d0810a-99e2-49d9-91c3-40034583f693.jpg)
Las cuales definimos de la siguiente manera

```css
grid-template-areas: "header header  header header  header"
                     "main   main    .      sidebar sidebar" 
                     "main   main    .      sidebar sidebar" 
                     "footer footer  footer footer  footer";
```