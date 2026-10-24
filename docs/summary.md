# Resumen de estudio para la PEC 1

Qué hay que estudiar de los módulos 1 y 2 para poder hacer la práctica. El detalle sigue en `docs/modulo01.md` y `docs/modulo02.md`. El avance del proyecto está en `docs/PEC1-CHECKLIST.md`.

La PEC pide una página sobre un libro, una película o una serie, hecha sobre UOC Boilerplate 3.14.0, con una dependencia externa, Sass (variables, anidado, una función escrita por ti, parciales e importación), una metodología y/o guía de estilo, Stylelint sin errores, `npm run build`, GitHub y Netlify. La memoria tiene que justificar esas decisiones.

## Módulo 1. Workflow

### Terminal, Node y npm

- [ ] Saber moverte por carpetas en el terminal y lanzar un comando. Basta el [Command line crash course](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line) hasta *A slightly more complex example*, más el resumen *TL;DR* de [Terminal for beginners!](https://medium.com/@grace.m.nolan/terminal-for-beginners-e492ba10902a).
- [ ] Comprobar la versión con `node -v` y `npm -v`. El módulo pide Node superior a 20.x. El `.nvmrc` de este boilerplate indica `v20.18.1`. Anota las dos versiones: entran en la memoria.
- [ ] Leer [Why Build Tools Are Essential for Modern Front-End Development](https://medium.com/@emre.deniz/why-build-tools-are-essential-for-modern-front-end-development-8298616687ed) para quedarte con el vocabulario: dependencia, *bundler*, preprocesador, *build*.
- [ ] En la documentación de npm, leer solo: qué es un paquete, instalar en local, desinstalar, actualizar y qué es `package.json`.
- [ ] Distinguir `npm install` (instala lo que ya lista `package.json` y crea `node_modules`) de `npm install <paquete>` (añade una dependencia nueva y la escribe en `package.json`).
- [ ] Distinguir dependencia de producción (`--save`, librería que usa la página) y dependencia de desarrollo (`--save-dev`, herramienta como Stylelint).

### UOC Boilerplate y Parcel

- [ ] Abrir `package.json` y saber explicar las dependencias que ya trae (Parcel, Sass, PostHTML, PostCSS, Sharp) y para qué sirve la clave `scripts`.
- [ ] Trabajar dentro de `src/`. El módulo dice que el resto de ficheros no se tocan salvo que sepas qué haces. En esta PEC sí se toca la raíz para Stylelint, el script de validación y, si hace falta, el `build`.
- [ ] Ejecutar `npm run dev` y saber qué hace: servidor en `http://localhost:8123`, recarga al guardar, sin minificar.
- [ ] Ejecutar `npm run build` y saber qué hace: genera `dist/` compilado, concatenado y minificado. Esa carpeta es la que se entrega y la que publica Netlify.
- [ ] Comparar `src/index.html` con `dist/index.html` (estructura, peso, HTML ya unido).
- [ ] Cambiar un color en `src/assets/styles/_variables.scss` y ver la recarga. Parar el servidor con `ctrl+c`.

### Dependencia externa

El ejemplo del módulo es Font Awesome. Sirve para la PEC. Si eliges otra librería, tienes que poder explicar el mismo recorrido: instalar, registrar en `package.json` e incorporarla al *bundle*.

- [ ] Instalar con `npm install --save @fortawesome/fontawesome-free` y mirar qué línea nueva aparece en `package.json`.
- [ ] Poner un icono en el HTML: `<i class="fas fa-university"></i>`.
- [ ] Importar la librería al final de `src/assets/styles/_dependencies.scss`:

```scss
@import "npm:@fortawesome/fontawesome-free/css/all.css";
```

- [ ] Arrancar `npm run dev` y comprobar que el icono se ve.

### Sass

La guía que hay que leer es [sass-lang.com/guide](https://sass-lang.com/guide): variables, anidado, parciales, importación, *mixins* y operadores, más los módulos que Sass trae de serie. La PEC obliga cinco piezas. Los *mixins* y los operadores ayudan, pero no los exige el enunciado.

- [ ] Variables. En el boilerplate ya están en `_variables.scss`.
- [ ] Anidado. Usarlo en reglas reales, sin pasarte de niveles.
- [ ] Parciales. Ficheros `_nombre.scss`, uno por responsabilidad.
- [ ] Importación. `src/assets/styles/main.scss` solo hace `@use` y no lleva reglas. El ejemplo de Font Awesome del módulo usa `@import` dentro de `_dependencies.scss`. Tienes que saber explicar las dos formas.
- [ ] Función escrita por ti (`@function`), con parámetros, y llamarla desde una propiedad. El módulo cita las funciones en las ideas clave; la actividad no manda leer esa página. Para la PEC sí hay que estudiarla en la guía de Sass.
- [ ] Provocar un error de sintaxis (un `}` de más) con `npm run dev` abierto y ver cómo lo muestra el terminal. Luego `npm run build` y comprobar que el cambio bueno llega a `dist/`.
- [ ] Mirar `src/assets/styles/` y anotar qué características de esa lista ya usa el boilerplate.

### HTML parcial y publicación

- [ ] Abrir `.posthtmlrc` y reconocer el plugin `posthtml-include`.
- [ ] Localizar en `src/index.html` la etiqueta `<include src="./views/footer.html"></include>`, editar `src/views/footer.html` y comprobar con `npm run dev` que el pie cambia.
- [ ] Hacer `npm run build` y ver que en `dist/` el pie ya va dentro del HTML, sin la etiqueta `<include>`.
- [ ] Seguir la [guía de GitHub](https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/adding-locally-hosted-code-to-github): repositorio propio, remoto, `commit` y `push`. El remoto actual de esta carpeta apunta al boilerplate de la UOC.
- [ ] Seguir el [vídeo de Netlify](https://www.youtube.com/watch?v=4h8B080Mv4U): sitio nuevo desde GitHub, comando de *build* `npm run build`, carpeta publicada `dist`.
- [ ] Cambiar algo en local, hacer `commit` y `push`, y comprobar en el panel de Netlify que se publica solo.

## Módulo 2. Criterios y Stylelint

Hay que conocer las cuatro metodologías lo bastante como para elegir una (o más) y justificarla. La guía de estilo es opcional. Stylelint es obligatorio, con plugins y reglas propias, y `npm run stylelint` tiene que terminar sin errores.

### Para elegir metodología y guía

- [ ] Leer [Why Coding Style Matters](https://www.smashingmagazine.com/2012/10/why-coding-style-matters/) y quedarte con la idea que luego escribirás en la memoria: un criterio estable hace el código coherente, aunque alguna regla sea solo estética.
- [ ] Leer de [CSS Guidelines](https://cssguidelin.es/) la introducción, *Syntax and Formatting*, *CSS Selectors* y *Specificity*.
- [ ] Leer [Code Guide](http://codeguide.co/) de Mark Otto (HTML y CSS).
- [ ] Echar un vistazo a las guías de Airbnb (CSS) y WordPress (HTML y CSS) solo para comparar si son más cerradas o más abiertas que las dos anteriores.
- [ ] Leer las cuatro metodologías y anotar, en una frase cada una, a qué afecta:
  - [OOCSS](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/): separar estructura y piel; separar contenedor y contenido.
  - [BEM](https://css-tricks.com/bem-101/): nombres `bloque__elemento--modificador`.
  - [SMACSS](http://smacss.com/), introducción y *Core*: carpetas o capas *base*, *layout*, *module*, *state*, *theme*.
  - [ITCSS](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/): siete capas de menos a más específicas (*settings*, *tools*, *generic*, *elements*, *objects*, *components*, *utilities*).
- [ ] Responder por escrito, aunque sea en bruto: ventajas de cada una, cuál es más completa, cuál más restrictiva, cuáles se pueden combinar y cuál encaja en una sola página.
- [ ] Decidir la metodología. Si eliges SMACSS o ITCSS, la estructura de carpetas Sass puede dejar de ser la del boilerplate: el enunciado lo permite si la metodología lo pide, y hay que explicarlo en la memoria. BEM se puede aplicar sin mover carpetas, cambiando los nombres de clase.
- [ ] Decidir si añades una guía (Harry Roberts, Code Guide, u otra) o te quedas solo con la metodología.

### Stylelint

El procedimiento está en la actividad del módulo 2. Hay que entender cada paso, no solo copiarlo.

- [ ] Leer la portada de [Stylelint](https://stylelint.io/): qué valida, cómo se configura y dónde están las reglas.
- [ ] Instalar la base y el plugin de SCSS:

```bash
npm install --save-dev stylelint stylelint-scss stylelint-config-recommended-scss
```

- [ ] Crear `.stylelintrc` en la raíz:

```json
{
  "extends": ["stylelint-config-recommended-scss"],
  "rules": {}
}
```

- [ ] Añadir reglas propias en `rules` que obliguen el criterio elegido. El ejemplo del módulo para BEM es la regla `selector-class-pattern`:

```json
"selector-class-pattern": "^.[a-z]([a-z0-9-]+)?(__([a-z0-9]+-?)+)?(--([a-z0-9]+-?)+){0,2}$"
```

- [ ] Si sigues el orden de declaraciones de Code Guide (@mdo), instalar `stylelint-config-recess-order` y añadirla a `extends`.
- [ ] Añadir el script `"stylelint": "stylelint src/**/*.scss"` y ejecutar `npm run stylelint`.
- [ ] Corregir el SCSS hasta que el comando acabe sin mensajes. Ese es el resultado que pide el enunciado.
- [ ] Entender el cambio de `build` que propone el módulo: `"build": "npm-run-all clean stylelint parcel:build"`. Así no se genera `dist/` si Stylelint falla.
- [ ] Anotar en la memoria paquetes, plugins, reglas y qué criterio de la metodología o de la guía cubre cada una.

## Cuando termines el estudio

Tienes que poder contestar esto sin volver a abrir los módulos. Las respuestas son el esqueleto de la memoria.

- [ ] Qué hace `npm install`, qué hace `npm run dev` y qué hace `npm run build`.
- [ ] Qué hay en `src/` y qué hay en `dist/`, y cuál de las dos se entrega y se publica.
- [ ] Qué dependencia añadiste, con qué comando, y en qué fichero entra al *bundle*.
- [ ] Dónde están tus variables, tu anidado, tu función, tus parciales y tus imports.
- [ ] Qué metodología y qué guía elegiste, y por qué encajan con una página pequeña.
- [ ] Qué reglas de `.stylelintrc` vigilan ese criterio.
- [ ] Cómo pasaste el código a GitHub y cómo Netlify lo publica a partir de `dist/`.

## Lecturas que no entran en esta entrega

Puedes saltártelas para la PEC 1.

- guide.bash.academy y el resto de la documentación de npm, Parcel y Sass que no esté en las secciones de arriba.
- Deno, Bun, Yarn, pnpm, Webpack, Vite, rspack y Turbopack. Basta saber que npm y Parcel son los que usa el boilerplate.
- Plugins de PostCSS. El módulo lo deja para el 4.2. Para esta PEC basta saber que el boilerplate ya prefija y minifica.
- La actividad final del módulo 1 con React, Angular, Vue o Astro.
- [Challenging CSS Best Practices](https://www.smashingmagazine.com/2013/10/challenging-css-best-practices-atomic-approach/). Está en los recursos del módulo 2 y no en los pasos de la actividad.
