# Módulo 6: Detalles Tipográficos y Background

## Introducción:

El diseño tipográfico y los fondos son fundamentales para transmitir la identidad y el tono de un sitio web. Este módulo te proporcionará las herramientas para elegir y estilizar fuentes y trabajar con diferentes tipos de fondos, mejorando así la experiencia visual del usuario.

## 📌 Agenda

-   Concenptos:
    -   Propiedades de Fuente
    -   Uso y Conexión de Fuentes Web
    -   Propiedades de Fondo
    -   Texto
-   Implementaciónen el Proyecto:
    -   Agregando Fuentes Web
    -   Finalizando el Header
    -   Finalizando la sección de Frases
    -   Finalizando el Footer

## 📚 Conceptos

### Propiedades de Fuente:

Las propiedades tipográficas en CSS nos permiten controlar cómo se muestra el texto en un sitio web.

-   **`font-family`**: Define la familia tipográfica para el texto.
-   **`font-size`**: Establece el tamaño del texto.
-   **`font-weight`**: Controla el grosor de la fuente.
-   **`font-style`**: Define estilos específicos para la fuente, como itálica.
-   **`line-height`**: Controla el espacio entre líneas de texto, mejorando la legibilidad.
-   **`letter-spacing`**: Ajusta el espacio entre caracteres, que puede ser útil para títulos o estilos específicos.

Ejemplo:

```css
p {
  font-family: Arial, sans-serif;
  font-size: 2rem;
  font-weight: bold;
  font-style: italic;
  line-height: 1.5;
  letter-spacing: 2px;
}
```

### Uso y Conexión de Fuentes Web:

Las fuentes web permiten a los diseñadores utilizar tipografías específicas que no están instaladas por defecto en las computadoras de los usuarios.

[Google Fonts](https://fonts.google.com/) es una de las bibliotecas más populares para fuentes web. Su uso es simple:

1. Elige la fuente que te guste.
2. Añade la URL proporcionada en el <link> dentro del <head> de tu HTML.
3. Utiliza la propiedad `font-family` en tu CSS para aplicar la fuente.

Ejemplo:

En el código HTML agregamos el `<link>` que Google Fonts proporciona para la fuente que queremos usar en nuestro proyecto:

```html
<link href="https://fonts.googleapis.com/css2?family=Open+Sans&display=swap" rel="stylesheet">
```

Después, en el código CSS podemos aplicar la fuente de Google fontas a través de la propiedad `font-family`:

```css
body {
  font-family: 'Open Sans', sans-serif;
}
```

### Texto

Manipular el texto puede cambiar drásticamente la apariencia y legibilidad de tu contenido. Vamos a sumergirnos en algunas de esas herramientas:

-   **`text-align``**: Controla cómo se alinea el texto.
-   **`text-decoration``**: Añade o elimina decoraciones, como subrayados.
-   **`text-transform``**: Cambia la capitalización del texto.

Ejemplo:

En el siguiente código estamos alineando todos los enlaces en el centro, quitando el subrayado, y cambiando el texto a mayusculas.

```css
a {
  text-align: center;
  text-decoration: none;
  text-transform: uppercase;
}
```

### Propiedades de Fondo

Los fondos pueden añadir un toque visual atractivo y ayudar a segmentar el contenido. CSS proporciona una variedad de propiedades para controlar el aspecto del fondo de un elemento. Veamos algunas de las más utilizadas:

-   **`background-color`**: Define el color de fondo.

Ejemplo:

```css
div.blue-bg {
  background-color: #3498db;
}
```

-   **`background-image``**: Añade una imagen como fondo.
-   **`background-size``**: Controla cómo se muestra la imagen.

Ejemplo:

```css
div.banner {
  background-image: url('path/to/image.jpg');
  background-size: cover;
}
```

#### Uso de `linear-gradient` y `url` en conjunto

Cuando se trata de estilizar fondos en CSS, puedes combinar diferentes técnicas para lograr efectos visuales interesantes. La propiedad `background-image` permite superponer múltiples imágenes o gradientes. Por ejemplo:

```css
header {
    background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("img/ejemplo.jpeg");
}
```

En este ejemplo:

-   `linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)` crea un "filtro" negro con una opacidad del 50%. Imagina que es como una capa transparente de color negro que colocamos encima de una imagen.
-   `url("img/ejemplo.jpeg")` es simplemente la imagen que quieres mostrar de fondo.

Al usar estos dos valores juntos, colocas la imagen ejemplo.jpeg como fondo, pero encima de ella, hay una capa semi-transparente de color negro. Esto puede ayudar a que cualquier texto que coloques encima sea más legible, porque el fondo está ligeramente oscurecido por el "filtro" negro.

## 🛠️ Implementación en el proyecto

### Agregando Fuentes Web

Para hacer nuestra página más interesenta vamos a utilizar distintas tipografías de Goolge Fonts:

-   Para los headings: [Barlow Condensed - Regular](https://fonts.google.com/specimen/Barlow+Condensed?query=barlo)
-   Para el body: [Rasa - Light](https://fonts.google.com/specimen/Rasa?query=rasa)
-   Para los botones: [Barlow - SemiBold](https://fonts.google.com/specimen/Barlow?query=barlow)

Para poder utilizar estas tipografías, necestiamos agregar el siguiente `<link>` dentro del `<head>` de nuestro archivo `index.html`

```html
    <head>
        <!-- ... Otro codigo -->
        <link rel="stylesheet" href="styles.css" />
        <link href="https://fonts.googleapis.com/css?family=Barlow+Condensed|Barlow:600|Rasa:300,500" rel="stylesheet">
  </head>
