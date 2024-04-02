# Propiedades de Grid

Grid es un sistema de diseño bidimensional que nos permite trabajar con filas y columnas. A continuación, veremos las propiedades más importantes de Grid.

Vamos a dividir las propiedades de Grid en dos categorías: propiedades del contenedor y propiedades de los elementos.

## Propiedades del contenedor

Para todos los ejemplos, consideraremos el siguiente HTML:

```html
<div class="container">
    <div class="item item-1">Item 1</div>
    <div class="item item-2">Item 2</div>
    <div class="item item-3">Item 3</div>
    <div class="item item-4">Item 3</div>
    <div class="item item-5">Item 3</div>
</div>

```

### display

La propiedad `display` es la que nos permite activar el modelo de diseño de Grid. Para ello, debemos asignarle el valor `grid` al contenedor.

```css
.container {
    display: grid; /* grid | inline-grid */
}
```

### grid-template-columns

La propiedad `grid-template-columns` establece el tamaño de las columnas del grid. Puede tomar uno o más valores, separados por espacios.

```css

.container {
    display: grid;
    grid-template-columns: 100px 200px 100px;
}

```

Nota* Si queremos que una columna tenga un tamaño automático, podemos usar la palabra clave `auto`. Lo cual hará que la columna se ajuste al contenido, o sea, al tamaño del texto o de la imagen. Un ejemplo de esto sería:

```css

.container {
    display: grid;
    grid-template-columns: 100px auto 100px;
}

```

Podemos ver que la segunda columna tiene un tamaño automático, ya que se ajusta al contenido. Casos de uso practicos para esto sería cuando queremos que una columna se ajuste al contenido de la celda y las demás tengan un tamaño fijo. Otro caso de uso sería cuando queremos que una columna tenga un tamaño fijo y las demás se ajusten al contenido. Con imagenes, por ejemplo, esto es muy útil. Veamos un ejemplo con imagenes. Considera el siguiente HTML

```html

<div class="container">
    <div class="item item-1"><img src="img1.jpg" alt="Imagen 1"></div>
    <div class="item item-2"><img src="img2.jpg" alt="Imagen 2"></div>
    <div class="item item-3"><img src="img3.jpg" alt="Imagen 3"></div>
    <div class="item item-4"><img src="img4.jpg" alt="Imagen 4"></div>
    <div class="item item-5"><img src="img5.jpg" alt="Imagen 5"></div>
    <div class="item item-6"><img src="img6.jpg" alt="Imagen 6"></div>
</div>

```

Y el siguiente CSS

```css

.container {
    display: grid;
    grid-template-columns: 100px auto 100px;
}

```

En este caso, la primera y la última columna tienen un tamaño fijo de 100px, mientras que la segunda columna tiene un tamaño automático, ya que se ajusta al tamaño de la imagen. Pero, ¿qué pasa si las imagenes tienen tamaños diferentes? En ese caso, la segunda columna se ajustará al tamaño de la imagen más grande. Si queremos que la segunda columna se ajuste al tamaño de la imagen más pequeña, podemos usar la propiedad `min-content`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-columns: 100px min-content 100px;
}

```

En este caso, la segunda columna se ajustará al tamaño de la imagen más pequeña. Si la imagen más grande es más grande que el tamaño de la columna, la imagen se recortará. Si queremos que la imagen se ajuste al tamaño de la columna, podemos usar la propiedad `max-content`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-columns: 100px max-content 100px;
}

```

En este caso, la imagen se ajustará al tamaño de la columna. Si la imagen es más grande que el tamaño de la columna, la columna se ajustará al tamaño de la imagen. Si la imagen es más pequeña que el tamaño de la columna, la imagen se ajustará al tamaño de la columna. Si queremos que la imagen se ajuste al tamaño de la columna, pero que no se recorte si es más grande, podemos usar la propiedad `fit-content`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-columns: 100px fit-content(100px) 100px;
}

