# Memoria PEC 1

Herramientas HTML y CSS II. Borrador de trabajo: se rellena a medida que avanza la práctica. La entrega es este contenido en PDF, dentro del zip de la actividad «Entrega P1», antes del 1 de noviembre de 2026 a las 23:59 h.

Las notas en cursiva indican qué falta escribir. Se borran al pasar el documento a PDF.

**Nombre:** Carlo Fidel Taboada Petersson  
**Usuario UOC:** cftaboada  
**Fecha del borrador:** 24 de octubre de 2026

## Enlaces

| Recurso | URL |
| --- | --- |
| Repositorio de GitHub | https://github.com/CarloFidel/uoc-css02-pec01 |
| Sitio publicado en Netlify | _Pendiente._ |
| Vídeo de la PEC | _Pendiente._ |

## 1. Proceso de desarrollo

_En cada apartado: qué hice, con qué comando o herramienta, y qué obtuve. Si algo falló, dejar también el error y cómo se resolvió._

### 1.1 Obtención del repositorio

Partí de UOC Boilerplate 3.14.0.

**Pasos**

_Pendiente: clonar o descargar, y desde dónde._

**Resultado**

_Pendiente._

### 1.2 Entorno de desarrollo

El fichero `.nvmrc` del boilerplate indica Node `v20.18.1`. El módulo 1 pide una versión superior a 20.x. El boilerplate, en su README, pide Node.js 18 o superior.

**Pasos**

Trabajo en macOS, con Cursor. Comprobé las versiones en el terminal con `node -v` y `npm -v`. No cambié la versión del sistema: la que ya tenía cumple lo que pide el módulo.

**Resultado**

`node -v` devuelve `v24.20.0`. `npm -v` devuelve `11.19.0`.

### 1.3 Instalación de dependencias

**Pasos**

Con las dependencias del boilerplate ya instaladas, añadí Font Awesome, que es el ejemplo del módulo 1:

```bash
npm install --save @fortawesome/fontawesome-free
```

En `package.json` quedó también el paquete `font-awesome` `4.7.0`. Ese paquete no se importa en ningún fichero. La librería que usa la página es `@fortawesome/fontawesome-free`.

**Resultado**

`@fortawesome/fontawesome-free` quedó en `dependencies` con la versión `^7.3.1`. El detalle de cómo entra en la página está en el apartado 2.3.

### 1.4 Servidor de desarrollo

El script del boilerplate es `npm run dev` (limpia la caché y arranca Parcel en el puerto 8123).

**Pasos**

_Pendiente._

**Resultado**

_Pendiente: si la página cargó en local y la dirección usada._

### 1.5 Desarrollo

Hasta aquí el desarrollo va así. El texto de ejemplo del boilerplate (`Hello, UOC!` y el párrafo de presentación) se sustituyó por un icono de Font Awesome dentro del `h1` y por un párrafo todavía provisional (`My personal`). La estructura de la página de la recomendación no está hecha. La dependencia externa ya está instalada e importada. La metodología elegida es BEM; las clases del HTML siguen siendo las del boilerplate (`uoc-container`, `uoc-title`, `uoc-logo`, `uoc-footer`), así que el criterio todavía no está aplicado en el marcado. Stylelint y el diseño responsive de la página final están por hacer. El detalle de cada decisión está en las secciones 2 y 3.

### 1.6 Compilación para producción

El script del boilerplate es `npm run build`. Genera la carpeta `dist/`.

**Pasos**

_Pendiente._

**Resultado**

_Pendiente: qué apareció en `dist/` y si la build terminó sin errores._

### 1.7 Publicación en GitHub

**Pasos**

El remoto inicial del boilerplate apunta a `uoc-advanced-html-css/uoc-boilerplate`. Lo sustituí por un repositorio propio. La identidad de los commits de esta carpeta está en la configuración local de Git (`user.name` y `user.email`), distinta de la configuración global.

**Resultado**

`git remote -v` muestra `origin` en `https://github.com/CarloFidel/uoc-css02-pec01.git` para fetch y para push. La rama `master` sigue a `origin/master`. En el momento de escribir este apartado, el repositorio local iba un commit por delante del remoto y los cambios de Font Awesome todavía no estaban en un commit. Netlify está pendiente.

### 1.8 Despliegue en Netlify

**Pasos**

