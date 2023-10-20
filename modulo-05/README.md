# Módulo 5: Posicionamiento y Layout en CSS

## Introducción:

El diseño y la estructura de una página web son esenciales para una buena experiencia del usuario. Las propiedades `display` y `position` de CSS brindan un control detallado sobre la disposición de los elementos en la pantalla. En este módulo, exploraremos estas herramientas y cómo pueden afectar la disposición de tu contenido.

## 📌 Agenda

-   Concenptos:
    -   Propiedades de display
    -   Propiedades de posicionamiento
-   Implementaciónen el Proyecto:
    -   Estilizando la sección de Animes
    -   Ajustando el video y su iframe
    -   Diseñando un formulario sencillo
-   Resumen y Pasos a Seguir

## 📚 Conceptos

### Propiedades de Display:

La propiedad `display` define cómo se representa un elemento en la página.

-   **block:**
    -   Los elementos `block` siempre comienzan en una nueva línea y se expanden para ocupar todo el ancho disponible.
    -   Ejemplos típicos: `<div>`, `<p>`, `<ul>`, `<ol>`, `<li>`
-   **inline:**
    -   A diferencia de los elementos `block`, los elementos `inline` no empiezan en una nueva línea y sólo ocupan el espacio necesario.
    -   Ejemplos: `<span>`, `<a>`.
-   **inline-block:**
    -   Estos elementos son una mezcla de los dos anteriores.
    -   Se colocan en línea como los elementos `inline`, pero pueden tener un ancho y alto definidos, como los elementos `block`.

**Ejemplo:** Los elementos de lista (`<li>`) son `block` por defecto y comienzan en una nueva línea. Si quisieras que se mostraran uno al lado del otro (en lugar de apilados verticalmente) y que cada elemento tuviera un margen y un ancho determinados, necesitarías cambiar su comportamiento por defecto utilizando `display: inline-block`.

Por qué: `inline-block` te permite controlar el ancho y el alto (como con `block`) pero se coloca en línea con otros elementos (como `inline`). Así, puedes lograr un diseño horizontal sin recurrir a técnicas más complicadas.

```css
ul li {
  display: inline-block;
  width: 100px; /* Define el ancho */
  margin-right: 10px; /* Espacio a la derecha de cada elemento */
}
```

Este código haría que cada elemento de la lista (`<li>`) tenga un ancho de `100px` y un margen a la derecha de `10px`, y se muestren uno al lado del otro.

### Propiedades de Posicionamiento:

El posicionamiento en CSS determina cómo y dónde se ubica un elemento en relación con otros elementos o con el viewport.

#### `position`:

Esta propiedad tiene varios valores:

-   **static**: Es el comportamiento por defecto de un elemento. Se posiciona según el flujo normal del documento.
-   **relative**: El elemento se posiciona en relación a su lugar original. Se puede mover con propiedades adicionales como top, right, bottom, y left, pero sin alterar el espacio que ocupa en el flujo del documento.
-   **absolute**: Se posiciona de manera absoluta en relación al primer ancestro que tenga un valor de position distinto de static. Si no existe tal ancestro, se posiciona en relación al viewport.
-   **fixed**: El elemento se posiciona en relación directa al viewport, lo que significa que permanecerá en la misma ubicación incluso si se desplaza la página.
-   **sticky**: SEs una mezcla entre relative y fixed. Se posiciona relativo hasta que una condición se cumple (generalmente definida por top, bottom, left, o right), momento en el que se convierte en fixed.

#### `top, right, bottom, left`:

Estas propiedades definen el desplazamiento exacto de un elemento de su posición. Se utilizan en conjunto con valores de la propiedad position como relative, absolute, fixed, y sticky.

**Ejemplo:** Si deseas desplazar un elemento 20px desde la parte superior y 15px desde la derecha de su posición original, puedes hacerlo de la siguiente manera:

```css
.elemento {
  position: relative;
  top: 20px;
  right: 15px;
}
```

## 🛠️ Implementación en el proyecto

### Estilizando la sección de Animes

Para presentar la Animes de manera visual y organizada, nos encontramos con la necesidad de darle ciertas propiedades específicas a los elementos que la componen. Agrega el siguiente código para lograr este objetivo.

```css
#animes ul {
  padding: 0;
}

#animes li {
  display: inline-block;
  width: 30%;
  margin: 1%;
}
```

Explicación:

-   **`display: inline-block;`**: Por defecto, los elementos de lista (`<li>`) son de tipo `block`, lo que significa que ocupan toda la línea y cada nuevo elemento de lista se presenta en una nueva línea. Al usar `display: inline-block`, estamos diciendo que queremos que los elementos se alineen uno al lado del otro, como lo hacen los elementos `inline`, pero con la capacidad de ajustar su ancho y alto, algo que no es posible con un simple `display: inline`.

-   **`width: 30%;`**: Establecemos un ancho para cada elemento de lista que representa un álbum. Con esto, nos aseguramos de que tres álbumes (aproximadamente) se muestren en una línea (3 x 30% = 90%), dejando espacio para los márgenes.

