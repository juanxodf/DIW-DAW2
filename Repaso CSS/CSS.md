# 📘 MEGA APUNTES CSS — LA BIBLIA COMPLETA

### 📌 Aquí encontramos:

* Selectores de todo tipo
* Pseudo-clases y pseudo-elementos
* Posicionamiento, layouts (flex, grid)
* Animaciones, transiciones, transformaciones
* Variables, funciones, filtros, efectos especiales
* Cosas raras (`:has`, `clip-path`, `mask-image`, `scroll-behavior`)
* Reglas para impresión y accesibilidad

Voy a dividirlo por **bloques temáticos**, con ejemplos y casos raros incluidos 👇

## 🔹 1. Selectores

### Básicos

```css
p {}           /* por etiqueta */
.clase {}      /* por clase */
#id {}         /* por id */
* {}           /* universal */
```

### Combinadores

```css
div p {}       /* descendiente */
div > p {}     /* hijo directo */
h1 + p {}      /* hermano adyacente */
h1 ~ p {}      /* hermanos posteriores */
```

### Atributos

```css
a[href] {}
a[href^="https"] {}  /* empieza */
a[href$=".pdf"] {}   /* termina */
a[href*="google"] {} /* contiene */
```

### Avanzados

```css
:first-child {}
:last-child {}
:nth-child(3) {}
:nth-child(odd) {}
:nth-of-type(2) {}
:only-child {}
:empty {}
:not(.activo) {}
:is(h1, h2, h3) {}
:where(section p) {}  /* igual que :is pero sin sumar especificidad */
:has(img) {}          /* selecciona si un elemento contiene otro (CSS4) */
```

## 🔹 2. Pseudo-clases de interacción

```css
a:link {}       /* enlace sin visitar */
a:visited {}
a:hover {}
a:active {}
button:focus {}
input:checked {}
input:disabled {}
input:required {}
input:valid {}
input:invalid {}
```

## 🔹 3. Pseudo-elementos

```css
p::first-line {}
p::first-letter {}
p::before { content:"👉"; }
p::after { content:"✅"; }
abbr::after { content:" (" attr(title) ")"; } /* usa atributos */
::selection { background: yellow; } /* al seleccionar texto */
```

## 🔹 4. Colores y fondos

```css
color: #333;
color: rgb(0,0,0);
color: rgba(0,0,0,.5);
background-image: url("fondo.jpg");
background-repeat: no-repeat;
background-position: center;
background-size: cover;
background-clip: text; /* fondo aplicado al texto */
```

## 🔹 5. Tipografía

```css
font-family: 'Arial', sans-serif;
font-size: 16px;
font-weight: bold;   /* 100 - 900 */
font-style: italic;
text-transform: uppercase;
text-decoration: underline;
letter-spacing: 2px;
word-spacing: 5px;
white-space: nowrap;
line-height: 1.5;
```

## 🔹 6. Box Model

```css
margin: 10px;
padding: 20px;
border: 2px solid black;
border-radius: 50%;       /* círculo */
box-sizing: border-box;
outline: 2px dashed red;  /* no ocupa espacio */
```


## 🔹 7. Posicionamiento

```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;

z-index: 10;
```


## 🔹 8. Display y layouts

```css
display: none;
display: inline;
display: block;
display: inline-block;
display: flex;
display: grid;
display: contents;
display: flow-root;
```


## 🔹 9. Flexbox

```css
.container {
  display: flex;
  flex-direction: row | column;
  justify-content: flex-start | center | space-between;
  align-items: stretch | center | flex-start;
  flex-wrap: wrap;
  gap: 10px;
}
.item { flex: 1; order: 2; }
```

## 🔹 10. Grid

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-rows: auto 200px;
  gap: 10px;
}
.item { grid-column: 1 / 3; grid-row: 2; }
```

## 🔹 11. Transiciones y transformaciones

```css
.caja {
  transition: all .3s ease;
}
.caja:hover {
  transform: rotate(15deg) scale(1.2);
}
```

## 🔹 12. Animaciones

```css
@keyframes mover {
  from { transform: translateX(0); }
  to { transform: translateX(100px); }
}
.caja {
  animation: mover 2s infinite alternate;
}
```

## 🔹 13. Filtros y efectos

```css
filter: blur(5px);
filter: brightness(1.5);
filter: grayscale(100%);
backdrop-filter: blur(10px); /* cristales tipo glassmorphism */
```


## 🔹 14. Responsive

```css
@media (max-width: 768px) { body { background: lightblue; } }
@media (orientation: landscape) {}
@media (prefers-color-scheme: dark) {} /* modo oscuro */
```


## 🔹 15. Variables CSS

```css
:root {
  --color-principal: #3498db;
  --espaciado: 10px;
}
.box { color: var(--color-principal); margin: var(--espaciado); }
```


## 🔹 16. Funciones CSS útiles

```css
width: calc(100% - 50px);
transform: translate(50%, -50%);
clip-path: circle(50%);
mask-image: url(mascara.svg);
```


## 🔹 17. Cosas raras pero útiles

```css
resize: both;            /* redimensionar un div */
cursor: pointer;         /* cambiar cursor */
scroll-behavior: smooth; /* scroll suave */
overscroll-behavior: none;
object-fit: cover;       /* imágenes responsivas */
aspect-ratio: 16/9;
writing-mode: vertical-rl; /* texto vertical */
```


## 🔹 18. Selectores avanzadísimos

```css
:root:has(body.dark) {}     /* si existe un hijo con clase dark */
html:lang(es) { font-family: Arial; } /* idioma */
```

## 🔹 19. Accesibilidad y print

```css
@media print {
  body { color: black; background: white; }
  a::after { content: " (" attr(href) ")"; }
}
```