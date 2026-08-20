# Box Model, Flexbox y Grid

# Parte 1 — Box Model

Ejemplos para repasar las 4 capas de la caja (content, padding, border, margin), el shorthand, box-sizing y el centrado con margin auto.

## Ejemplo 1 — Las 4 capas de la caja: content, padding, border, margin

PANEL HTML:
```html
<div class="caja">Contenido</div>
```

PANEL CSS:
```css
.caja {
  width: 200px;
  padding: 20px;
  border: 5px solid #ff4354;
  margin: 30px;
  background-color: #ffdde6;
}
```

## Ejemplo 2 — Padding: separar el contenido del borde

PANEL HTML:
```html
<div class="sin-padding">Sin padding</div>
<div class="con-padding">Con padding</div>
```

PANEL CSS:
```css
.sin-padding,
.con-padding {
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  margin-bottom: 10px;
}
.con-padding {
  padding: 25px;
}
```

## Ejemplo 3 — Margin: separar una caja de otra

PANEL HTML:
```html
<div class="caja">Caja 1</div>
<div class="caja">Caja 2</div>
<div class="caja">Caja 3</div>
```

PANEL CSS:
```css
.caja {
  background-color: #e8ecff;
  padding: 15px;
  margin-bottom: 20px;
}
```

## Ejemplo 4 — Padding y margin por separado en cada lado

PANEL HTML:
```html
<div class="caja">Mirá cómo quedo</div>
```

PANEL CSS:
```css
.caja {
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding-top: 40px;
  padding-left: 10px;
  margin-left: 60px;
}
```

## Ejemplo 5 — La propiedad abreviada (shorthand) de 4 valores

PANEL HTML:
```html
<div class="caja">Arriba - Derecha - Abajo - Izquierda</div>
```

PANEL CSS:
```css
.caja {
  background-color: #e8ecff;
  border: 2px solid #5b6cff;
  padding: 10px 30px 10px 5px;
}
```

## Ejemplo 6 — border: grosor, estilo y color

PANEL HTML:
```html
<div class="caja1">Borde sólido</div>
<div class="caja2">Borde punteado</div>
<div class="caja3">Borde discontinuo</div>
```

PANEL CSS:
```css
.caja1,
.caja2,
.caja3 {
  padding: 15px;
  margin-bottom: 10px;
}
.caja1 {
  border: 3px solid #ff4354;
}
.caja2 {
  border: 3px dotted #5b6cff;
}
.caja3 {
  border: 3px dashed #2d2d3a;
}
```

## Ejemplo 7 — border-radius: esquinas redondeadas

PANEL HTML:
```html
<div class="cuadrado">Cuadrado</div>
<div class="redondeado">Redondeado</div>
<div class="circulo">Círculo</div>
```

PANEL CSS:
```css
.cuadrado,
.redondeado,
.circulo {
  width: 120px;
  height: 120px;
  background-color: #ff4354;
  color: white;
  margin-bottom: 10px;
  padding: 10px;
}
.redondeado {
  border-radius: 15px;
}
.circulo {
  border-radius: 50%;
}
```


## Ejemplo 8 — box-sizing: por qué el ancho "se agranda" con el padding

PANEL HTML:
```html
<div class="normal">content-box (default)</div>
<div class="corregida">border-box</div>
```

PANEL CSS:
```css
.normal,
.corregida {
  width: 250px;
  padding: 20px;
  border: 4px solid #ff4354;
  background-color: #ffdde6;
  margin-bottom: 10px;
}
.normal {
  box-sizing: content-box;
}
.corregida {
  box-sizing: border-box;
}
```

## Ejemplo 9 — width/height vs. contenido que desborda

PANEL HTML:
```html
<div class="caja">
  Este texto es bastante largo y capaz que no entra en el espacio que le dimos a la caja con el alto fijo que pusimos.
</div>
```

PANEL CSS:
```css
.caja {
  width: 200px;
  height: 80px;
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding: 10px;
  overflow: hidden; // cambiar auto
}
```


# Parte 2 — Flexbox

Ejemplos para practicar display: flex, la alineación con justify-content y align-items, el crecimiento de items con flex, y un caso real de navbar.

## Ejemplo 1 — display: flex, lo básico

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 20px;
  margin: 5px;
}
```

## Ejemplo 2 — gap: separar los items sin usar margin

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">A</div>
  <div class="item">B</div>
  <div class="item">C</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  gap: 20px;
}
.item {
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding: 15px;
}
```

## Ejemplo 3 — justify-content: alinear en el eje horizontal

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  justify-content: space-between;
  background-color: #ffdde6;
  padding: 10px;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 15px;
}
```

## Ejemplo 4 — align-items: alinear en el eje vertical

PANEL HTML:
```html
<div class="contenedor">
  <div class="item chico">Chico</div>
  <div class="item grande">Grande</div>
  <div class="item mediano">Mediano</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  align-items: center;
  height: 200px;
  background-color: #ffdde6;
}
.item {
  background-color: #5b6cff;
  color: white;
  padding: 10px;
  margin: 5px;
}
.chico {
  height: 40px;
}
.grande {
  height: 120px;
}
.mediano {
  height: 70px;
}
```

## Ejemplo 5 — justify-content + align-items juntos: centrar del todo

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">Estoy centrado</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 250px;
  background-color: #ffdde6;
  border: 2px solid #ff4354;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 20px;
}
```