```

Ahora si, dentro de `styles.css`, podemos agregar código para utilizar estas tipografías:

```css
body {
  font-family: "Rasa", serif;  /* Nuevo*/
  font-weight: 300; /* Nuevo*/
  background-color: #f0ede6;
  color: #333;
  line-height: 1.6;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Barlow Condensed", sans-serif; /* Nuevo*/
  font-weight: 400; /* Nuevo*/
  text-transform: uppercase;
}

nav a:hover {
  color: #000000;
  padding: 5px 10px;
  background-color: #d9e3da;
  font-family: "Barlow", sans-serif; /*Nuevo */
  font-weight: 600; /*Nuevo */
  font-size: 13px;
  text-transform: uppercase;
}

.estilo-boton {
  background-color: #d9e3da;
  font-family: "Barlow", sans-serif; /* Nuevo*/
  font-weight: 600; /*Nuevo */
  font-size: 13px;
  text-transform: uppercase;
  letter-spacing: 3px;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  text-decoration: none;
}

footer a:hover {
  color: #000000;
  padding: 5px 10px;
  background-color: #d9e3da;
  font-family: "Barlow", sans-serif; /*Nuevo */
  font-weight: 600; /*Nuevo */
  font-size: 13px;
  text-transform: uppercase;
  text-decoration: none;
}
```

### Finalizando el Header

Para que el texto de nuestro encabezado se vea y lea mejor, vamos a darle un toque oscuro a la imagen de fondo. Así, las letras saltarán a la vista y será más fácil de leer.

```css

/* Header */
header {
  background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(13, 13, 13, 0.9)),
    url("/img/animes.jpg"); /* Nuevo */
  background-size: cover;
  height: 600px;
  color: #fff;
}
```

Ahora vamos a poner el texto al centro y ajustar un poco los espacios y tamaños de letra para que todo quede más ordenado:

```css
/* Header */
header {
  background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(13, 13, 13, 0.9)),
    url("/img/animes.jpg");
  background-size: cover;
  height: 600px;
  color: #fff;
  position: relative; /* Nuevo */
  text-align: center; /* Nuevo */
}

/* Todo el siguiente código es Nuevo */
.content-center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 80%;
}

header h1 {
  font-size: 80px;
}

header p {
  font-size: 20px;
  margin: 20px;
}
```

### Finalizando la sección de Frases

Vamos a añadir una imagen de fondo a la sección de frases. Para que el texto destaque y se lea claramente, le pondremos un filtro oscuro. Y para que la imagen se ajuste perfectamente y ocupe todo el espacio, estableceremos su tamaño en "cover".

```css
/* Frases */
#frases {
  background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(13, 13, 13, 0.9)),
  url("https://media.tenor.com/7ZzPY3wgX_4AAAAC/zero-two-002.gif"); /*Nuevo*/
  background-size: cover; /*Nuevo*/
  height: 800px;
  color: #fff;
  position: relative;
  text-align: center;
}
```

### Finalzando el Footer

Finalmente, vamos a centrar el texto del footer. Le añadiremos un poco de espacio alrededor, usando padding, para darle un aspecto más pulido y estructurado

```css
/* Footer */
footer {
  background-color: #000000;
  color: #fff;
  text-align: center; /*Nuevo*/
  padding: 1em 0; /*Nuevo*/
}
```

## ¡Felicidades por completar el proyecto!

Llegar hasta aquí no es poca cosa, y mereces reconocimiento por el esfuerzo y la dedicación que has invertido. A lo largo de este proyecto, has recorrido un camino extenso y enriquecedor en el mundo del diseño y desarrollo web.

Este es solo el comienzo de tu viaje en el mundo del desarrollo web. Sigue adelante, continúa aprendiendo y, sobre todo, ¡disfruta de cada paso en este emocionante camino!
