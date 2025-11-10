# 🌐 Apuntes de Desarrollo de Interfaces Web (Responsive)


## 🧱 1. Introducción. Repaso de HTML

HTML (HyperText Markup Language) es el **lenguaje de marcado** que estructura el contenido de la web.
Cada página está formada por **etiquetas** que definen encabezados, párrafos, imágenes, enlaces, formularios, etc.

### 📄 Estructura básica de un documento HTML

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi primera página web</title>
</head>
<body>
  <header>
    <h1>Bienvenido a mi página 🌍</h1>
  </header>

  <nav>
    <a href="#inicio">Inicio</a>
    <a href="#contacto">Contacto</a>
  </nav>

  <main>
    <section>
      <h2>Sobre mí</h2>
      <p>Hola, soy un desarrollador web apasionado por la tecnología.</p>
      <img src="foto.jpg" alt="Foto personal" width="200">
    </section>
  </main>

  <footer>
    <p>© 2025 Mi Sitio Web</p>
  </footer>
</body>
</html>
```

### 🧩 Etiquetas semánticas más importantes

| Etiqueta    | Uso principal                           |
| ----------- | --------------------------------------- |
| `<header>`  | Cabecera del sitio o sección            |
| `<nav>`     | Menús de navegación                     |
| `<main>`    | Contenido principal                     |
| `<section>` | Bloque temático                         |
| `<article>` | Contenido independiente (post, noticia) |
| `<aside>`   | Contenido lateral o complementario      |
| `<footer>`  | Pie de página                           |




## 📦 2. El Modelo de la Caja (Box Model)

Todo elemento HTML se comporta como una **caja** con diferentes áreas:

```
+-----------------------------+
|         margin              |
|  +-----------------------+  |
|  |       border          |  |
|  |  +-----------------+  |  |
|  |  |    padding      |  |  |
|  |  |  +-----------+  |  |  |
|  |  |  | content   |  |  |  |
|  |  |  +-----------+  |  |  |
|  |  +-----------------+  |  |
|  +-----------------------+  |
+-----------------------------+
```

### 🧮 Propiedades principales

```css
.caja {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid #2c3e50;
  margin: 15px;
  background-color: #ecf0f1;
}
```

👉 **Consejo:**
Agrega `box-sizing: border-box;` para que el `width` incluya el padding y el borde.

```css
* {
  box-sizing: border-box;
}
```

💡 Esto facilita mucho el diseño de layouts complejos.


## 🧭 3. Estructura Flex y Grid

### 🎯 Flexbox — diseño unidimensional (horizontal o vertical)

Flexbox es ideal para **alinear y distribuir elementos** en una sola dirección.

```html
<div class="contenedor">
  <div class="item">🟥</div>
  <div class="item">🟩</div>
  <div class="item">🟦</div>
</div>
```

```css
.contenedor {
  display: flex;
  justify-content: space-around; /* distribución horizontal */
  align-items: center;            /* alineación vertical */
  height: 150px;
  background-color: #f0f0f0;
}
.item {
  width: 80px;
  height: 80px;
  background-color: coral;
}
```

🧠 **Propiedades importantes:**

* `flex-direction`: dirección del eje (`row`, `column`)
* `justify-content`: alinea en el eje principal
* `align-items`: alinea en el eje cruzado
* `flex-wrap`: permite que los ítems bajen de línea


### 🧮 CSS Grid — diseño bidimensional

Grid permite diseñar estructuras con **filas y columnas**.

```html
<div class="grid">
  <div class="caja">1️⃣</div>
  <div class="caja">2️⃣</div>
  <div class="caja">3️⃣</div>
  <div class="caja">4️⃣</div>