## Ejemplo 6 — flex-direction: cambiar el eje principal

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 15px;
}
```

## Ejemplo 7 — flex-wrap: que los items pasen a la siguiente línea

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}
.item {
  background-color: #e8ecff;
  border: 2px solid #5b6cff;
  padding: 20px;
  width: 150px;
}
```

## Ejemplo 8 — flex: 1, que los items repartan el espacio disponible

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">Columna A</div>
  <div class="item">Columna B</div>
  <div class="item">Columna C</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  gap: 15px;
}
.item {
  flex: 1;
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding: 20px;
  text-align: center;
}
```

## Ejemplo 9 — flex con proporciones distintas

PANEL HTML:
```html
<div class="contenedor">
  <div class="lateral">Menú</div>
  <div class="principal">Contenido principal</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: flex;
  gap: 10px;
}
.lateral {
  flex: 1;
  background-color: #5b6cff;
  color: white;
  padding: 20px;
}
.principal {
  flex: 3;
  background-color: #ffdde6;
  padding: 20px;
}
```

## Ejemplo 10 — Navbar con Flexbox: caso real

PANEL HTML:
```html
<nav class="navbar">
  <div class="logo">MiSitio</div>
  <div class="links">
    <span>Inicio</span>
    <span>Nosotros</span>
    <span>Contacto</span>
  </div>
</nav>
```

PANEL CSS:
```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #ff4354;
  padding: 15px 25px;
}
.logo {
  color: white;
  font-weight: bold;
}
.links {
  display: flex;
  gap: 20px;
  color: white;
}
```

---

# Parte 3 — Grid

Ejemplos para practicar display: grid, columnas y filas con fr, repeat(), grid-column, grid-template-areas para un layout completo, y auto-fit para grillas responsive.

## Ejemplo 1 — display: grid, lo básico

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 20px;
  text-align: center;
}
```


## Ejemplo 2 — Columnas de distinto ancho con fr

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">Angosta</div>
  <div class="item">Ancha</div>
  <div class="item">Media</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  gap: 10px;
}
.item {
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding: 15px;
}
```

## Ejemplo 3 — Columnas con un ancho fijo y una flexible

PANEL HTML:
```html
<div class="contenedor">
  <div class="menu">Menú fijo</div>
  <div class="contenido">Contenido flexible</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: 150px 1fr;
  gap: 10px;
}
.menu {
  background-color: #5b6cff;
  color: white;
  padding: 15px;
}
.contenido {
  background-color: #ffdde6;
  padding: 15px;
}
```


## Ejemplo 4 — grid-template-rows: también se pueden definir las filas

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 80px 150px;
  gap: 10px;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 10px;
}
```

## Ejemplo 5 — gap con columnas y filas por separado

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  row-gap: 30px;
  column-gap: 5px;
}
.item {
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding: 15px;
  text-align: center;
}
```

## Ejemplo 6 — repeat(): evitar escribir 1fr muchas veces

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 20px;
  text-align: center;
}
```


## Ejemplo 7 — grid-column: hacer que un item ocupe varias columnas

PANEL HTML:
```html
<div class="contenedor">
  <div class="destacado">Ocupo 2 columnas</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}
.destacado {
  grid-column: span 2;
  background-color: #ff4354;
  color: white;
  padding: 20px;
}
.item {
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding: 20px;
}
```


## Ejemplo 8 — Grid de galería de tarjetas (caso real)

PANEL HTML:
```html
<div class="galeria">
  <div class="tarjeta">Producto 1</div>
  <div class="tarjeta">Producto 2</div>
  <div class="tarjeta">Producto 3</div>
  <div class="tarjeta">Producto 4</div>
  <div class="tarjeta">Producto 5</div>
  <div class="tarjeta">Producto 6</div>
</div>
```

PANEL CSS:
```css
.galeria {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
.tarjeta {
  background-color: #ffdde6;
  border: 2px solid #ff4354;
  padding: 25px;
  text-align: center;
}
```


## Ejemplo 9 — Layout de página completa con grid-template-areas

PANEL HTML:
```html
<div class="pagina">
  <header class="encabezado">Header</header>
  <nav class="menu">Menú</nav>
  <main class="contenido">Contenido principal</main>
  <footer class="pie">Footer</footer>
</div>
```

PANEL CSS:
```css
.pagina {
  display: grid;
  grid-template-columns: 150px 1fr;
  grid-template-areas:
    "encabezado encabezado"
    "menu contenido"
    "pie pie";
  gap: 10px;
}
.encabezado {
  grid-area: encabezado;
  background-color: #ff4354;
  color: white;
  padding: 15px;
}
.menu {
  grid-area: menu;
  background-color: #5b6cff;
  color: white;
  padding: 15px;
}
.contenido {
  grid-area: contenido;
  background-color: #ffdde6;
  padding: 15px;
}
.pie {
  grid-area: pie;
  background-color: #2d2d3a;
  color: white;
  padding: 15px;
}
```

## Ejemplo 10 — Grid responsive automático con auto-fit

PANEL HTML:
```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

PANEL CSS:
```css
.contenedor {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  gap: 10px;
}
.item {
  background-color: #ff4354;
  color: white;
  padding: 20px;
  text-align: center;
}
```
