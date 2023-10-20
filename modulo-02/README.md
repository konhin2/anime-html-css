# Módulo 2: Conociendo los selectores

## Agenda

-   **Conceptos:**

    -   Selector Universal, de clase y de ID
    -   Selectores de descendientes (espacio en blanco)
    -   Introducción a border, margin y padding

-   **Implementación en el proyecto:**

    -   Aplicación de un reset básico para navegadores
    -   Estilización de la navegación utilizando selectores de descendientes
    -   Estilización de botones usando selectores de clase
    -   Estilización de Secciones Específicas usando Selectores de ID

-   **Resumen y siguientes pasos**

## Conceptos

En el módulo anterior, seleccionaste elementos a partir de su tipo (`p`, `body`, etc.). Sin embargo, CSS ofrece selectores más específicos para tener un mayor control sobre los elementos:

### Selector Universal

Representado por el símbolo `*`, aplica estilos a todos los elementos en la página.

```css
* {
    box-sizing: border-box;
}
```

En este ejemplo, todos los elementos en la página usarán box-sizing: border-box;, lo que afecta cómo se calculan las dimensiones del elemento.

### Selector de Clase

Representado por un punto `.` seguido del nombre de la clase. Aplica estilos a todos los elementos que tienen esa clase.

```html
<p class="destacado">Este parrafo tiene la clase "destacado".</p>
```

```css
.destacado {
    color: blue;
}
```

Con el código anterior, todos los elementos con la clase destacado tendrán el texto en color azul.

### Selector de ID

Representado por un # seguido del nombre del ID. Aplica estilos al único elemento que tenga ese ID.

```html
<div id="encabezado">Encabezado principal</div>
```

```css
#encabezado {
    font-size: 24px;
    font-weight: bold;
}
```

Aquí, el elemento con el ID encabezado tendrá un tamaño de fuente de 24px y un peso de fuente en negrita.

### Selectores de Descendientes

Permiten seleccionar un elemento basado en su relación ancestral. Si quieres seleccionar todos los `li` dentro de un `nav`, utilizarías:

```css
nav li {
    list-style-type: none;
}
```

En este caso, estamos seleccionando todos los elementos `li` que son descendientes directos o indirectos de un elemento `nav` y les estamos quitando cualquier estilo de lista.

### Introducción a border, margin y padding

Las propiedades border, margin y padding son esenciales para controlar el espacio alrededor y dentro de los elementos. Por ejemplo:

```css
nav ul {
    border: 1px solid black;  /* Borde alrededor del elemento */
    margin: 10px;             /* Espacio externo alrededor del elemento */
    padding: 10px;            /* Espacio interno entre el contenido y el borde del elemento */
}
```

Con este código, estamos añadiendo un borde negro alrededor de `nav ul`, dejando un espacio de `10px` alrededor del elemento (`margin`) y un espacio de `10px` entre el contenido y el borde (`padding`).

Con estos nuevos conceptos en tu arsenal, estás listo para tener un control más preciso sobre el diseño y la apariencia de tu página. ¡Vamos a continuar agregando estilos a nuestro proyecto y verás cómo estos selectores y propiedades marcan la diferencia!

## Implementación en el proyecto

### Aplicación de un reset básico para navegadores

Cada navegador tiene su conjunto predeterminado de estilos que se aplican a los elementos HTML. Sin embargo, estos estilos varían de un navegador a otro, lo que puede conducir a inconsistencias visuales en nuestro diseño.

Agrega el siguiente código en `styles.css` para hacer un "reset" de los estilos predeterminados de los navegadores:

```css
/* Reset básico para navegador */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

Con el selector universal `*,` estamos asegurándonos de que todos los elementos tengan un `margin` y un `padding` de `0`, eliminando cualquier espacio predeterminado. También estamos aplicando `box-sizing: border-box`, que cambia la forma en que se calculan las dimensiones del elemento, considerando cualquier borde y padding en el tamaño total del elemento.

## Estilización de la navegación utilizando selectores de descendientes

Para estilizar la barra de navegación de nuestro proyecto, necesitamos agregar estilo a la lista (`ul`) que está dentro de nuestra etiqueta de navegación (`nav`). Si simplemente usáramos el selector `ul`, todos los elementos `ul` en el proyecto se verían afectados. Pero al usar `nav ul`, nos aseguramos de que solo las listas dentro de la etiqueta nav reciban estos estilos.

Agrega el siguiente código en `styles.css` para agregar estilo a la barra de navegación:

```css
/* Navegación */
nav ul {
  background-color: #000000;  /* Color de fondo negro */
  list-style-type: none;      /* Elimina los bullets predeterminados de la lista */
  padding: 1em 0;             /* Agrega espacio en la parte superior e inferior */
  text-align: center;         /* Centra el contenido de la lista */
}

