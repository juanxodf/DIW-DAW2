# 📘 Chuleta de CSS — De 0 a Pro


## 🔹 1. Selectores básicos

```css
/* Por etiqueta */
p { color: red; }   /* Afecta a todos los <p> */

/* Por clase */
.caja { background: lightblue; }   /* Afecta a elementos con class="caja" */

/* Por id */
#principal { width: 80%; }   /* Afecta a elemento con id="principal" */

/* Universal */
* { margin: 0; padding: 0; }   /* Resetea todo */
```


## 🔹 2. Selectores combinados

```css
/* Hijo directo */
div > p { color: blue; }   /* Solo <p> hijos DIRECTOS de un <div> */

/* Descendiente */
div p { color: green; }   /* Todos los <p> dentro de un <div> */

/* Hermano adyacente */
h1 + p { color: orange; }   /* Primer <p> justo después de un <h1> */

/* Hermanos generales */
h1 ~ p { color: purple; }   /* Todos los <p> después de un <h1> */
```


## 🔹 3. Atributos

```css
a[href] { color: red; }   /* Todos los <a> con href */
a[href^="https"] { color: green; }  /* Empieza por */
a[href$=".pdf"] { color: blue; }    /* Termina en */
a[href*="google"] { color: purple; }/* Contiene */
```


## 🔹 4. Colores, fondos y texto

```css
body {
  background: #f0f0f0;       /* Hexadecimal */
  color: rgb(0, 0, 0);       /* RGB */
  color: rgba(0, 0, 0, .5);  /* Con transparencia */
  background-image: url("fondo.jpg");
  background-size: cover;
}

p {
  font-family: Arial, sans-serif;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
  text-decoration: underline;
  line-height: 1.5;
  letter-spacing: 2px;
}
```


## 🔹 5. Caja (Box Model)

```css
.caja {
  width: 200px;
  height: 100px;
  padding: 20px;      /* espacio interior */
  margin: 10px;       /* espacio exterior */
  border: 2px solid black;
  box-sizing: border-box; /* Incluye borde y padding en el width */
}
```


## 🔹 6. Posicionamiento

```css
.caja1 { position: static; }   /* por defecto */
.caja2 { position: relative; top: 10px; left: 20px; }
.caja3 { position: absolute; top: 0; right: 0; }
.caja4 { position: fixed; bottom: 0; right: 0; }
.caja5 { position: sticky; top: 20px; }
```


## 🔹 7. Display y layout

```css
span { display: inline; }   /* Se comporta como texto */
div { display: block; }     /* Ocupa toda la línea */
li { display: inline-block; } /* Como inline, pero admite alto/ancho */
.container { display: flex; justify-content: center; align-items: center; }
.grid { display: grid; grid-template-columns: 1fr 2fr; gap: 10px; }
```


## 🔹 8. Pseudo-clases

```css
a:hover { color: red; }       /* Al pasar el ratón */
a:active { color: blue; }     /* Al hacer click */
a:visited { color: purple; }  /* Enlaces visitados */
input:focus { border: 2px solid green; } /* Al enfocar */
p:first-child { font-weight: bold; }
p:last-child { color: gray; }
p:nth-child(2) { color: orange; } /* Segundo hijo */
```


## 🔹 9. Pseudo-elementos

```css
p::first-line { color: red; }   /* Primera línea */
p::first-letter { font-size: 2em; }
p::before { content: "👉 "; }   /* Inserta antes */
p::after { content: " ✅"; }    /* Inserta después */
```



## 🔹 10. Transiciones y animaciones

```css
.caja {
  transition: all 0.5s ease;
}
.caja:hover {
  transform: scale(1.2) rotate(10deg);
}

/* Animaciones */
@keyframes mover {
  0% { transform: translateX(0); }
  100% { transform: translateX(100px); }
}
.caja {
  animation: mover 2s infinite alternate;
}
```


## 🔹 11. Responsividad (Media Queries)

```css
@media (max-width: 768px) {
  body { background: lightblue; }
}
@media (min-width: 1024px) {
  body { background: lightgreen; }
}
```


## 🔹 12. Cosas útiles extra

```css
/* Sombras */
.box { box-shadow: 2px 2px 5px rgba(0,0,0,0.3); }

/* Bordes redondeados */
.img { border-radius: 50%; }

/* Degradados */
.fondo { background: linear-gradient(45deg, red, yellow); }

/* Z-index */
.superior { position: absolute; z-index: 10; }
```

📌 **Tip final**:

* **Hijos directos** → `>`
* **Hermanos** → `+` (adyacente) o `~` (todos)
* **Pseudo-elementos** → `::before`, `::after`, `::first-line`, `::first-letter`
* **Pseudo-clases** → `:hover`, `:focus`, `:nth-child()`