```

En este caso, la imagen se ajustará al tamaño de la columna. Si la imagen es más grande que el tamaño de la columna, la columna se ajustará al tamaño de la imagen. Si la imagen es más pequeña que el tamaño de la columna, la imagen se ajustará al tamaño de la columna. Si la imagen es más grande que el tamaño de la columna, la imagen se recortará. Si queremos que la imagen se ajuste al tamaño de la columna, pero que no se recorte si es más grande, podemos usar la propiedad `minmax`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-columns: 100px minmax(100px, auto) 100px;
}

```

Como podemos ver en este ejemplo, la segunda columna se ajustará al tamaño de la columna, pero no se recortará si es más grande. Si la imagen es más grande que el tamaño de la columna, la columna se ajustará al tamaño de la imagen. Si la imagen es más pequeña que el tamaño de la columna, la imagen se ajustará al tamaño minimo de la columna (100px). Si queremos que la imagen se ajuste al tamaño de la columna, pero que no se recorte si es más grande, podemos usar la propiedad `repeat`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-columns: repeat(3, 100px);
}

```

En este caso, las tres columnas tendrán un tamaño fijo de 100px. Si queremos que la imagen se ajuste al tamaño de la columna, pero que no se recorte si es más grande, podemos usar la propiedad `fr`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
}

```

En este caso, la primera y la última columna tendrán un tamaño fijo de 1fr, mientras que la segunda columna tendrá un tamaño fijo de 2fr. Si queremos que la imagen se ajuste al tamaño de la columna, pero que no se recorte si es más grande, podemos usar la propiedad `grid-template-rows`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-rows: 100px 200px 100px;
}

```

### grid-template-rows

La propiedad `grid-template-rows` establece el tamaño de las filas del grid. Puede tomar uno o más valores, separados por espacios.

```css

.container {
    display: grid;
    grid-template-rows: 100px 200px 100px;
}

```

Nota* Si queremos que una fila tenga un tamaño automático, podemos usar la palabra clave `auto`. Lo cual hará que la fila se ajuste al contenido, o sea, al tamaño del texto o de la imagen. Un ejemplo de esto sería:

```css

.container {
    display: grid;
    grid-template-rows: 100px auto 100px;
}

```

Podemos ver que la segunda fila tiene un tamaño automático, ya que se ajusta al contenido. Casos de uso practicos para esto sería cuando queremos que una fila se ajuste al contenido de la celda y las demás tengan un tamaño fijo. Otro caso de uso sería cuando queremos que una fila tenga un tamaño fijo y las demás se ajusten al contenido. Con imagenes, por ejemplo, esto es muy útil. Veamos un ejemplo con imagenes. Considera el siguiente HTML

```html

<div class="container">
    <div class="item item-1"><img src="img1.jpg" alt="Imagen 1"></div>
    <div class="item item-2"><img src="img2.jpg" alt="Imagen 2"></div>
    <div class="item item-3"><img src="img3.jpg" alt="Imagen 3"></div>
    <div class="item item-4"><img src="img4.jpg" alt="Imagen 4"></div>
    <div class="item item-5"><img src="img5.jpg" alt="Imagen 5"></div>
    <div class="item item-6"><img src="img6.jpg" alt="Imagen 6"></div>
</div>

```

Y el siguiente CSS

```css

.container {
    display: grid;
    grid-template-rows: 100px auto 100px;
}

```

En este caso, la primera y la última fila tienen un tamaño fijo de 100px, mientras que la segunda fila tiene un tamaño automático, ya que se ajusta al tamaño de la imagen. Pero, ¿qué pasa si las imagenes tienen tamaños diferentes? En ese caso, la segunda fila se ajustará al tamaño de la imagen más grande. Si queremos que la segunda fila se ajuste al tamaño de la imagen más pequeña, podemos usar la propiedad `min-content`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-rows: 100px min-content 100px;
}

```