_Pendiente: cómo se conectó el repositorio, comando de build (`npm run build`) y carpeta publicada (`dist`)._

**Resultado**

_Pendiente: URL pública y comprobación en escritorio y en móvil._

## 2. Decisiones de diseño y desarrollo

### 2.1 Temática

_Pendiente: libro, película o serie; título; por qué esa obra. El plazo para proponer otra temática terminó el 13 de octubre de 2026._

### 2.2 Contenido y estructura de la página

Sitio de una sola página. El HTML de partida está en `src/index.html`. El boilerplate parte el pie con `src/views/footer.html` mediante `posthtml-include`.

_Pendiente: bloques de la página (cabecera, ficha, recomendación, datos, pie) y por qué ese orden. Mencionar el HTML semántico usado (`header`, `main`, `section`, `footer`, encabezados)._

### 2.3 Dependencia externa

El enunciado exige al menos una dependencia que no venga ya con el boilerplate.

**Cuál**

`@fortawesome/fontawesome-free`, versión `^7.3.1`.

**Por qué esta**

Es la dependencia que el módulo 1 usa como ejemplo para añadir una librería externa a UOC Boilerplate. Aporta iconos sin tener que dibujarlos ni alojar SVG propios, y encaja en una ficha de recomendación (por ejemplo, un icono junto al título o a los datos de la obra). Se instala con npm y entra en el bundle de Parcel, que es el recorrido que pide el módulo.

**Cómo se añadió y dónde se usa**

La instalé con `npm install --save @fortawesome/fontawesome-free`. El CSS entra al final de `src/assets/styles/_dependencies.scss`:

```scss
@import "npm:@fortawesome/fontawesome-free/css/all.css";
```

`main.scss` ya carga ese parcial con `@use "dependencies"`, así que no hizo falta un segundo enlace en el HTML. El icono visible está en `src/index.html`, dentro del título:

```html
<i class="fas fa-university"></i>
```

`fas` es el estilo sólido y `fa-university` es el icono. Es el ejemplo del módulo; cuando la página tenga contenido, el icono se cambiará por uno acorde a la obra. `font-awesome` `4.7.0` figura en `dependencies`, pero ningún fichero lo importa.

### 2.4 Enfoque de los estilos

_Pendiente: mobile first o desktop first, y por qué encaja con esta página._

### 2.5 Diseño responsive

_Pendiente: breakpoints, qué cambia en teléfono, tablet y escritorio, y cómo se comprobó._

### 2.6 Sass

El enunciado exige usar las cinco características. `src/assets/styles/main.scss` ya importa parciales con `@use` y no debe contener reglas propias.

**Variables**

_Pendiente: fichero (de partida, `src/assets/styles/_variables.scss`), qué guardan y dónde se usan._

**Anidado**

_Pendiente: un caso concreto y por qué el anidado sigue siendo legible._

**Función propia**

_Pendiente: nombre, qué calcula, parámetros y en qué propiedad se llama. Tiene que ser una función escrita en el proyecto, no una función de Sass ya existente._

**Parciales**

_Pendiente: lista de parciales y qué responsabilidad tiene cada uno._

**Importación**

_Pendiente: cómo se importan (`@use` en `main.scss` u otro esquema si la metodología lo cambia) y por qué no se dejan reglas sueltas en el fichero de entrada._

### 2.7 Otras decisiones

La metodología elegida es BEM (apartado 3). BEM fija cómo se nombran las clases y no pide otra estructura de carpetas. Mantengo la del boilerplate: `main.scss` como único punto de entrada, `_variables.scss`, `_dependencies.scss` y `layouts/_home.scss`.

_Pendiente: tipografía, color, imágenes y qué se dejó fuera cuando la página de la recomendación esté diseñada._

## 3. Metodología, guía de estilo y Stylelint

Esta sección cubre la justificación de los criterios, cómo quedaron aplicados en el código y la configuración de Stylelint.

### 3.1 Criterios elegidos

**Metodología**

BEM (Block, Element, Modifier).

**Guía de estilo**

_Pendiente: nombre, o indicar que no se añadió ninguna guía aparte de la metodología._

### 3.2 Justificación

Elegí BEM entre las cuatro metodologías del módulo 2.

