
# 📌 Chuletario de Etiquetas HTML Frecuentes

## 1. Estructura Básica
- **`<!DOCTYPE html>`** → Indica el tipo de documento.
- **`<html>`** → Raíz de la página.
- **`<head>`** → Contiene metadatos, título, enlaces a estilos.
- **`<body>`** → Contenido visible de la página.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mi página</title>
  </head>
  <body>
    <h1>Hola Mundo</h1>
  </body>
</html>
```

---

## 2. Encabezados

* **`<h1>` a `<h6>`** → Títulos, de mayor a menor importancia.

```html
<h1>Título principal</h1>
<h2>Subtítulo</h2>
```

---

## 3. Párrafos y Texto

* **`<p>`** → Párrafo de texto.
* **`<span>`** → Texto en línea, sin salto de línea.
* **`<br>`** → Salto de línea.
* **`<strong>`** → Texto en **negrita** (semántico).
* **`<em>`** → Texto en *cursiva* (semántico).

```html
<p>Esto es un <strong>texto importante</strong> y <em>destacado</em>.</p>
```

---

## 4. Enlaces

* **`<a>`** → Crea un enlace.

```html
<a href="https://ejemplo.com" target="_blank">Ir a Ejemplo</a>
```

---

## 5. Imágenes

* **`<img>`** → Inserta una imagen.

```html
<img src="imagen.jpg" alt="Descripción de la imagen">
```

---

## 6. Listas

* **`<ul>`** → Lista desordenada.
* **`<ol>`** → Lista ordenada.
* **`<li>`** → Elemento de lista.

```html
<ul>
  <li>Elemento 1</li>
  <li>Elemento 2</li>
</ul>
```

---

## 7. Tablas

* **`<table>`** → Crea una tabla.
* **`<tr>`** → Fila.
* **`<td>`** → Celda.
* **`<th>`** → Celda de encabezado.

```html
<table>
  <tr>
    <th>Nombre</th>
    <th>Edad</th>
  </tr>
  <tr>
    <td>Ana</td>
    <td>25</td>
  </tr>
</table>
```

---

## 8. Formularios

* **`<form>`** → Contenedor de formulario.
* **`<input>`** → Campo de entrada.
* **`<label>`** → Etiqueta asociada a un input.
* **`<textarea>`** → Campo de texto grande.
* **`<button>`** → Botón.

```html
<form>
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre">
  <button type="submit">Enviar</button>
</form>
```

---

## 9. Contenedores

* **`<div>`** → Contenedor genérico en bloque.
* **`<section>`** → Sección temática.
* **`<article>`** → Contenido independiente.
* **`<header>` / `<footer>`** → Encabezado y pie de página.
* **`<nav>`** → Menú de navegación.
* **`<main>`** → Contenido principal.

```html
<section>
  <h2>Noticias</h2>
  <article>
    <h3>Noticia 1</h3>
    <p>Contenido de la noticia...</p>
  </article>
</section>
```

---

## 10. Multimedia

* **`<audio>`** → Reproducir audio.
* **`<video>`** → Reproducir video.

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
</video>
```

---

✅ **Tip**: Usa atributos como `id`, `class`, `src`, `alt`, `href`, `type`, `name` para dar funcionalidad y accesibilidad a las etiquetas.