En este caso, la segunda fila se ajustará al tamaño de la imagen más pequeña. Si la imagen más grande es más grande que el tamaño de la fila, la imagen se recortará. Si queremos que la imagen se ajuste al tamaño de la fila, podemos usar la propiedad `max-content`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-rows: 100px max-content 100px;
}

```

En este caso, la imagen se ajustará al tamaño de la fila. Si la imagen es más grande que el tamaño de la fila, la fila se ajustará al tamaño de la imagen. Si la imagen es más pequeña que el tamaño de la fila, la imagen se ajustará al tamaño de la fila. Si queremos que la imagen se ajuste al tamaño de la fila, pero que no se recorte si es más grande, podemos usar la propiedad `fit-content`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-rows: 100px fit-content(100px) 100px;
}

```

En este caso, la imagen se ajustará al tamaño de la fila. Si la imagen es más grande que el tamaño de la fila, la fila se ajustará al tamaño de la imagen. Si la imagen es más pequeña que el tamaño de la fila, la imagen se ajustará al tamaño de la fila. Si la imagen es más grande que el tamaño de la fila, la imagen se recortará. Si queremos que la imagen se ajuste al tamaño de la fila, pero que no se recorte si es más grande, podemos usar la propiedad `minmax`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-rows: 100px minmax(100px, auto) 100px;
}

```

Como podemos ver en este ejemplo, la segunda fila se ajustará al tamaño de la fila, pero no se recortará si es más grande. Si la imagen es más grande que el tamaño de la fila, la fila se ajustará al tamaño de la imagen. Si la imagen es más pequeña que el tamaño de la fila, la imagen se ajustará al tamaño minimo de la fila (100px). Si queremos que la imagen se ajuste al tamaño de la fila, pero que no se recorte si es más grande, podemos usar la propiedad `repeat`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-rows: repeat(3, 100px);
}

```

En este caso, las tres filas tendrán un tamaño fijo de 100px. Si queremos que la imagen se ajuste al tamaño de la fila, pero que no se recorte si es más grande, podemos usar la propiedad `fr`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-rows: 1fr 2fr 1fr;
}

```

En este caso, la primera y la última fila tendrán un tamaño fijo de 1fr, mientras que la segunda fila tendrá un tamaño fijo de 2fr. Si queremos que la imagen se ajuste al tamaño de la fila, pero que no se recorte si es más grande, podemos usar la propiedad `grid-template-columns`. Veamos un ejemplo:

```css

.container {
    display: grid;
    grid-template-columns: 100px 200px 100px;
    grid-template-rows: 100px 200px 100px;
}

```

### grid-template-areas

La propiedad `grid-template-areas` establece un nombre para cada área del grid. Puede tomar uno o más valores, separados por espacios.

```css

.container {
    display: grid;
    grid-template-areas: "header header header"
                         "nav main main"
                         "nav footer footer";
}

```

A decir verdad, esta propiedad es muy útil para organizar el contenido de una página web. Por ejemplo, si queremos que el header ocupe toda la fila superior, el nav ocupe toda la columna izquierda y el main ocupe toda la columna derecha, podemos hacer lo siguiente:

```css

.container {
    display: grid;
    grid-template-columns: 200px auto;
    grid-template-rows: 100px auto;
    grid-template-areas: "header header"
                         "nav main";
}

```

Y en el HTML, podemos hacer lo siguiente:

```html

<div class="container">
    <div class="item item-1" style="grid-area: header;">Header</div>
    <div class="item item-2" style="grid-area: nav;">Nav</div>
    <div class="item item-3" style="grid-area: main;">Main</div>
</div>

```

### grid-template

La propiedad `grid-template` es un shorthand(propiedad abreviada) que combina las propiedades `grid-template-rows`, `grid-template-columns` y `grid-template-areas` en una sola declaración.

```css

