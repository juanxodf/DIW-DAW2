
# 🎨 **APUNTES COMPLETOS DE ANIMACIONES EN CSS**

---

## 🧩 1. Introducción a las animaciones en CSS

Las **animaciones en CSS** permiten crear efectos visuales fluidos sin necesidad de JavaScript.
Se usan para **mejorar la interacción del usuario** (UX), **dar dinamismo** a las interfaces o **resaltar elementos**.

Existen **dos mecanismos principales**:

1. **Transiciones (`transition`)** → animan el cambio entre *dos estados conocidos* (por ejemplo, normal y hover).
2. **Animaciones (`@keyframes` + `animation`)** → permiten secuencias más complejas con múltiples etapas o repeticiones.

---

## ⚡ 2. Transiciones en CSS

### 2.1. ¿Qué son?

Las **transiciones** permiten que los cambios en propiedades CSS ocurran **de forma gradual**.

👉 Se activan **cuando cambia una propiedad** (por ejemplo, con `:hover`, `:focus`, o al modificar una clase con JavaScript).

---

### 2.2. Sintaxis básica

```css
selector {
  transition: <property> <duration> <timing-function> <delay>;
}
```

#### Ejemplo:

```css
button {
  background-color: #3498db;
  color: white;
  transition: background-color 0.5s ease, transform 0.3s ease-in-out;
}

button:hover {
  background-color: #2ecc71;
  transform: scale(1.1);
}
```

📘 Al pasar el ratón, el botón cambia suavemente de color y aumenta su tamaño.

---

### 2.3. Propiedades de transición

| Propiedad                    | Descripción                     | Ejemplo                                                                  |
| ---------------------------- | ------------------------------- | ------------------------------------------------------------------------ |
| `transition-property`        | Define qué propiedad se animará | `transition-property: color;`                                            |
| `transition-duration`        | Tiempo que dura la animación    | `transition-duration: 0.5s;`                                             |
| `transition-timing-function` | Curva de aceleración            | `ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out`, `cubic-bezier()` |
| `transition-delay`           | Retraso antes de comenzar       | `transition-delay: 0.3s;`                                                |
| `transition`                 | Shorthand (todo en una línea)   | `transition: all 0.5s ease-in-out;`                                      |

---

### 2.4. Funciones de tiempo (`timing-function`)

Estas definen **cómo se distribuye la velocidad** de la transición:

| Valor                          | Descripción                                                      |
| ------------------------------ | ---------------------------------------------------------------- |
| `linear`                       | Velocidad constante                                              |
| `ease`                         | Aceleración al principio y desaceleración al final (por defecto) |
| `ease-in`                      | Empieza lento, termina rápido                                    |
| `ease-out`                     | Empieza rápido, termina lento                                    |
| `ease-in-out`                  | Empieza y termina lento                                          |
| `cubic-bezier(x1, y1, x2, y2)` | Permite definir tu propia curva personalizada                    |

Ejemplo:

```css
transition-timing-function: cubic-bezier(0.68, -0.55, 0.27, 1.55);
```

---

## 🎬 3. Animaciones con `@keyframes`

### 3.1. ¿Qué son?

Las animaciones definidas con `@keyframes` permiten **controlar múltiples etapas** del movimiento o cambio de un elemento, sin depender de un evento como `:hover`.

---

### 3.2. Sintaxis básica

```css
@keyframes nombreAnimacion {
  from { propiedad: valorInicial; }
  to { propiedad: valorFinal; }
}
```

O con **porcentajes**:

```css
@keyframes ejemplo {
  0% { transform: translateX(0); }
  50% { transform: translateX(100px); }
  100% { transform: translateX(0); }
}
```

---

### 3.3. Aplicación de la animación

