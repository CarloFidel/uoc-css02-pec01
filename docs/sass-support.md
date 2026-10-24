# Sass para la PEC 1

Sass es un lenguaje que se escribe en ficheros `.scss` y, al ejecutar `npm run dev` o `npm run build`, Parcel lo convierte en CSS normal. El navegador nunca lee Sass: lee el CSS resultante.

La PEC pide cinco cosas, usadas de verdad en el proyecto:

1. Variables
2. Anidado
3. Una función escrita por ti
4. Parciales
5. Importación de esos parciales

Este boilerplate ya usa las cuatro primeras piezas de la lista salvo la función propia. Abajo se ve cada una sobre los ficheros de `src/assets/styles/`.

## Cómo llega el estilo a la página

`src/index.html` enlaza un solo fichero:

```html
<link rel="stylesheet" type="text/css" href="./assets/styles/main.scss" />
```

`main.scss` no contiene reglas. Solo carga otros ficheros. Esos ficheros se llaman parciales. Parcel los junta y entrega un CSS.

```text
index.html
  └── main.scss
        ├── _dependencies.scss
        └── layouts/_home.scss
              └── _variables.scss
```

## 1. Variables

Una variable guarda un valor para reutilizarlo. El nombre empieza por `$`. Se declara con `:` y cierra con `;`.

En `src/assets/styles/_variables.scss` ya existen:

```scss
$uoc-corporate: #000078;
$uoc-masterbrand: #73edff;
$mqMinWidth: 420px;
```

Sirven para no repetir el mismo color o el mismo ancho en varias reglas. Si cambias `$uoc-corporate`, cambian todos los sitios que la usan.

Para usarla hace falta cargar el parcial (eso es la importación, más abajo). En `layouts/_home.scss` se usa así:

```scss
color: variables.$uoc-corporate;
```

`variables` es el nombre del fichero, sin `_` y sin `.scss`. El punto separa el fichero del nombre de la variable. Si la variable y la regla están en el mismo fichero, se escribe solo `$uoc-corporate`.

Una variable puede guardar un color, un tamaño, una fuente o el resultado de un cálculo. Esta línea del mismo fichero calcula un color a partir de otro:

```scss
$uoc-bg: color.scale($uoc-masterbrand, $lightness: 70%);
```

`color.scale` es una función que ya trae Sass. No cuenta como la función que la PEC te pide escribir.

## 2. Anidado

El anidado escribe una regla dentro de otra. Sass la convierte en un selector CSS más largo.

En `layouts/_home.scss` el `@media` está dentro de `.uoc-title`:

```scss
.uoc-title {
  font-size: 24px;

  @media (min-width: variables.$mqMinWidth) {
    font-size: 36px;
  }
}
```

El CSS que acaba leyendo el navegador equivale a esto:

```css
.uoc-title {
  font-size: 24px;
}

@media (min-width: 420px) {
  .uoc-title {
    font-size: 36px;
  }
}
```

También se anidan selectores. Dentro de un bloque, `&` significa «el selector de fuera»:

```scss
.card {
  padding: 1rem;

  &__title {
    font-size: 1.5rem;
  }
}
```

Sass lo convierte en `.card__title`. Ese patrón encaja con BEM (`bloque__elemento`), si al final eliges esa metodología.

Dos niveles se leen bien. A partir de tres, el selector se vuelve difícil de seguir y más específico de lo necesario.

## 3. Función escrita por ti

Una función toma un valor y devuelve otro. Se declara con `@function`, termina con `@return` y luego se llama desde una propiedad, como si fuera una variable.

Esta todavía no está en el proyecto. Hay que crearla y usarla. Un ejemplo suficiente para la PEC, un paso de espaciado a partir de un número:

```scss
@use "sass:math";

@function space($step) {
  @return math.div($step, 2) * 1rem;
}

.card {
  padding: space(4);
}
```

`space(4)` devuelve `2rem`. `math.div(4, 2)` divide 4 entre 2. En Sass actual la división se escribe así, con el módulo `math`, y no con el símbolo `/`.

La función puede vivir en el mismo parcial que la usa, o en un parcial aparte (por ejemplo `_tools.scss`) cargado con `@use`. Si está en otro fichero, se llama con el nombre de ese fichero delante: `tools.space(4)`.

Para que cuente en la PEC tiene que cumplirse esto:

- La escribes tú con `@function`. `color.scale` y el resto de funciones del lenguaje no valen.
- Tiene al menos un parámetro (aquí, `$step`).
- Alguna propiedad real la llama (`padding: space(4)`). Si nadie la llama, no está aplicada.

## 4. Parciales

Un parcial es un fichero Sass pensado para ser cargado por otro, no para enlazarse desde el HTML. Su nombre empieza por `_`.

En este proyecto:

| Fichero | Qué guarda |
| --- | --- |
| `_variables.scss` | Valores reutilizables |
| `_dependencies.scss` | Librerías externas, como Font Awesome |
| `layouts/_home.scss` | Reglas de la página |

`main.scss` no lleva `_` porque es el punto de entrada: el único que enlaza `index.html`. El comentario del propio fichero pide no poner reglas ahí.

Cada parcial debería tener una sola responsabilidad. Si la metodología que elijas (SMACSS o ITCSS) pide otras carpetas, los parciales se mueven a esas carpetas y se explica en la memoria. El HTML sigue enlazando solo `main.scss`.

## 5. Importación

Importar es cargar un parcial desde otro fichero. En este boilerplate se hace con `@use`.

`main.scss` carga la página y las dependencias:

```scss
@use "dependencies";
@use "layouts/home";
```

`layouts/_home.scss` carga las variables:

```scss
@use "../variables";
```

Reglas de `@use`:

- Se escribe al principio del fichero.
- Se omite el `_` y la extensión: `"variables"` encuentra `_variables.scss`.
- `"layouts/home"` encuentra `layouts/_home.scss`.
- `"../variables"` sube una carpeta, de `layouts/` a `styles/`.
- Lo cargado queda detrás de un nombre. Por eso el color se escribe `variables.$uoc-corporate` y no `$uoc-corporate`.
- Sass carga cada fichero una sola vez. Un segundo `@use` del mismo parcial no lo duplica.

`_dependencies.scss` usa la otra forma, la antigua:

```scss
@import "npm:@fortawesome/fontawesome-free/css/all.css";
```

`@import` vuelca el CSS de Font Awesome en el resultado, sin namespace. El módulo 1 usa `@import` para esta librería. El código Sass nuevo del boilerplate va con `@use`, que es lo que ya hace `main.scss`. En la memoria conviene explicar las dos: `@use` para tus parciales y `@import` para el CSS de la dependencia.

## Qué mirar en cada fichero

- `_variables.scss`: declaraciones `$…`.
- `layouts/_home.scss`: `variables.$…` y un `@media` anidado dentro de una clase.
- `main.scss`: solo `@use`, sin reglas.
- `_dependencies.scss`: el `@import` de Font Awesome.
- Una `@function` nueva, llamada desde alguna propiedad. Este es el hueco que falta.