.container {
    display: grid;
    grid-template: "header header header"
                   "nav main main"
                   "nav footer footer" / 200px auto;
}

```

grid-template funciona de la siguiente manera `grid-template: <grid-template-areas> / <grid-template-columns>`. En este caso, estamos definiendo las áreas del grid y las columnas del grid. Si queremos definir las filas del grid, podemos hacer lo siguiente:

```css

.container {
    display: grid;
    grid-template: "header header header"
                   "nav main main"
                   "nav footer footer" / 100px auto;
}

```

En resumen funciona de la siguiente manera `grid-template: <grid-template-areas> / <grid-template-rows> <grid-template-columns>`. En este caso, estamos definiendo las áreas del grid, las filas del grid y las columnas del grid.

### grid-gap

La propiedad `grid-gap` establece el espacio entre las filas y las columnas del grid. Puede tomar uno o dos valores, separados por espacios.

```css

.container {
    display: grid;
    grid-gap: 10px 20px;
}

```

En este caso, el espacio entre las filas será de 10px y el espacio entre las columnas será de 20px. Si queremos que el espacio entre las filas y las columnas sea el mismo, podemos hacer lo siguiente:

```css

.container {
    display: grid;
    grid-gap: 10px;
}

```

En este caso, el espacio entre las filas y las columnas será de 10px. Si queremos que el espacio entre las filas y las columnas sea diferente, podemos hacer lo siguiente:

```css

.container {
    display: grid;
    grid-row-gap: 10px;
    grid-column-gap: 20px;
}

```

En este caso, el espacio entre las filas será de 10px y el espacio entre las columnas será de 20px.

### justify-items

La propiedad `justify-items` alinea los elementos a lo largo del eje de las columnas del grid. Puede tomar uno de los siguientes valores:

- `start`: los elementos se alinean al principio de las columnas.
- `end`: los elementos se alinean al final de las columnas.
- `center`: los elementos se alinean en el centro de las columnas.
- `stretch`: los elementos se estiran para ajustarse al tamaño de las columnas. (default)

```css

.container {
    display: grid;
    justify-items: center; /* start | end | center | stretch */
}

```

### align-items

La propiedad `align-items` alinea los elementos a lo largo del eje de las filas del grid. Puede tomar uno de los siguientes valores:

- `start`: los elementos se alinean al principio de las filas.
- `end`: los elementos se alinean al final de las filas.
- `center`: los elementos se alinean en el centro de las filas.
- `stretch`: los elementos se estiran para ajustarse al tamaño de las filas. (default)

```css

.container {
    display: grid;
    align-items: center; /* start | end | center | stretch */
}

```

### justify-content

La propiedad `justify-content` alinea los elementos a lo largo del eje de las columnas del grid. Puede tomar uno de los siguientes valores:

- `start`: los elementos se alinean al principio de las columnas.
- `end`: los elementos se alinean al final de las columnas.
- `center`: los elementos se alinean en el centro de las columnas.
- `space-between`: los elementos se distribuyen de manera uniforme en las columnas.
- `space-around`: los elementos se distribuyen de manera uniforme en las columnas con espacios iguales alrededor de ellos.

```css

.container {
    display: grid;
    justify-content: space-between; /* start | end | center | space-between | space-around */
}

```

### align-content

La propiedad `align-content` alinea las líneas de elementos a lo largo del eje de las filas del grid. Solo tiene efecto si los elementos se distribuyen en varias líneas. Puede tomar uno de los siguientes valores:

- `start`: las líneas de elementos se alinean al principio de las filas.
- `end`: las líneas de elementos se alinean al final de las filas.
- `center`: las líneas de elementos se alinean en el centro de las filas.
- `space-between`: las líneas de elementos se distribuyen de manera uniforme en las filas.
- `space-around`: las líneas de elementos se distribuyen de manera uniforme en las filas con espacios iguales alrededor de ellas.

```css