```css
.elemento {
  animation-name: ejemplo;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: 0s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

O en una sola línea:

```css
animation: ejemplo 2s ease-in-out 0s infinite alternate;
```

---

### 3.4. Propiedades de `animation`

| Propiedad                   | Descripción                                                      | Ejemplo                                 |
| --------------------------- | ---------------------------------------------------------------- | --------------------------------------- |
| `animation-name`            | Nombre de la animación definida en `@keyframes`                  | `mover`                                 |
| `animation-duration`        | Duración total de un ciclo                                       | `2s`                                    |
| `animation-timing-function` | Curva de velocidad                                               | `ease`, `linear`, `ease-in`...          |
| `animation-delay`           | Retraso antes de iniciar                                         | `1s`                                    |
| `animation-iteration-count` | Número de repeticiones (`1`, `3`, `infinite`)                    | `infinite`                              |
| `animation-direction`       | Dirección: `normal`, `reverse`, `alternate`, `alternate-reverse` | `alternate`                             |
| `animation-fill-mode`       | Qué estado conserva el elemento antes/después de la animación    | `none`, `forwards`, `backwards`, `both` |
| `animation-play-state`      | Pausa o reanuda la animación                                     | `running`, `paused`                     |

---

### 3.5. Ejemplo completo

```css
@keyframes saltar {
  0% { transform: translateY(0); }
  30% { transform: translateY(-50px); }
  60% { transform: translateY(0); }
  100% { transform: translateY(-10px); }
}

.bola {
  width: 50px;
  height: 50px;
  background: tomato;
  border-radius: 50%;
  animation: saltar 1s ease-in-out infinite;
}
```

---

## 🧠 4. `animation-fill-mode` explicado

Controla **el estilo del elemento antes o después de la animación**.

| Valor       | Descripción                                       |
| ----------- | ------------------------------------------------- |
| `none`      | No mantiene el estado final ni inicial            |
| `forwards`  | Mantiene el estado final (`100%`)                 |
| `backwards` | Aplica el estado inicial (`0%`) antes de comenzar |
| `both`      | Combina ambos comportamientos                     |

Ejemplo:

```css
animation: mover 2s forwards;
```

➡️ El elemento se queda en la posición final tras terminar la animación.

---

## 🎛️ 5. Controlar animaciones con clases y JS

Puedes **iniciar, detener o cambiar animaciones** con JavaScript:

```js
document.querySelector('.caja').style.animationPlayState = 'paused';
```

O alternar clases con animaciones:

```js
element.classList.toggle('animar');
```

---

## 🎨 6. Transformaciones más comunes para animar

| Transformación    | Descripción              | Ejemplo              |
| ----------------- | ------------------------ | -------------------- |
| `translate(x, y)` | Mueve un elemento        | `translate(50px, 0)` |
| `scale(x, y)`     | Escala el tamaño         | `scale(1.2)`         |
| `rotate(deg)`     | Rota un elemento         | `rotate(45deg)`      |
| `skew(x, y)`      | Inclina un elemento      | `skew(20deg)`        |
| `matrix()`        | Combina transformaciones | —                    |

---

## 🧭 7. Ejemplos prácticos

### 🟡 Rotación infinita

```css
@keyframes rotar {
  to { transform: rotate(360deg); }
}

.icono {
  animation: rotar 2s linear infinite;
}
```

---

### 🟣 Efecto de aparición (fade in)

```css
@keyframes aparecer {
  from { opacity: 0; }
  to { opacity: 1; }
}

.texto {
  animation: aparecer 1.5s ease forwards;
}
```

---

### 🔵 Rebote

```css
@keyframes rebote {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
}

.caja {
  animation: rebote 0.8s ease-in-out infinite;
}
```

---

## ⚙️ 8. Rendimiento y buenas prácticas

✅ **Usa `transform` y `opacity`**: son las propiedades más eficientes.
🚫 Evita animar `width`, `height`, `top`, `left`, `margin`, etc. (requieren recalcular el layout).
🧠 **`will-change`** ayuda al navegador a optimizar:

```css
.elemento {
  will-change: transform, opacity;
}
```

💡 **Usa animaciones con propósito**: guían la atención, no distraen.

---

## 🧱 9. Compatibilidad y prefijos

Hoy en día, la mayoría de los navegadores soportan animaciones CSS sin prefijos.
Sin embargo, para proyectos legacy puedes añadir:

```css
-webkit-animation: nombre 2s infinite;
-moz-animation: nombre 2s infinite;
```

---

## 🌈 10. Recursos útiles

* [MDN Web Docs – Animations](https://developer.mozilla.org/es/docs/Web/CSS/animation)
* [Cubic Bezier Editor](https://cubic-bezier.com/)
* [Animate.css](https://animate.style/) → Librería con animaciones predefinidas
* [Keyframes.app](https://keyframes.app/) → Editor visual de animaciones