nav li {
  display: inline;            /* Coloca los elementos de la lista en una sola línea */
  margin-right: 20px;         /* Espacio a la derecha de cada elemento para separación */
}

nav a {
  color: #ffffff;             /* Color blanco para los enlaces */
  text-decoration: none;      /* Elimina el subrayado de los enlaces */
}
```

Observa cómo hemos usado `nav ul`, `nav li`, y `nav a`. Estos son ejemplos de selectores de descendientes. Al decir `nav ul`, estamos seleccionando específicamente cualquier lista no ordenada (`ul`) que sea un descendiente directo o indirecto de un elemento `nav`.

Este enfoque garantiza que los estilos aplicados no afecten a otros elementos `ul`, `li` o `a` en otras partes del sitio.

## Estilización de botones usando selectores de clase

Los selectores de clase nos brindan una manera de estilizar elementos basándonos en una característica común: la clase que les asignamos. Esta es una técnica poderosa porque nos permite reutilizar estilos en diferentes partes de nuestro sitio sin tener que repetir código.

Observa que `index.html`, tenemos varios elementos con `class="estilo-boton"` como por ejemplo, los elemento `<a>` dentro de la sección de encabezado y Animes, o el boton dentro del formulario. Podemos utilizar `.estilo-boton` para aplicar un conjunto consistente de estilos a todos esos elementos sin importar dónde se encuentren.

Agrega el siguiente código en `styles.css` para añadir estilo a todos los elementos con `class="estilo-boton"`:

```css
/* Estilo para Botones */
.estilo-boton {
  background-color: #d9e3da;  /* Color de fondo claro para los botones */
  font-size: 13px;            /* Tamaño de fuente */
  text-transform: uppercase;  /* Convierte el texto en mayúsculas */
  letter-spacing: 3px;        /* Espacio entre las letras */
  border: none;               /* Elimina el borde predeterminado del botón */
  padding: 10px 20px;         /* Espacio interno para el botón */
  cursor: pointer;            /* Cambia el cursor a una mano cuando se pasa sobre él */
  text-decoration: none;      /* Elimina cualquier subrayado */
}
```

## Estilización de Secciones Específicas usando Selectores de ID

A medida que tu sitio web crece, es posible que quieras aplicar estilos específicos a secciones individuales. Una forma eficiente de hacerlo es utilizando selectores de ID, los cuales permiten seleccionar y estilizar un elemento específico basado en su atributo `id`.

Agrega el siguiente código en `styles.css` para estilizar distintas secciones de nuestra pagina:

```css
/* Secciones */
#historia,
#animes,
#datos-curiosos,
#animes-populares,
#video,
#suscripcion {
  margin: 20px;               /* Espacio externo alrededor de la sección */
  padding: 20px;              /* Espacio interno entre el contenido y el borde de la sección */
  background-color: #fff;    /* Color de fondo blanco para resaltar el contenido */
}
```

En el código anterior, utilizamos selectores de ID, representados por el símbolo `#`. Por ejemplo, `#historia` selecciona el elemento con el atributo `id="historia"`. De esta manera, logramos aplicar estilos a secciones individuales como Historia, Animes, y más.

Las propiedades `margin`, `padding` y `background-color` son empleadas para darle a cada sección un aspecto distintivo y bien estructurado. Con `margin` controlamos el espacio externo alrededor de la sección, con `padding` gestionamos el espacio interno entre el contenido y el borde de la sección, y `background-color` nos da un fondo blanco, lo que ayuda a resaltar el contenido.

## Resumen y siguientes pasos

¡Gran trabajo! Con estos nuevos conceptos en tu arsenal, estás listo para tener un control más preciso sobre el diseño y la apariencia de tu página. En el siguiente módulo nos enfocaremos en agregar un poco de interactividad al proyecto utilizando estilos dinámicos.