.container {
    display: grid;
    align-content: center; /* start | end | center | space-between | space-around */
}

```

## Medidas

### fr

La unidad `fr` (fracción) nos permite distribuir el espacio restante entre las columnas o las filas del grid. Puede tomar cualquier valor entero, positivo o negativo.

```css

.container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
}

```

En este caso, la primera y la última columna tendrán un tamaño fijo de 1fr, mientras que la segunda columna tendrá un tamaño fijo de 2fr.

### auto

La palabra clave `auto` nos permite ajustar el tamaño de las columnas o las filas del grid al contenido de los elementos. En otras palabras, el tamaño de las columnas o las filas se ajustará al tamaño del texto o de la imagen.

```css

.container {
    display: grid;
    grid-template-columns: 100px auto 100px;
}

```

En este caso, la segunda columna tendrá un tamaño automático, ya que se ajusta al contenido.

### min-content

La palabra clave `min-content` nos permite ajustar el tamaño de las columnas o las filas del grid al tamaño del contenido más pequeño. En otras palabras, el tamaño de las columnas o las filas se ajustará al tamaño del texto o de la imagen más pequeña.

```css

.container {
    display: grid;
    grid-template-columns: 100px min-content 100px;
}

```

En este caso, la segunda columna se ajustará al tamaño de la imagen más pequeña.

### max-content

La palabra clave `max-content` nos permite ajustar el tamaño de las columnas o las filas del grid al tamaño del contenido más grande. En otras palabras, el tamaño de las columnas o las filas se ajustará al tamaño del texto o de la imagen más grande.

```css

.container {
    display: grid;
    grid-template-columns: 100px max-content 100px;
}

```

En este caso, la imagen se ajustará al tamaño de la columna.

### fit-content

La palabra clave `fit-content` nos permite ajustar el tamaño de las columnas o las filas del grid al tamaño del contenido. En otras palabras, el tamaño de las columnas o las filas se ajustará al tamaño del texto o de la imagen, pero no se recortará si es más grande.

```css

.container {
    display: grid;
    grid-template-columns: 100px fit-content(100px) 100px;
}

```

En este caso, la imagen se ajustará al tamaño de la columna.

### minmax

La función `minmax` nos permite establecer un tamaño mínimo y un tamaño máximo para las columnas o las filas del grid. Puede tomar dos valores, separados por una coma.

```css

.container {
    display: grid;
    grid-template-columns: 100px minmax(100px, auto) 100px;
}

```

En este caso, la segunda columna se ajustará al tamaño de la columna, pero no se recortará si es más grande.

### %, px, em, rem, vw, vh

Todas las unidades de medida que hemos visto anteriormente se pueden usar para establecer el tamaño de las columnas o las filas del grid.

```css

.container {
    display: grid;
    grid-template-columns: 100px 200px 100px;
    grid-template-rows: 100px 200px 100px;
}

```

En este caso, las columnas tendrán un tamaño fijo de 100px, 200px y 100px, mientras que las filas tendrán un tamaño fijo de 100px, 200px y 100px.

## repeat

La función `repeat` nos permite repetir un patrón de columnas o filas en el grid. Puede tomar dos valores, separados por una coma.

```css

.container {
    display: grid;
    grid-template-columns: repeat(3, 100px);
}

```

## combinación de unidades y casos de uso

Pensemos en un layout complejo, donde queremos que las columnas tengan un tamaño fijo, pero que las filas se ajusten al contenido. Podemos hacer lo siguiente:

```css

.container {
    display: grid;
    grid-template-columns: 100px 200px 100px;
    grid-template-rows: auto auto auto;
}

```

en el html, podemos hacer lo siguiente con imagenes:

```html

