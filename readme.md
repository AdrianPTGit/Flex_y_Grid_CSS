# Uso de Grid y Flex en CSS

## 1. Flex CSS

- Al inicio en CSS se utilizaba para posicionar elementos en la página web (`static`, `relative`, `absolute`…), elementos en línea o en bloque, o la propiedad `float` para realizar maquetaciones, este sistema complica realizar páginas webs modernas, parta distintos dispositivos móviles, escritorio o resolución de pantalla.

> `Flex` o `Flexbox`: sistema de elementos flexible, permite que los elementos HTML se adapten y colocan automáticamente y  es más fácil personalizar el diseño de una pagina web.
Flex crea estructuras de una sola dimensión mediante CSS.

### 1.1. Conceptos de Flex

- **Contenedor**: Es el elemento padre que tendrá en su interior cada uno de los ítems flexibles. Observa que al contrario que muchas otras estructuras CSS, por norma general, en Flex establecemos las propiedades al elemento padre.

  - Eje **principal**: Los contenedores flexibles tendrán una orientación principal específica. Por defecto, el eje principal del contenedor flex es en horizontal (en fila).

  - Eje **secundario**: De la misma forma, los contenedores flexibles tendrán una orientación secundaria, perpendicular a la principal. Si la principal es en horizontal, la secundaria será en vertical (y viceversa).

- **Ítem**: Cada uno de los hijos que tendrá el contenedor en su interior.

Para activar el modo flex, utilizaremos sobre el elemento contenedor la propiedad `display`, y especificaremos el valor `flex` o `inline-flex`

| Tipo de elemento | Descripción                                                                 |
|------------------|------------------------------------------------------------------------------|
| `inline-flex`    | Establece un contenedor en línea, similar a `inline-block` (ocupa solo el contenido). |
| `flex`           | Establece un contenedor en bloque, similar a `block` (ocupa todo el ancho del padre). |

### 1.2. Dirección de los ejes

| Propiedad       | Valor                                   | Significado                             |
|-----------------|------------------------------------------|-----------------------------------------|
| `flex-direction`| `row` \| `row-reverse` \| `column` \| `column-reverse` | Cambia la orientación del eje principal. |

- Mediante la propiedad `flex-direction` podemos modificar la dirección del eje principal del contenedor para que se oriente en **horizontal** (valor por defecto) o en **vertical.** 
- También podemos incluir el sufijo `-reverse` para indicar que coloque los **ítems en orden inverso**.

| Valor           | Descripción                                                   |
|-----------------|----------------------------------------------------------------|
| `row`           | Establece la dirección del eje principal en horizontal.        |
| `row-reverse`   | Establece la dirección del eje principal en horizontal invertido. |
| `column`        | Establece la dirección del eje principal en vertical.          |
| `column-reverse`| Establece la dirección del eje principal en vertical invertido. |

```css
.container{
    display: flex;
    flex-direction: row;
    background: steelblue;
    padding-bottom: 10px;
    padding-top: 10px;
    padding-left: 10px;
    padding-right: 10px;
    margin-top: 20px;

}

.item{
    background-color: grey;
    height:300px ;
    width: 300px;
    margin-left: 6px;
    margin-top: 6px;
}
```

### 1.3. Contenedor flex multilínea

- flex se suele utilizar para estructuras de una sola dimensión, es decir, contenedores que sólo van en una dirección.
- Por defecto, si un elemento no cabe dentro de nuestro contenedor flex, los elementos se harán más pequeños **(son flexibles)** para ajustarlos al contenedor.
- Con la propiedad `flex-wrap` podemos cambiar este comportamiento y permitir que nuestro contenedor flex se desborde, convirtiéndose en un **contenedor flex multilínea.**

| Propiedad   | Valor                            | Significado                                      |
|-------------|----------------------------------|--------------------------------------------------|
| `flex-wrap` | `nowrap` \| `wrap` \| `wrap-reverse` | Evita o permite el desbordamiento (multilínea). |

| Valor          | Descripción                                                                 |
|----------------|------------------------------------------------------------------------------|
| `nowrap`       | Los ítems se ajustan para ocupar el tamaño del contenedor (no permite desbordamiento en múltiples líneas). |
| `wrap`         | Establece los ítems en modo multilínea (permite que se desborde el contenedor). |
| `wrap-reverse` | Establece los ítems en modo multilínea, pero en dirección inversa.          |

- En el caso de especificar `nowrap` (u omitir la propiedad flex-wrap) en el contenedor, los 3 ítems se mostrarían en una misma línea del contenedor (que es el comportamiento por defecto)

#### Atajo: Direccion ejes

- existe una propiedad de atajo llamada `flex-flow`, con la que podemos resumir los valores de las propiedades `flex-direction` y `flex-wrap`, especificándolas en una sola propiedad y ahorrándonos utilizar las propiedades concretas:

```css
.container {
  /* flex-flow: <flex-direction> <flex-wrap>; */
  flex-flow: row wrap;
}
```