El encargo es una sola página, no un sistema de diseño. BEM se aplica entero con una convención de nombres: `bloque__elemento--modificador`. No hace falta repartir el CSS en las cinco categorías de SMACSS ni en las siete capas de ITCSS, que están pensadas para proyectos grandes y me obligarían a cambiar las carpetas del boilerplate. OOCSS aporta dos principios útiles, pero no deja una huella clara en el HTML ni una regla que Stylelint pueda vigilar. El enunciado permite cambiar la estructura solo si la metodología lo exige. Con BEM no lo exige, así que respeto las carpetas de UOC Boilerplate.

Parto de poco recorrido con Sass y con estas metodologías. BEM es la que puedo mantener de forma consistente: el nombre de la clase dice qué bloque es, qué pieza es y si es una variante. El módulo 2, además, usa BEM como ejemplo al configurar Stylelint con `selector-class-pattern`, así que el criterio y la herramienta de comprobación van juntos.

Encaja con la forma de trabajar del boilerplate. El HTML sigue en `src/`, los parciales Sass siguen donde están y la metodología se ve en las clases, no en un cambio de arquitectura. En una página pequeña el criterio no es decorativo: cada bloque de la ficha (cabecera, datos, recomendación, pie) tendrá un nombre propio, y Stylelint podrá rechazar una clase que no cumpla el patrón.

### 3.3 Aplicación en el código

La convención queda así:

- El bloque es el componente, en minúsculas y con guiones si hace falta más de una palabra: `card`.
- El elemento es una pieza de ese bloque: `card__title`.
- El modificador es una variante: `card--featured` o `card__title--muted`.

Las carpetas no cambian. `main.scss` solo importa. `_variables.scss` guarda los valores reutilizables. `_dependencies.scss` carga Font Awesome. `layouts/_home.scss` guarda las reglas de la página.

En el HTML de ahora las clases siguen siendo las del boilerplate: `uoc-container`, `uoc-logo`, `uoc-title` y `uoc-footer`. BEM todavía no está aplicado al marcado. Los ejemplos de arriba son la convención; los ejemplos reales de la página se escribirán aquí cuando exista la ficha de la obra. No uso las capas de SMACSS ni de ITCSS, porque BEM no las pide y la página no las necesita.

### 3.4 Stylelint

**Instalación**

_Pendiente: paquetes (Stylelint, config recomendada y plugins) y si se añadieron como dependencias de desarrollo._

**Configuración**

_Pendiente: fichero de configuración, plugins activados y reglas propias. Relacionar cada bloque importante con el criterio de la sección 3.1 (por ejemplo, una regla de patrón de clases que obliga al nombre elegido en la metodología)._

**Ejecución**

_Pendiente: comando usado, script de `package.json` si se añadió, y resultado. El enunciado pide que la validación termine sin errores._

## 4. Propiedad intelectual

Recursos que no son míos. Si no hay datos de licencia, se consideran con copyright. La licencia tiene que permitir el uso en esta práctica. Si el recurso es un fichero digital, el original va adjunto en la entrega; si tiene código fuente, también.

| Recurso | Autor | Dónde se obtuvo | Licencia |
| --- | --- | --- | --- |
| `@fortawesome/fontawesome-free` 7.3.1 (CSS) | Fonticons, Inc. | npm, paquete `@fortawesome/fontawesome-free` | MIT, para el código que no es fuente ni icono SVG |
| Iconos de Font Awesome Free usados como fuente web | Fonticons, Inc. | El mismo paquete, vía `css/all.css` | SIL Open Font License 1.1. Los iconos SVG y JS del paquete van bajo CC BY 4.0. Hay que mantener la atribución |
| Logotipo de la UOC (`src/assets/images/logo.png`) | Universitat Oberta de Catalunya | Incluido en UOC Boilerplate | Sin licencia explícita en el repositorio. Se asume copyright de la UOC |

_Añadir una fila por imagen, tipografía, icono, biblioteca o texto de terceros. La dependencia externa de la sección 2.3 también se lista aquí._

## 5. Vídeo

_Pendiente: enlace (el mismo de la tabla inicial), duración aproximada, dónde está alojado (Google Drive de la cuenta @uoc.edu, compartido, y/o la tarea; YouTube solo si también es la cuenta académica) y qué se muestra: página (bloques, dependencia, responsive) y código (metodología, Stylelint, Sass, HTML)._