<div class="container">
    <div class="item item-1"><img src="img1.jpg" alt="Imagen 1"></div>
    <div class="item item-2"><img src="img2.jpg" alt="Imagen 2"></div>
    <div class="item item-3"><img src="img3.jpg" alt="Imagen 3"></div>
    <div class="item item-4"><img src="img4.jpg" alt="Imagen 4"></div>
    <div class="item item-5"><img src="img5.jpg" alt="Imagen 5"></div>
    <div class="item item-6"><img src="img6.jpg" alt="Imagen 6"></div>
</div>

```

En este caso, las columnas tendrán un tamaño fijo de 100px, 200px y 100px, mientras que las filas se ajustarán al tamaño de las imagenes.

Pensemos en otro layout complejo donde queremos que las columnas tengan un tamaño fijo pero no menor a 100px, y que las filas se ajusten al contenido en su mayor tamaño, pero que no se recorten si son más grandes. Podemos hacer lo siguiente:

```css

.container {
    display: grid;
    grid-template-columns: 100px minmax(100px, auto) 100px;
    grid-template-rows: minmax(100px, auto) minmax(100px, auto) minmax(100px, auto);
}

```

en el html, podemos hacer lo siguiente con imagenes:

```html

<div class="container">
    <div class="item item-1"><img src="img1.jpg" alt="Imagen 1"></div>
    <div class="item item-2"><img src="img2.jpg" alt="Imagen 2"></div>
    <div class="item item-3"><img src="img3.jpg" alt="Imagen 3"></div>
    <div class="item item-4"><img src="img4.jpg" alt="Imagen 4"></div>
    <div class="item item-5"><img src="img5.jpg" alt="Imagen 5"></div>
    <div class="item item-6"><img src="img6.jpg" alt="Imagen 6"></div>
</div>

```

En este caso, las columnas tendrán un tamaño fijo de 100px, 200px y 100px, mientras que las filas se ajustarán al tamaño de las imagenes, pero no se recortarán si son más grandes.

Pensemos en otro layout complejo donde queremos que las columnas tengan un tamaño fijo pero no menor a 100px, y que las filas se ajusten al contenido en su mayor tamaño, pero que no se recorten si son más grandes. Además, queremos que el espacio entre las filas y las columnas sea de 10px. Podemos hacer lo siguiente:

```css

.container {
    display: grid;
    grid-template-columns: 100px minmax(100px, auto) 100px;
    grid-template-rows: minmax(100px, auto) minmax(100px, auto) minmax(100px, auto);
    grid-gap: 10px;
}

```

en el html, podemos hacer lo siguiente con imagenes:

```html

<div class="container">
    <div class="item item-1"><img src="img1.jpg" alt="Imagen 1"></div>
    <div class="item item-2"><img src="img2.jpg" alt="Imagen 2"></div>
    <div class="item item-3"><img src="img3.jpg" alt="Imagen 3"></div>
    <div class="item item-4"><img src="img4.jpg" alt="Imagen 4"></div>
    <div class="item item-5"><img src="img5.jpg" alt="Imagen 5"></div>
    <div class="item item-6"><img src="img6.jpg" alt="Imagen 6"></div>
</div>

```

En este caso, las columnas tendrán un tamaño fijo de 100px, 200px y 100px, mientras que las filas se ajustarán al tamaño de las imagenes, pero no se recortarán si son más grandes. Además, el espacio entre las filas y las columnas será de 10px.


## Propiedades de los elementos

### grid-column-start

La propiedad `grid-column-start` establece la línea de inicio de un elemento en las columnas del grid. Puede tomar un valor entero, positivo o negativo.

```css

.item {
    grid-column-start: 2;
}

```

En este caso, el elemento comenzará en la segunda línea de las columnas del grid.

### grid-column-end

La propiedad `grid-column-end` establece la línea de fin de un elemento en las columnas del grid. Puede tomar un valor entero, positivo o negativo.

```css

.item {
    grid-column-end: 4;
}

