# Módulo 3: Estilos Dinámicos

## 📖 Introducción

A medida que avanzamos en la construcción de nuestro proyecto, es crucial que pensemos en la experiencia del usuario. Los estilos dinámicos, como los efectos al pasar el cursor sobre un botón, proporcionan retroalimentación visual y mejoran la interacción. En este módulo, aprenderemos a implementar estos estilos y a usar diferentes formatos para definir colores en CSS.

## 📌 Agenda

**Conceptos:**
- **Pseudo-clases:** entendiendo y aplicando, con énfasis en `:hover`.
- **Exploración de colores en CSS:** desde nombres simples hasta valores HEX y RGB.

**Implementación en el proyecto:**
- Enlaces y botones con efectos al pasar el cursor.
- Estilizando nuestro footer para mejorar la consistencia y experiencia del usuario.

**Resumen y pasos a seguir**

## 📚 Conceptos

### 1. Pseudo-clases

Las pseudo-clases son herramientas poderosas en CSS que nos permiten aplicar estilos en situaciones específicas.

#### 🌟 `:hover`

Usado principalmente en botones y enlaces, `:hover` se activa cuando un usuario coloca el cursor sobre un elemento. Ayuda a resaltar interacciones posibles y a guiar al usuario.

Ejemplo:

```css
/* El fondo se vuelve gris claro al pasar el cursor sobre el elemento a (enlaces)*/
a:hover {
  background-color: lightgray; 
}
```

### 2. Colores en CSS

El color es fundamental para el diseño. Veamos diferentes maneras de definirlo en CSS:

- **Nombres de colores:** Son palabras clave que representan colores específicos. Ejemplo: `color: black;`.
- **Valores HEX:** Códigos de seis caracteres que representan colores. Ejemplo: `color: #000000;` para negro.
- **Valores RGB:** Usan tres números para representar los colores rojo, verde y azul. Ejemplo: `color: rgb(0, 0, 0);` para negro.

## 🛠️ Implementación en el proyecto

### 1. Enlaces y botones con efectos al pasar el cursor

**Objetivo:** Queremos que, al pasar el cursor sobre un enlace o botón, el usuario reciba una señal visual de que ese elemento es interactivo.

**Pasos:**
- Para los enlaces de la navegación: Al pasar el cursor, el color del texto cambiará a negro, se añadirá un poco de espacio alrededor para resaltar el enlace, y el texto se convertirá a mayúsculas.
- Para los botones: Buscamos un cambio sutil de color al pasar el cursor.

Inserta el siguiente código en `styles.css`:

```css
/* Navegación */
nav a:hover {
  color: #000000;              /* Cambia el color del texto a negro */
  padding: 5px 10px;          /* Añade un poco de espacio alrededor */
  background-color: #d9e3da;  /* Establece un color de fondo claro */
  font-size: 13px;            /* Cambia el tamaño de fuente a 13 pixeles*/
  text-transform: uppercase;  /* Convierte el texto a mayúsculas */
}

/* Estilo para Botones */
.estilo-boton:hover {
  background-color: #a7bea9;  /* Cambia el color de fondo del botón */
}


```

### 2. Mejorando el diseño del footer

**Objetivo:** Deseamos que los enlaces en el footer también tengan una retroalimentación visual al pasar el cursor, manteniendo una estética consistente con el resto de nuestro sitio.

**Pasos:**
- Definimos un color base para nuestros enlaces en el footer.
- Al pasar el cursor, este enlace se resaltará de manera similar a nuestros enlaces de navegación.

Añade el siguiente código:

```css
/* Footer */
footer a {
  color: #d9e3da;  /* Color de texto por defecto */
}

footer a:hover {
  color: #000000;              /* Cambia el color del texto a negro */
  padding: 5px 10px;          /* Espacio alrededor para resaltarlo */
  background-color: #d9e3da;  /* Color de fondo claro */
  font-size: 13px;            /* Cambia el tamaño de fuente a 13 pixeles*/
  text-transform: uppercase;  /* Texto en mayúsculas */
  text-decoration: none;      /* Elimina cualquier subrayado */
}

```

## 📝 Resumen y pasos a seguir

Con este módulo, hemos intensificado la experiencia visual de nuestro proyecto, implementando interactividad en botones y enlaces. Además, hemos sumergido nuestros dedos en el mundo colorido de CSS, aprendiendo diferentes formas de definir colores.

En el próximo módulo, daremos un salto hacia el diseño responsive, garantizando que nuestro sitio luzca y funcione de manera óptima en todo tipo de dispositivos. ¡Nos vemos pronto en el siguiente capítulo de esta aventura!
