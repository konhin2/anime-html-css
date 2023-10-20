# Módulo 1: Introducción y Fundamentos de CSS

**Lección dirigida por el instructor**

## Agenda

**Conceptos:**

-   Introducción a CSS
-   Anatomía de una regla CSS
-   Métodos de inclusión de CSS: En línea, internos y externos
-   Comentarios en CSS
-   Selectores de Elemento

**Implementación en el proyecto:**

-   Aplicación de estilos básicos
-   Progresamos estilizando encabezados y enlaces
-   Migración a hoja de estilo externa
-   Agregando estilos al encabezado y pie de pagina
-   Resumen y siguientes pasos

## Conceptos

### Introducción a CSS

HTML y CSS trabajan juntos para crear la estructura y el diseño de una página web. Imagina que estás construyendo una casa: HTML sería como los ladrillos y la estructura básica, proporcionando la base y los componentes esenciales, mientras que CSS sería como la pintura, el diseño interior y la decoración, determinando cómo se ve y se siente esa estructura.

**Codigo de inicio**

Observa el de archivo `index.html` de inicio del proyecto y abrelo en el navegador. ¿Notas cómo la página web se ve simple y sin mucho estilo? Eso es porque aún no hemos aplicado CSS. El CSS, que significa "Cascading Style Sheets", es esencial para transformar una página HTML básica en algo visualmente atractivo. Nos permite controlar la apariencia de los elementos en la página, desde colores hasta márgenes y mucho más.

### Anatomía de una regla CSS

Para entender cómo funciona CSS, es útil desglosar una regla CSS individual. Consiste en:

-   **Selector:** El elemento HTML que queremos estilizar.
-   **Propiedad:** El tipo de estilo que queremos cambiar (como color, fuente, etc.)
-   **Valor:** El valor específico para esa propiedad.

Ejemplo:

```css
p {
    color: red;
}
```

Aquí, `p` es el selector, `color` es la propiedad y `red` es el valor.

### Métodos de inclusión de CSS

Existen tres formas principales de incluir CSS:

1. **En línea**: Directamente en el elemento HTML usando el atributo style.

```html
<p style="color: blue;">Este es un texto azul.</p>
```

2. **Interno**: Dentro de la etiqueta `<style>` en el `<head>` de nuestro documento HTML.

```html
<head>
    <style>
        p {
            color: green;
        }
    </style>
</head>
```

3. **Externo**: En un archivo separado con extensión `.css`, vinculado al HTML.

```html
<!--
    Para vincular una hoja de estilo externa, utiliza el elemento <link> dentro de la sección <head> del archivo HTML.
-->
<head>
    <link rel="stylesheet" type="text/css" href="estilos.css">
</head>
```

### Comentarios en CSS

Los comentarios son esenciales para mantener nuestro código organizado y comprensible. No afectan la ejecución del código y son útiles para añadir notas y recordatorios.

```css
/* Este es un comentario en CSS */

```

### Selectores de Elemento

Los selectores nos permiten aplicar estilos a elementos específicos. Por ejemplo, si quisiéramos que todos los párrafos de nuestra página tuvieran una fuente más grande:

```css
p {
    font-size: 16px;
}
```

## Implementación en el proyecto

### Aplicación de estilos básicos

Para comenzar, queremos darle estilo al cuerpo de nuestra página web. Esto se logra definiendo estilos para el elemento `body` en CSS.

Dentro del documento `index.html`, los estilos deben ser insertados dentro de una etiqueta `<style>` que, a su vez, debe ubicarse dentro del `<head>` de la página. Así es como se ve:

```html
<head>
    <style>
        body {
            background-color: #f0ede6; /*cambia el color de fondo a un tono beige*/
            color: #333; /* Establece el color del texto del cuerpo a un tono oscuro */
            line-height: 1.6; /* Define la altura de línea para el texto del cuerpo */
        }
    </style>
</head>

```

Agrega estos estilos, guarda estos cambios y abre tu archivo actualizado `index.html` en el navegador. Debes ver que el color de fondo ha cambiado a un tono beige y el texto a un color oscuro. También notarás una altura de línea más espaciada.

### Progresamos estilizando encabezados y enlaces:

De manera similar, para estilizar los encabezados y enlaces, agreguemos el siguiente código CSS también dentro de las etiquetas `<style>`:

```html
<head>
    <style>
        h1, h2, h3, h4, h5, h6 {
            text-transform: uppercase; /* Transforma el texto de los encabezados a letras mayúsculas */
        }

        a {
            color: #000000;/* Establece el color de los enlaces a negro */
        }
    </style>
</head>
```

Guardo los cambios y recarga tu archivo `index.html` en el navegador. Ahora, todos los encabezados deberían aparecer en mayúsculas y los enlaces en color negro.

### Migración a hoja de estilo externa

**1. Creación del archivo styles.css**
Vamos a crear un archivo externo para nuestros estilos. Crea un nuevo archivo llamado `styles.css` en la misma carpeta donde se encuentra el archivo `index.html` y en él, transfiere todo el código CSS que hemos definido:

```css
/* Estilos para el cuerpo de la página */
body {
    background-color: #f0ede6;
    color: #333;
    line-height: 1.6;
}

/* Estilos para los encabezados */
h1, h2, h3, h4, h5, h6 {
    text-transform: uppercase;
}

/* Estilo para los enlaces */
a {
    color: #000000;
}

```

**2. Vinculación del archivo styles.css a index.html**

Ahora, necesitamos vincular nuestro archivo CSS externo (`styles.css`) a nuestro documento HTML (`index.html`). Para ello, usa la etiqueta `<link>` dentro del `<head>`:

```html
<!-- Archivo HTML -->
<head>
    <link rel="stylesheet" type="text/css" href="estilos.css">
</head>
```

Guarda los cambios y abre de nuevo tu archivo `index.html` en el navegador. Deberías ver exactamente el mismo diseño, ¡pero ahora con la ventaja de tener el CSS en un archivo separado!

### Agregando estilos al encabezado y pie de pagina

Ahora, dentro de la hoja de estilos externa styles.css podemos agregar más estilos para el encabezado y el pie de página:

```css

/* Estilos para el encabezado de la página */
header {
    background-image: url("/img/animes.jpg");
    background-size: cover;
    height: 600px;
    color: #fff;
}

/* Estilos para el pie de página */
footer {
    background-color: #000000;
    color: #fff;
}

```

### Resumen y siguientes pasos

¡Gran trabajo! Ahora comprendes la base de CSS, desde su anatomía básica hasta la implementación en tu proyecto. La habilidad de darle estilo y diseño a tu sitio web es esencial y, con la práctica, podrás crear sitios asombrosos.

En la próxima sección, nos adentraremos en aspectos más avanzados de CSS, ¡prepárate para llevar tus habilidades al siguiente nivel! 🎨🚀
