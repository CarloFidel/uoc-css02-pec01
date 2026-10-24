# Módulo 2: Guías de estilo y metodologías CSS

En el segundo módulo de la asignatura Herramientas HTML y CSS II conoceremos la importancia de escribir código de calidad, más flexible, reutilizable, comprensible y manejable, para mejorar nuestros proyectos.

Si trabajáis con equipos grandes de desarrollo, o en proyectos de código abierto, el código que se genere deberá cumplir con unos estándares que permitan que cualquier miembro del equipo sea capaz de entender y generar código con las mismas características. Se debe adoptar, pues, un estilo de programación, que decida, por ejemplo, cómo se ordenan los ficheros, qué tipo de nombre poner a los elementos, o qué tipo de propiedades se prefiere usar respecto de otras. Estas decisiones pueden ser más o menos justificadas o arbitrarias, pero el hecho de contar con una preferencia clara causa que el código generado siempre sea coherente entre sí.

En UOC Boilerplate, por ejemplo, os habéis encontrado con algunas decisiones ya tomadas: la mayoría de herramientas ya estaban escogidas por adelantado, y la estructura de ficheros y carpetas la habéis respetado como estaba. Pero a partir de aquí tenéis que tomar algunas decisiones, como por ejemplo los nombres de las clases de los elementos de vuestras páginas, o la sintaxis de HTML y CSS que creáis oportuna.

En este módulo conoceremos algunas guías de estilo y distintas metodologías que os pueden ayudar a entender mejor los lenguajes y a tomar decisiones que os lleven a escribir código más limpio, coherente y ordenado. Algunas de las decisiones sobre las que leeremos pueden ser incluso contradictorias, pero es bueno conocer distintos estilos de programación para saber qué ventajas e inconvenientes tiene cada uno. También conoceremos una herramienta que nos permitirá automatizar parte de estas tareas de estilo.

Como siempre, los materiales de aprendizaje los encontraréis en la sección Recursos básicos, y en la sección Contenidos y actividades encontraréis diferentes ideas y propuestas de actividades sencillas para consolidar los conocimientos adquiridos con los recursos propuestos. Si tenéis alguna duda sobre alguna de las actividades propuestas o no sabéis la respuesta a alguna de las preguntas, abrid un hilo en el foro para hablarlo.

## Objetivos

- Conocer distintas guías de estilo para mejorar la calidad del código CSS y HTML.
- Conocer distintas metodologías con propuestas de nomenclatura y ordenación del CSS para generar un código de calidad.
- Conocer Stylelint para automatizar la comprobación de estilos de las hojas de estilos del proyecto.

## Recursos básicos

Las lecturas que os llevarán a alcanzar los objetivos de aprendizaje de este módulo son las siguientes:

- [Why Coding Style Matters](https://www.smashingmagazine.com/2012/10/why-coding-style-matters/), de Nicholas C. Zakas, en Smashing Magazine.
- [Challenging CSS Best Practices](https://www.smashingmagazine.com/2013/10/challenging-css-best-practices-atomic-approach/), de Thierry Koblentz, en Smashing Magazine.
- Guías de estilo:
  - [CSS Guidelines](https://cssguidelin.es/), de Harry Roberts.
  - [Code Guide](http://codeguide.co/), de Mark Otto.
- Documentaciones:
  - [OOCSS](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)
  - [BEM](https://css-tricks.com/bem-101/)
  - [SMACSS](http://smacss.com/)
  - [ITCSS](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/)
  - [Stylelint](https://stylelint.io/)

> Como siempre, debéis tomar las documentaciones como referencia y no como lectura secuencial obligatoria, y solo deberéis entender y aprender lo necesario para este curso. Por estos motivos, os recomendamos la lectura de estos documentos y la realización de las actividades de acuerdo con las pautas propuestas en la sección Contenidos y actividades. Os alentamos a que, además, leáis y aprendáis todo aquello que os interese y complemente los contenidos de este curso.

## Contenidos y actividades

### Guías de estilo

#### Ideas clave

- Una guía de estilo propone convenciones sobre distintos aspectos del código: por ejemplo, el uso de nombres, de comentarios, de espacios o tabulaciones.
- El estilo de código de cada uno puede ser distinto, y también puede variar según el lenguaje de programación.
- Tanto si se trabaja individualmente como en equipo, es importante que se mantenga un estilo coherente para asegurarse de que el código es flexible, reutilizable, comprensible y manejable, y en definitiva, de mejor calidad.
- Las decisiones tomadas al crear una guía de estilo suelen estar justificadas (por ejemplo, la preferencia de clases respecto de IDs en el CSS), pero en otros casos son puramente estéticas o arbitrarias (por ejemplo, la preferencia de espacios o tabulaciones).

#### Actividad

Empieza leyendo el artículo [Why Coding Style Matters](https://www.smashingmagazine.com/2012/10/why-coding-style-matters/) de Nicholas C. Zakas en Smashing Magazine.

Accede a las [CSS Guidelines](https://cssguidelin.es/) de Harry Roberts. Lee la sección de introducción, donde se da una buena explicación de por qué son importantes las guías de estilo. Lee algunas de las secciones donde se dan las recomendaciones, como por ejemplo las de *Syntax and Formatting*, *CSS Selectors* o *Specificity*.

Otra guía de estilo bastante conocida es la de Mark Otto, creador de Bootstrap. Estas recomendaciones de estilo son coherentes con el estilo de programación del código base de Bootstrap. Esta guía propone recomendaciones de HTML y CSS. Accede a la [Code Guide by @mdo](http://codeguide.co/) y consulta su contenido.

Después de haber revisado estas dos guías de estilo, responde las siguientes preguntas:

- ¿Qué te parecen las recomendaciones?
- ¿Crees que las decisiones están justificadas?
- ¿Crees que es ventajoso usar una guía de estilo?
- ¿Cuál de las dos guías te parece más completa? ¿Y más coherente? ¿Se parece alguna a tu estilo de código? ¿Por cuál te decantarías si tuvieras que escoger una para tus proyectos?

Algunas empresas y proyectos de software libre también tienen publicadas sus propias guías de estilo con las aproximaciones que usan en sus proyectos. Echa un vistazo a las siguientes y mira si son más o menos completas y más o menos restrictivas que las otras dos:

- Airbnb: guía de estilo de CSS.
- WordPress: guía de estilo de HTML y guía de estilo de CSS.

### Metodologías CSS

#### Ideas clave

Una metodología CSS propone recomendaciones sobre cómo escribir código CSS de manera que sea más flexible, reutilizable, comprensible y manejable. En este módulo veremos cuatro metodologías distintas.

- **OOCSS** fue propuesta por Nicole Sullivan en 2008 y se basa en dos principios: la separación de la estructura del diseño, y la separación de contenedor y contenido.
- **BEM** es un sistema de nomenclatura de clases de CSS que permite la reutilización del código y la mejora de la modularidad y la estructuración de nuestro CSS.
- **SMACSS** (*Scalable and Modular Architecture for CSS*) fue desarrollada en 2011 por Jonathan Snook, y se basa en la organización de las reglas de CSS en cinco categorías: *base*, *layout*, *module*, *state* y *theme*.
- **ITCSS** (*Inverted Triangle CSS*) es una aproximación que se basa en dividir el código CSS en siete secciones (capas) que quedan dispuestas en forma de triángulo invertido (*settings*, *tools*, *generic*, *elements*, *objects*, *components*, *utilities*) según su especificidad y explicitud. Fue propuesta en 2016 por Lubos Ktmetko.

#### Actividad

Consulta la documentación siguiente sobre las metodologías:

- **OOCSS:** lee el artículo [An Introduction To Object Oriented CSS (OOCSS)](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/) de Louis Lazaris en Smashing Magazine.
- **BEM:** lee el artículo [BEM 101](https://css-tricks.com/bem-101/) de Robin Rendle en CSS-Tricks.
- **SMACSS:** lee la sección *Introduction* y las secciones del apartado *Core* de la documentación de [SMACSS](http://smacss.com/).
- **ITCSS:** lee el artículo [ITCSS: Scalable and Maintainable CSS Architecture](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/) de Lubos Ktmetko, en el que se propuso esta metodología por primera vez.

Después de haber consultado la documentación propuesta sobre estas cuatro metodologías, responde las siguientes preguntas:

- ¿Qué te parece cada una de las metodologías? ¿Qué ventajas o inconvenientes ves a cada una de ellas?
- ¿Todas las metodologías afectan sobre los mismos aspectos? ¿Cuál crees que es más completa? ¿Cuál crees que es más restrictiva?
- ¿Crees que algunas de las metodologías estudiadas pueden ser compatibles entre ellas?
- ¿Cuál o cuáles de estas metodologías crees que podrías aplicar en algún proyecto propio?

### Stylelint

#### Ideas clave

- Stylelint es una herramienta que analiza automáticamente nuestro código y lo valida en función de unas reglas de estilo predefinidas.
- Aunque hay distintas formas de utilizarlo, una aproximación coherente con lo que hemos trabajado es incorporarlo a las rutinas de UOC Boilerplate.

#### Actividad

Para empezar, lee la portada de la [documentación de Stylelint](https://stylelint.io/), donde se explica qué es, cómo funciona y cómo configurarlo. Todos los pasos a seguir están detallados con más profundidad en la guía de usuario, que puedes consultar como referencia.

Para incorporarlo a UOC Boilerplate, tendrás que seguir los siguientes pasos. En primer lugar, abre tu proyecto de pruebas o crea uno nuevo basado en UOC Boilerplate, y asegúrate de que tienes todas las dependencias instaladas.

Primero instala Stylelint:

```bash
npm install --save-dev stylelint
```

Como estamos usando la sintaxis SCSS de Sass, también deberás instalar `stylelint-scss`. Además, instalaremos una configuración base recomendada, `stylelint-config-recommended-scss`. Estas dos dependencias se pueden instalar de la misma forma:

```bash
npm install --save-dev stylelint-scss stylelint-config-recommended-scss
```

A continuación hay que configurar Stylelint según las decisiones tomadas. Hay que crear en la raíz del proyecto un fichero con nombre `.stylelintrc` (atención: el nombre de fichero empieza con un punto), e introducir un objeto de configuración, que puede ser como el siguiente:

```json
{
  "extends": ["stylelint-config-recommended-scss"],
  "rules": {}
}
```

Esta es la configuración base, pero para hacer cumplir las reglas de estilo que marcan las metodologías o guías de estilo debes personalizarla. Las reglas están documentadas en la sección de reglas de la guía de usuario de Stylelint, y se deben definir en la clave `rules` del fichero `.stylelintrc`. También puedes usar otras configuraciones por defecto que se correspondan con las metodologías o guías de estilo elegidas, o instalar los plugins que necesites.

Por ejemplo: si elegiste la metodología BEM, puedes usar la regla `selector-class-pattern` con una expresión regular para asegurar que las clases tienen nombres que sigan esta metodología:

```json
{
  "rules": {
    "selector-class-pattern": "^.[a-z]([a-z0-9-]+)?(__([a-z0-9]+-?)+)?(--([a-z0-9]+-?)+){0,2}$"
  }
}
```

Otro ejemplo: si elegiste la guía de estilo de @mdo, además de configurar las otras reglas que sean necesarias, puedes asegurar que se cumpla el orden de las declaraciones con la configuración de Stylelint `stylelint-config-recess-order`, instalándola con:

```bash
npm install --save-dev stylelint-config-recess-order
```

e introduciéndola en el fichero `.stylelintrc`:

```json
{
  "extends": [
    "stylelint-config-recess-order"
  ]
}
```

Por último, solo nos queda añadir Stylelint a las rutinas de UOC Boilerplate. En la sección `scripts` de `package.json` puedes crear una entrada nueva, siguiendo el mismo formato que las anteriores:

```json
{
  "scripts": {
    "stylelint": "stylelint src/**/*.scss"
  }
}
```

Una vez hecho esto, comprueba qué ocurre cuando ejecutas `npm run stylelint`. No te asustes si te aparecen muchas advertencias. Lo más probable es que haya alguna discrepancia entre tus estilos y las normas definidas. Con esta herramienta podrás comprobar cuáles son estas diferencias y qué hay que hacer para corregirlas. Si la ejecución finaliza sin ningún mensaje, significa que no hay ningún error de validación.

Por último, se puede incorporar la rutina que hemos creado a la rutina de *build*, de forma que solo podamos compilar para producción si las hojas de estilos pasan la validación de Stylelint. En la rutina `build` se ejecuta la herramienta `npm-run-all`, que nos permite ejecutar otras rutinas secuencialmente. Solo tienes que añadir la rutina de Stylelint a esta configuración:

```json
{
  "scripts": {
    "build": "npm-run-all clean stylelint parcel:build"
  }
}
```