-   **`margin: 1%`**;: Agregamos un pequeño margen alrededor de cada álbum para que no estén pegados entre sí y haya espacio visual entre ellos. Esto es esencial para la legibilidad y estética de la presentación.

Muy bien las imagenes se muestran horizontalmente, pero aun no se ven posicionadas de una manera ordenada. Agreguemos más código:

```css
#animes img {
  width: 80%;
  margin: 10px auto 20px auto;
  display: block;
}
```

Explicación:

-   `width: 80%;`: Las imágenes de los álbumes dentro de cada elemento de lista ocuparán el 80% del ancho del `<li>` en el que se encuentran. Esto deja algo de espacio alrededor de la imagen, proporcionando un respiro visual y evitando que la imagen se sienta apretada dentro de su contenedor.

-   `margin: 10px auto 20px auto;`: Estamos definiendo los márgenes de la imagen. Con "auto" para los márgenes izquierdo y derecho, estamos centrando la imagen dentro del elemento `<li>`. El valor `10px` para el margen superior proporciona un pequeño espacio entre la parte superior del `<li>` y la imagen, mientras que `20px` en la parte inferior proporciona un espacio más amplio, dando importancia visual a la imagen.

-   `display: block;`: Por defecto, las imágenes tienen un display `inline`, lo que puede provocar problemas con márgenes y alineación. Al establecerlo en `block`, garantizamos que la imagen se comportará como un bloque, facilitando el manejo de márgenes y centrado.

Finalmente, agreguemos un poco más de código para estilizar los textos de la sección:

```css
#animes {
  text-align: center;
}

#animes h2 {
  text-align: left;
}
```

### Ajustando el video y su iframe

Ahora enfoquemosnos en la sección de video, agrega el siguiente código para asegurarnos que el video y su contenedor se muestren adecuadamente:

```css
iframe {
  max-width: 100%;
  display: block;
  margin: 20px auto;
}
```

Explicación:

-   **`max-width: 100%;`**: Esta propiedad asegura que el `iframe` nunca exceda el ancho de su contenedor. Al usar "`max-width`" en lugar de "`width`", permitimos que el iframe sea responsivo. Si el contenedor tiene un ancho menor que el ancho original del `iframe`, el `iframe` se ajustará para encajar en ese espacio, pero no se expandirá más allá de su ancho original si el contenedor es más grande.

-   **`display: block;`**: Por defecto, los iframes tienen un comportamiento `inline`, similar al de las imágenes. Esto puede llevar a problemas inesperados con el espaciado y la alineación. Al definir el `iframe` como un elemento de bloque, ocupará toda la línea y no tendrá ningún espacio blanco extra alrededor, como sucede con los elementos `inline`. Además, esto nos facilita centrar el `iframe` en su contenedor.

-   **`margin: 20px auto;`**: Con esta propiedad, estamos dando un margen de `20px` en la parte superior e inferior del `iframe`. El valor "`auto`" para los márgenes izquierdo y derecho es una técnica comúnmente usada para centrar elementos de bloque horizontalmente dentro de su contenedor. Así, el video aparecerá centrado y con un adecuado respiro visual respecto a otros elementos en la página.

### Diseñando un formulario sencillo

Crear un formulario fácil de completar y visualmente agradable es esencial para una buena experiencia del usuario. Agrega el siguiente código para lograr esto:

```css
form {
  margin: 20px 0;
}

label,
input[type="text"],
input[type="email"] {
  display: block;
  margin: 10px 0;
}
```

Explicación:

-   **`form { margin: 20px 0; }`**: Este código añade un margen de `20px` tanto en la parte superior como en la inferior del formulario. Este espacio extra ayuda a que el formulario se destaque y no se sienta apretado o demasiado pegado a otros contenidos de la página.

-   **`display: block;`**: Por defecto, las etiquetas (`label`) y los campos de entrada (`input`) tienen comportamientos diferentes en cuanto a su visualización. Al aplicar `display: block`, nos aseguramos de que tanto las etiquetas como los campos de entrada se muestren en su propia línea, ocupando todo el ancho disponible. Esto hace que el formulario sea más legible y fácil de completar, ya que los usuarios no tendrán que buscar el campo correspondiente a cada etiqueta.

-   **`margin: 10px 0;`**: Este margen se aplica a cada etiqueta y campo de entrada. Establecer un margen en la parte superior e inferior garantiza que haya un espacio adecuado entre cada elemento del formulario. Esto no solo mejora la estética del diseño, sino que también hace que el proceso de completar el formulario sea más intuitivo y menos abrumador para el usuario.

## 📝 Resumen y pasos a seguir

¡Muchas Felicidades! En éste modulo hemos adentrado en el poder y la flexibilidad de las propiedades de `display` y `position` en CSS, permitiéndonos tener un mayor control sobre cómo se organizan y muestran los elementos en nuestra página.

En el próximo módulo, aprenderemos sobre tipografía y fondos en CSS... y avanzaremos aún más en el refinamiento de nuestro proyecto web.