```

En este caso, el elemento terminará en la cuarta línea de las columnas del grid.

### grid-column

La propiedad `grid-column` es un shorthand(propiedad abreviada) que combina las propiedades `grid-column-start` y `grid-column-end` en una sola declaración.

```css

.item {
    grid-column: 2 / 4;
}

```

En este caso, el elemento comenzará en la segunda línea de las columnas del grid y terminará en la cuarta línea de las columnas del grid.

### grid-row-start

La propiedad `grid-row-start` establece la línea de inicio de un elemento en las filas del grid. Puede tomar un valor entero, positivo o negativo.

```css

.item {
    grid-row-start: 2;
}

```

En este caso, el elemento comenzará en la segunda línea de las filas del grid.

### grid-row-end

La propiedad `grid-row-end` establece la línea de fin de un elemento en las filas del grid. Puede tomar un valor entero, positivo o negativo.

```css

.item {
    grid-row-end: 4;
}

```

En este caso, el elemento terminará en la cuarta línea de las filas del grid.

### grid-row

La propiedad `grid-row` es un shorthand(propiedad abreviada) que combina las propiedades `grid-row-start` y `grid-row-end` en una sola declaración.

```css

.item {
    grid-row: 2 / 4;
}

```

En este caso, el elemento comenzará en la segunda línea de las filas del grid y terminará en la cuarta línea de las filas del grid.

### grid-area

La propiedad `grid-area` establece la posición de un elemento en el grid. Puede tomar uno de los siguientes valores:

- `<grid-row-start> / <grid-column-start> / <grid-row-end> / <grid-column-end>`
- `<grid-row-start> / <grid-column-start> / <grid-row-span> / <grid-column-span>`
- `<grid-area-name>`

```css

.item {
    grid-area: 2 / 2 / 4 / 4;
}

```

En este caso, el elemento comenzará en la segunda línea de las filas del grid y en la segunda línea de las columnas del grid, y terminará en la cuarta línea de las filas del grid y en la cuarta línea de las columnas del grid.

```css

.item {
    grid-area: 2 / 2 / span 2 / span 2;
}

```

En este caso, el elemento comenzará en la segunda línea de las filas del grid y en la segunda línea de las columnas del grid, y se extenderá dos líneas en las filas del grid y dos líneas en las columnas del grid.

```css

.item {
    grid-area: header;
}

```

En este caso, el elemento se colocará en el área llamada `header`.

### justify-self

La propiedad `justify-self` alinea un elemento a lo largo del eje de las columnas del grid. Puede tomar uno de los siguientes valores:

- `start`: el elemento se alinea al principio de las columnas.
- `end`: el elemento se alinea al final de las columnas.
- `center`: el elemento se alinea en el centro de las columnas.
- `stretch`: el elemento se estira para ajustarse al tamaño de las columnas. (default)

```css

.item {
    justify-self: center; /* start | end | center | stretch */
}

```

### align-self

La propiedad `align-self` alinea un elemento a lo largo del eje de las filas del grid. Puede tomar uno de los siguientes valores:

- `start`: el elemento se alinea al principio de las filas.
- `end`: el elemento se alinea al final de las filas.
- `center`: el elemento se alinea en el centro de las filas.
- `stretch`: el elemento se estira para ajustarse al tamaño de las filas. (default)

```css

.item {
    align-self: center; /* start | end | center | stretch */
}

```

## Conclusión

Grid es un sistema de diseño bidimensional que nos permite trabajar con filas y columnas. Hemos visto las propiedades más importantes de Grid, tanto para el contenedor como para los elementos. Con estas propiedades, podemos crear layouts complejos y flexibles. Además, hemos visto cómo combinar diferentes unidades de medida y cómo usar la función `repeat`. Con Grid, podemos crear diseños responsivos y adaptables a cualquier dispositivo. Es una herramienta poderosa que nos permite crear interfaces de usuario modernas y atractivas. ¡Espero que esta guía te haya sido útil!


