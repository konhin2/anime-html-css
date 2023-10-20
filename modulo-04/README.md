# Módulo 4: Box Model y Unidades de Medida

## 📖 Introducción  
El diseño web se basa en una serie de cajas. Cada elemento es tratado como una caja rectangular, y esta naturaleza es esencial para la construcción y diseño de páginas web. En este módulo, exploraremos el "Box Model" o "Modelo de Caja" en CSS y las diferentes unidades de medida que nos permiten definir el tamaño, espacio y otros aspectos de estos elementos.

## 📌 Agenda
- Conceptos:
  - Propiedades del Box Model
  - Unidades de medida absolutas
  - Unidades de medida relativas
- Implementación en el proyecto:
  - Realzando la apariencia de las listas 
  - Mejorando la sección "Frases"
  - Diseño coherente para tablas
  - Resumen y pasos a seguir 


## 📚 Conceptos

### 1. Propiedades del Box Model

En CSS, todos los elementos son tratados como cajas rectangulares. Estas "cajas" determinan cómo se organiza y se presenta visualmente cada elemento en la página. Las características clave de estas cajas son controladas por ciertas propiedades:

- **padding**: Espacio entre el contenido del elemento y su borde.
- **border**: Define el borde alrededor del elemento.
- **margin**: Espacio entre el borde del elemento y los elementos circundantes.
- **width** y **height**: Define el ancho y alto del contenido del elemento.

```css
.caja {
    width: 300px;
    height: 150px;
    padding: 15px;
    border: 5px solid black;
    margin: 10px;
}
```

#### box-sizing
La propiedad `box-sizing` define cómo se calculan el ancho y el alto: si incluyen `padding` y `border` o no.

Hay dos valores principales para `box-sizing`:

- **content-box** (valor predeterminado): Con este valor, las propiedades width y height definen únicamente el tamaño del contenido del elemento. El padding y border se suman al tamaño final del elemento, haciendo que este sea más grande.

```css
.caja-content-box {
    box-sizing: content-box;
    width: 300px;
    height: 150px;
    padding: 15px;
    border: 5px solid black;
}
```
La caja en este ejemplo tendría un ancho total de 340px (300px de ancho + 15px de padding a la izquierda + 15px de padding a la derecha + 5px de borde a la izquierda + 5px de borde a la derecha) y un alto total de 190px (150px de alto + 15px de padding arriba + 15px de padding abajo + 5px de borde arriba + 5px de borde abajo).


- **border-box**: Con este valor, cualquier `padding` o `border` que agregues al elemento se incluirá en el valor definido para `width` o `height`. Es decir, el tamaño total del elemento (incluyendo `padding` y `border`) nunca excederá el `width` o `height` que especifiques.

```css
.caja-border-box {
    box-sizing: border-box;
    width: 300px;
    height: 150px;
    padding: 15px;
    border: 5px solid black;
}
```

Si utilizas `border-box`, la caja en este ejemplo tendrá un ancho total de `300px` y un alto total de `150px`, independientemente del `padding` y `border` añadidos.


### 2. Unidades de medida absolutas

Las unidades son esenciales para definir tamaños, espacios y otras medidas en CSS.

**px**: Los pixels (px) son unidades fijas que definen un tamaño específico en pantalla.

```css
p {
  font-size: 16px;
}
```

### 3. Unidades de medida relativas

Las unidades de medida relativa son dinámicas y dependen de otro valor para su cálculo.

- **em**: Esta es una unidad de medida relativa basada en el tamaño de fuente del elemento. Por ejemplo, si el tamaño de fuente es `16px`, entonces `1em` es igual a 16px. Es muy útil para diseños escalables y para mantener proporciones relativas entre elementos.

```css
p {
  font-size: 1.5em;  /* 1.5 veces el tamaño de fuente del padre */
}
```

- **%**: Representa un porcentaje relativo al tamaño del elemento padre. Por ejemplo, si un elemento padre tiene un ancho de `500px`, y un hijo tiene un ancho de `50%`, el hijo será de `250px`.

```css
.child {
  width: 50%;  /* Si el padre es de 500px, el hijo será de 250px */
}
```
Con estos nuevos conceptos en tu arsenal, estás listo para tener un control más preciso sobre el diseño y la apariencia de tu página.

## 🛠️ Implementación en el proyecto

Agreguemos más codigo CSS a nuestro proyecto para que la página se vea mejor.

### 1. Realzando la apariencia de las listas 
A fin de ofrecer una mejor lectura y presentación visual de las listas, implementaremos varios estilos:

- Tipo de viñeta: Utilizaremos el estilo disc para darle un aspecto clásico a las viñetas.
- Margen izquierdo: Añadimos un desplazamiento para que las viñetas no se peguen al borde.
- Separación vertical: Aumentamos el espacio entre cada ítem de la lista para mejorar la legibilidad.

```css
ul li {
  list-style-type: disc;
  margin-left: 20px;
  padding: 0.5em 0;
}
```

### 2. Mejorando la sección "Frases" 

Nuestro objetivo es que las frases se destaquen y sean el centro de atención:

- Alineación: Centramos el contenido para darle protagonismo.
- Tamaño de texto: Aumentamos el tamaño de las letras para que las frases sean fácilmente legibles.
- Espaciado: Agregamos márgenes para evitar que el texto parezca apretado.

```css
#frases {
  height: 600px;
  color: #fff;
  position: relative;
  text-align: center;
}

#frases h1 {
  font-size: 50px;
}

#frases p {
  font-size: 20px;
  margin: 20px;
}
```

### 3. Diseño coherente para tablas 
Queremos que las tablas sean legibles y tengan una apariencia limpia y organizada.

- Anchura: La tabla ocupará todo el ancho disponible para aprovechar el espacio.
- Borde: Usamos el estilo border-collapse para que los bordes de las celdas se fusionen, logrando una apariencia más limpia.
- Espaciado: Añadimos un padding a las celdas, garantizando que el texto no esté pegado a los bordes.lido.

```css
table {
  width: 100%;
  border-collapse: collapse;
}

th, td {
  padding: 10px;
  border: 2px solid #f0ede6;
}
```


## 📝 Resumen y pasos a seguir  

El Box Model y las unidades de medida son esenciales en el diseño web. Al comprenderlos y aplicarlos adecuadamente, garantizamos un diseño coherente y atractivo. Con este módulo, hemos añadido más detalles y refinamientos a nuestro proyecto, acercándonos cada vez más a un sitio web profesional y elegante.

En el próximo módulo, abordaremos aspectos más avanzados de CSS, y continuaremos construyendo y perfeccionando nuestro proyecto. ¡Estamos emocionados por seguir adelante en esta jornada