</div>
```

```css
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 100px 100px;
  gap: 10px;
}
.caja {
  background-color: #3498db;
  color: white;
  font-size: 2em;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

📐 **Propiedades útiles:**

* `grid-template-columns` / `grid-template-rows`
* `gap`: espacio entre celdas
* `grid-column` / `grid-row`: para expandir elementos
* `justify-items` y `align-items`: alineación dentro de cada celda


## 📱 4. Diseño Adaptativo (Responsive Design)

El **diseño adaptativo** ajusta el sitio web según el dispositivo (móvil, tablet, PC).

### 🔑 Principios básicos:

1. Usar **unidades relativas** (`%`, `em`, `rem`, `vw`, `vh`).
2. Aplicar **media queries** para ajustar estilos según el ancho de pantalla.
3. Imágenes **fluidas** con `max-width: 100%`.
4. Usar **Flexbox y Grid** para estructuras flexibles.

### 🧭 Ejemplo práctico

```html
<div class="caja">Contenido adaptativo</div>
```

```css
.caja {
  width: 80%;
  margin: auto;
  background-color: lightblue;
  text-align: center;
  padding: 20px;
  font-size: 20px;
}

@media (max-width: 768px) {
  .caja {
    background-color: lightcoral;
    font-size: 16px;
  }
}
```

🖥️ → Azul en escritorio
📱 → Rojo en móvil


## 🎨 5. Pseudoclases y Pseudoelementos

### ✨ Pseudoclases

Se usan para definir **estados especiales** de un elemento.

```css
a:hover {
  color: red;
}

input:focus {
  border: 2px solid blue;
}

li:nth-child(odd) {
  background-color: #eee;
}

button:disabled {
  opacity: 0.5;
}
```

👉 **Ejemplo interactivo:**

```html
<input type="text" placeholder="Escribe algo...">
<button disabled>Deshabilitado</button>
```


### 🧩 Pseudoelementos

Permiten dar estilo a **partes específicas** de un elemento.

```css
p::first-letter {
  font-size: 2em;
  color: #e67e22;
}

p::before {
  content: "💬 ";
}

p::after {
  content: " 🔚";
}
```

🪄 Resultado:
💬 **P**rimera letra destacada 🔚


## ⚙️ 6. Sass (Syntactically Awesome Style Sheets)

Sass es un **preprocesador CSS** que añade características avanzadas:

* Variables
* Anidación
* Mixins
* Herencia
* Funciones y operaciones


### 🎨 Variables

```scss
$color-principal: #2980b9;
$tamano-base: 16px;

body {
  background-color: $color-principal;
  font-size: $tamano-base;
}
```


### 🧬 Anidación

```scss
nav {
  background-color: #34495e;
  ul {
    list-style: none;
    li {
      display: inline-block;
      a {
        color: white;
        text-decoration: none;
        &:hover {
          color: yellow;
        }
      }
    }
  }
}
```

---

### 🧰 Mixins

```scss
@mixin redondeado($radio) {
  border-radius: $radio;
  border: 1px solid #ccc;
}

button {
  @include redondeado(10px);
  background-color: #27ae60;
  color: white;
}
```


### ➗ Operaciones

```scss
$base: 10px;

div {
  margin: $base * 2; // 20px
  padding: $base / 2; // 5px
}
```

💡 Sass se compila a CSS normal antes de usarse en el navegador.


## 🧰 7. Frameworks para interfaces responsive: Bootstrap

Bootstrap es un **framework CSS** que simplifica la creación de sitios responsive.
Incluye una rejilla de 12 columnas, componentes listos y utilidades.

---

### 🚀 Integración

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
```


### 🧮 Sistema de rejilla

```html
<div class="container text-center">
  <div class="row">
    <div class="col-md-4 bg-primary text-white">Columna 1</div>
    <div class="col-md-4 bg-success text-white">Columna 2</div>
    <div class="col-md-4 bg-warning text-dark">Columna 3</div>
  </div>
</div>
```

🪄 En pantallas pequeñas las columnas se apilan, en grandes se distribuyen horizontalmente.


### 🧱 Componentes útiles

```html
<button class="btn btn-primary">Aceptar</button>
<button class="btn btn-outline-danger">Cancelar</button>

<div class="alert alert-success mt-3" role="alert">
  ✅ Operación completada con éxito.
</div>
```


### 🧩 Utilidades comunes

| Función            | Clases                    |
| ------------------ | ------------------------- |
| Texto centrado     | `.text-center`            |
| Márgenes y relleno | `.m-3`, `.p-2`            |
| Colores            | `.bg-dark`, `.text-light` |
| Mostrar/Ocultar    | `.d-none`, `.d-lg-block`  |



## 🧠 Conclusión

Dominar estos conceptos te permitirá construir sitios:

* 📱 **Adaptativos**
* 🎨 **Atractivos**
* ⚙️ **Eficientes**
* 🧩 **Mantenibles**

Combinando **HTML + CSS + Flexbox + Grid + Sass + Bootstrap**, podrás crear **interfaces modernas y profesionales** listas para cualquier dispositivo 🌎✨.

