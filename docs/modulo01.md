# Módulo 1: Un workflow moderno de desarrollo front-end

En el primer módulo de la asignatura Herramientas HTML y CSS II empezaremos a tocar código y nos familiarizaremos con un conjunto de herramientas moderno que nos permite que el desarrollo sea más eficiente.

Si alguna vez habéis desarrollado el front-end de una página web, habréis trabajado con un editor de texto tocando ficheros HTML, CSS y JavaScript. Actualmente, los desarrolladores web usamos herramientas un poco más avanzadas que un simple editor de textos. Aunque de entrada puede parecer que se complica un proceso que es relativamente sencillo, el uso de herramientas avanzadas facilita a largo plazo el desarrollo, ya que permite la gestión de dependencias, la automatización de algunas tareas, como la optimización de imágenes, y el uso de lenguajes más avanzados, como los preprocesadores de estilos.

En primer lugar, tendréis que familiarizaros con el uso del terminal si no sois usuarios habituales. Tendréis que saber navegar por la estructura de directorios y saber ejecutar comandos. Una vez entendáis su funcionamiento básico, empezaremos a ver algunas de las herramientas básicas para el desarrollo front-end, como los gestores de paquetes y los module bundlers. Por último conoceremos el concepto de preprocesador de estilos, y aprenderemos el funcionamiento básico del lenguaje Sass.

Todo esto lo haremos a través del uso de una plantilla de inicio pensada para esta asignatura, UOC Boilerplate, que podréis encontrar en [este repositorio](https://github.com/uoc-advanced-html-css/uoc-boilerplate). La palabra *boilerplate* se refiere a un código de inicio que no tendréis que escribir cada vez, puesto que os facilitamos una plantilla de estructura de ficheros y un conjunto de herramientas a partir del cual se puede empezar un desarrollo con facilidad. Se trata, pues, del punto de partida a partir del cual se realizarán las PECs de este curso. Ya incluye un workflow moderno preparado para que podáis empezar a desarrollar, y aprenderemos cómo personalizarlo añadiendo dependencias. Os animamos a que os familiaricéis con el boilerplate siguiendo las actividades propuestas en esta guía, ya que más adelante lo tendréis que usar. Además, podéis usar las herramientas propuestas en este curso en otros contextos y proyectos, como veremos en el apartado final de este módulo.

Los materiales de aprendizaje los encontraréis en la sección Recursos básicos, y en la sección Contenidos y actividades encontraréis algunas ideas y propuestas de actividades sencillas para consolidar los conocimientos adquiridos con los recursos propuestos. Si tenéis alguna duda sobre alguna de las actividades o no sabéis la respuesta a alguna de las preguntas, abrid un hilo en el foro para comentarlo.

> Si ya cursaste la asignatura Herramientas HTML y CSS I, este módulo sirve de repaso de algunos de los contenidos que ya trabajaste en esa asignatura. Sin embargo, te recomendamos que trabajes los contenidos de este módulo, ya que también se introduce UOC Boilerplate, una herramienta que deberás usar en esta asignatura. Si todavía no cursaste la asignatura Herramientas HTML y CSS I, no te preocupes, porque este módulo introduce todos los contenidos necesarios.

## Objetivos de aprendizaje

- Familiarizarse con el uso del terminal.
- Conocer el funcionamiento y la utilidad de los gestores de paquetes como npm.
- Conocer el funcionamiento y la utilidad de los module bundlers como Parcel.
- Conocer el funcionamiento y la utilidad de un preprocesador de estilos como Sass.
- Familiarizarse con el boilerplate de desarrollo de UOC Boilerplate.
- Conocer herramientas modernas para control de versiones (Git, GitHub) y para la publicación de sitios web estáticos (Netlify).

## Recursos básicos

En este módulo empezaremos a trabajar con código HTML, CSS y JavaScript. Para editarlo, tendréis que disponer de un buen editor de texto, como Visual Studio Code, Sublime Text, o cualquier otro que hayáis usado habitualmente y que tenga características similares.

Si usáis Windows, tenéis diferentes opciones: usar PowerShell, el nuevo Terminal de Windows, o el subsistema de Linux para Windows. El método recomendado este semestre es PowerShell, aunque es probable que las otras opciones os funcionen correctamente. Si sois usuarios de macOS o Linux, ya disponéis de las herramientas necesarias para empezar.

Las lecturas que os llevarán a alcanzar los objetivos de aprendizaje de este módulo son las siguientes:

- [Command line crash course](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)
- [Introducción al uso del terminal](https://medium.com/@grace.m.nolan/terminal-for-beginners-e492ba10902a)
- [Sobre las herramientas de desarrollo front-end](https://medium.com/@emre.deniz/why-build-tools-are-essential-for-modern-front-end-development-8298616687ed)
- [Introducción a GitHub desde el terminal](https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/adding-locally-hosted-code-to-github)
- [Tutorial de Netlify: deployment desde GitHub](https://www.youtube.com/watch?v=4h8B080Mv4U)
- Documentaciones, como referencia y no como lectura seguida:
  - [npm](https://docs.npmjs.com/)
  - [Parcel](https://parceljs.org/getting-started/webapp/)
  - [Sass](https://sass-lang.com/guide)

> Las documentaciones técnicas de los lenguajes y herramientas mencionados son muy extensas y contienen mucha más información de la necesaria para alcanzar los objetivos de aprendizaje de este módulo. Debéis usar las documentaciones como referencia y no como lectura secuencial obligatoria, y solo tendréis que entender y aprender lo necesario para este curso. Por estos motivos, os recomendamos la lectura de estos documentos y la realización de las actividades de acuerdo con las pautas propuestas en la sección Contenidos y actividades. Os alentamos a que, además, leáis y aprendáis todo aquello que os interese y que complemente los contenidos de este curso.

## Contenidos y actividades

### Uso del terminal

#### Ideas clave

El terminal es la herramienta que nos permitirá ejecutar las demás herramientas de este módulo. Por lo tanto, es necesario que os habituéis a su uso y entendáis su funcionamiento básico.

#### Actividad

Si usas Windows, te recomendamos usar PowerShell o el nuevo Terminal de Windows. También puedes instalar el subsistema de Linux para Windows. Si lo haces, cada vez que nos refiramos al terminal, en el caso de Windows, querrá decir acceder al subsistema de Linux en modo terminal. Si usas Windows, cuenta en el foro qué opción has usado y si te funciona todo correctamente.

Lee el documento [Command line crash course](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line) y realiza los ejemplos que allí se proponen hasta la sección *A slightly more complex example*. En la parte superior encontrarás la sección *Basic built-in terminal commands* con los comandos más habituales.

Un poco más exhaustivo, pero también un artículo muy recomendable para empezar con la terminal, es el artículo [Terminal for beginners!](https://medium.com/@grace.m.nolan/terminal-for-beginners-e492ba10902a) de Grace Nelson. En la parte superior encontrarás la sección *TL;DR* con un resumen de los comandos más importantes que deberías conocer. Ambos artículos hacen una introducción similar, pero se complementan bien.

En guide.bash.academy encontrarás mucha más información sobre el uso del terminal.

### Sobre los gestores de paquetes

#### Ideas clave

- Para ejecutar las herramientas que usaremos en esta asignatura, que internamente funcionan con JavaScript, necesitamos un entorno de ejecución (*runtime*) de JavaScript. La más popular y que usaremos en esta asignatura es Node.js. Hay otras alternativas recientes que están ganando popularidad, como Deno y Bun.
- Un gestor de paquetes nos sirve para instalar y gestionar dependencias externas a nuestro proyecto. Puede tratarse de una dependencia necesaria para el desarrollo, como un optimizador de imágenes, o de una librería que quieras usar en el front-end, como por ejemplo jQuery.
- UOC Boilerplate usa npm, un gestor de paquetes que viene por defecto con Node.js. Otras alternativas compatibles con npm, aunque con algunas diferencias en su funcionamiento, son Yarn, pnpm o Bun Package Manager (si usas Bun Runtime en lugar de Node.js).

#### Actividad 1

Comprueba si tienes instalado npm en tu ordenador. npm se instala conjuntamente con Node.js. Por lo tanto, para comprobarlo, puedes ejecutar el comando `node -v` en el terminal. Si te aparece un número de versión (algo así como `24.21.0`), es que ya tienes npm instalado y, por lo tanto, puedes ir a la siguiente actividad. Si no, te saldrá un error.

Como en esta asignatura usamos herramientas modernas, deberás usar una versión de Node.js superior a 20.x. Si al ejecutar `node -v` te apareció una versión inferior, deberás actualizarla. Puedes hacerlo siguiendo las instrucciones de instalación del siguiente párrafo, o si necesitas mantener diferentes versiones de Node.js en tu ordenador por algún motivo (por ejemplo, para otros proyectos o asignaturas), puedes usar un gestor de versiones de Node.js como nvm o fnm.

Si no tienes npm instalado, hay que instalarlo. Para hacerlo, ve a la página de descargas de Node.js e instala la versión adecuada para tu sistema operativo. Busca entre la lista de versiones la LTS (*Long Term Support*).

En el caso de macOS, puedes usar alguno de los gestores de versiones de Node.js (nvm o fnm), Homebrew, o el instalador. En el caso de Linux o el Subsistema de Linux para Windows, te recomendamos seguir las instrucciones para usar nvm o fnm (recuerda elegir Linux en el selector de sistema operativo si usas el Subsistema de Linux para Windows, y ejecutar los comandos en el terminal del subsistema de Linux). Si usas otras opciones en Windows, también puedes usar el instalador o las instrucciones para usar un gestor de versiones de Node.js.

Una vez finalizada la instalación, comprueba que se ha realizado correctamente ejecutando el comando `node -v`.

Para poder compilar algunas de las herramientas que usaremos en este curso, es posible que tu entorno necesite herramientas adicionales. Las puedes instalar de la siguiente manera:

- **Windows:** si usaste el instalador, durante la instalación de Node.js te pedirá si quieres instalar las herramientas adicionales. Si no lo hiciste en su momento, puedes ejecutar su instalador en el menú Inicio > Node.js > Install Additional Tools for Node.js.
- **macOS:** si no lo hiciste con anterioridad, deberás instalar las Command Line Tools en tu sistema, ejecutando el comando `xcode-select --install` en el Terminal.
- **Linux / WSL:** algunas distribuciones de Linux (Ubuntu, Debian) necesitan la librería `build-essential`, que puedes instalar ejecutando el comando `sudo apt-get install build-essential` en el Terminal.

#### Actividad 2

Como lectura introductoria, lee el artículo [Why Build Tools Are Essential for Modern Front-End Development](https://medium.com/@emre.deniz/why-build-tools-are-essential-for-modern-front-end-development-8298616687ed). Esta lectura presenta los tipos de herramientas que usaremos en este curso y también mucha de la terminología que usaremos. Por lo tanto, es importante que lo leas con atención.

#### Actividad 3

Lee las siguientes secciones de la documentación de npm:

- About npm
- Packages and modules > About packages and modules
- Packages and modules > Downloading and installing packages locally
- Packages and modules > Uninstalling packages and dependencies
- Packages and modules > Updating packages downloaded from the registry
- Packages and modules > Creating a package.json file

Ten a mano la documentación de la sección *Resolving EACCES permissions errors when installing packages globally* por si tuvieras problemas más adelante.

#### Actividad 4

¡Nos ponemos las pilas con UOC Boilerplate! Es importante que te vayas familiarizando, ya que tendrás que desarrollar las PECs de este curso sobre esta plantilla inicial.

Realiza las siguientes actividades y responde a las siguientes preguntas:

1. Descarga el repositorio <https://github.com/uoc-advanced-html-css/uoc-boilerplate> con el botón verde de la parte superior derecha, y cópialo en una carpeta de trabajo. También puedes clonar el repositorio con `git clone`, si estás familiarizado con esta herramienta.
2. Abre el fichero `package.json` con un editor de textos. ¿Qué dependencias ves? ¿Para qué crees que sirven? ¿Qué otras entradas hay en este fichero y para qué sirven?
3. Ejecuta el comando `npm install` desde el terminal en tu carpeta de trabajo. ¿Para qué sirve este comando? ¿Qué ocurre dentro de la carpeta cuando lo ejecutas?
4. Instala una dependencia nueva en el proyecto. Te proponemos instalar Font Awesome, una conocida librería de iconos que usaremos en la siguiente sección. Para instalar esta librería, ejecuta el comando `npm install --save @fortawesome/fontawesome-free`, como se explica en la documentación de Font Awesome. ¿Cómo afecta esta instalación al contenido del fichero `package.json`?
5. ¿Para qué sirve el comando `npm install`? ¿Qué diferencia hay entre ejecutar `npm install` y `npm install <nombre del paquete>`?

> Si al ejecutar `npm install` te aparecen warnings (no errores), puedes ignorarlos. Del mismo modo, puede ser que te avise que algunas de las dependencias puedan tener vulnerabilidades, pero no es necesario resolverlo con `npm audit`. Hacerlo podría romper algunas de las funcionalidades de UOC Boilerplate. En cualquier caso, cada semestre se actualizan las herramientas para resolver posibles vulnerabilidades en las dependencias.

### Sobre los module bundlers

#### Ideas clave

- Un *module bundler* nos permite automatizar un conjunto de tareas así como gestionar los assets de las dependencias instaladas con npm.
- UOC Boilerplate usa Parcel v2 como *module bundler*. Otro *module bundler* muy conocido y que durante mucho tiempo fue líder en la industria es Webpack, aunque es más difícil de configurar y usar. Últimamente, están ganando popularidad alternativas como rspack, Vite y Bun Bundler.
- La configuración por defecto de UOC Boilerplate contiene herramientas para facilitar el desarrollo así como la optimización de assets para producción.
- En entorno de producción, UOC Boilerplate compila, concatena y minifica las hojas de estilos y scripts, y tiene herramientas para transformar y optimizar las imágenes.
- En entorno de desarrollo, UOC Boilerplate realiza los mismos procesos, excepto la optimización y minificación. Lanza un servidor de desarrollo y monitoriza los cambios en los ficheros para actualizar el navegador automáticamente.
- Los ficheros que hay que modificar para desarrollar un sitio web con UOC Boilerplate son los que se encuentran dentro de la carpeta `src/`. De momento, el resto de los ficheros no los tenéis que modificar si no sabéis exactamente lo que estáis haciendo. Más adelante en el curso los modificaremos y crearemos otros nuevos.

#### Actividad 1

Lee y entiende los [conceptos básicos](https://parceljs.org/getting-started/webapp/) de Parcel. La parte de instalación te la puedes saltar, porque UOC Boilerplate ya incluye una instalación local de Parcel.

La configuración de Parcel es muy sencilla (se autodenomina *zero configuration web application bundler*), y UOC Boilerplate añade configuraciones adicionales y propone una estructura de ficheros. Ahora fíjate en el contenido de la sección `scripts` del fichero `package.json`. ¿Para qué crees que sirve?

#### Actividad 2

Después de haber ejecutado el comando `npm install` en las actividades anteriores, ya tenemos Parcel instalado localmente en la carpeta del proyecto. Por lo tanto, ya podemos trabajar con él. Ahora usaremos los comandos que vimos en la sección `scripts` del `package.json`.

Realiza las siguientes actividades y responde las siguientes preguntas:

1. Ejecuta el comando `npm run build`. ¿Qué ocurre en el terminal? ¿Qué ocurre en la carpeta de trabajo? ¿Qué crees que hay en la nueva carpeta que ha aparecido? Inspecciona los ficheros generados. ¿Qué diferencias hay con los contenidos de la carpeta `src/`? Para encontrar estas diferencias, fíjate en la estructura de los ficheros en las carpetas, el peso de los ficheros, y abre también algún fichero (por ejemplo, el `index.html` en ambas rutas) con tu editor de texto para compararlos.
2. Ahora ejecuta el comando `npm run dev`. Mantén esta ventana del terminal abierta. Abre una nueva ventana del navegador e introduce la URL que te apareció en el terminal (normalmente, `http://localhost:8123`). ¿Qué ocurre? ¿Qué diferencias hay con la ejecución del comando anterior? Vuelve a fijarte en la estructura de los ficheros en las carpetas y en el contenido de estos ficheros.
3. Manteniendo el entorno de desarrollo que lanzaste en el paso anterior en ejecución, abre el fichero `src/assets/styles/_variables.scss` con tu editor de código. Prueba a cambiar alguno de los códigos de color que aparecen en las líneas 8-9 de este fichero, y observa qué ocurre en el navegador.
4. Ahora averigua la IP de tu máquina en tu red local. Con cualquier otro dispositivo que no sea tu ordenador (otro ordenador, una tablet o un teléfono), conectado a la misma red local (WiFi, ethernet), abre el navegador e introduce esta dirección IP seguida de `:` y el puerto que vimos anteriormente (normalmente es `:8123`). ¿Qué ocurre?
5. Puedes cancelar la ejecución del entorno de desarrollo con la combinación de teclas `ctrl+c`.

#### Actividad 3

Siguiendo con el ejemplo anterior, procederemos a incluir Font Awesome en nuestro *bundle*.

Después de realizar la actividad 3 de la sección *Sobre los gestores de paquetes*, realiza las siguientes actividades y responde las siguientes preguntas:

1. Abre el fichero `src/index.html` con tu editor de texto. Dentro del elemento `<h1></h1>` escribe el siguiente código:

   ```html
   <i class="fas fa-university"></i>
   ```

2. Ahora hay que incorporar las dependencias de Font Awesome que instalamos anteriormente a nuestro *bundle*. Para hacerlo, abre el fichero `src/assets/styles/_dependencies.scss` y, al final del fichero, escribe el siguiente código:

   ```scss
   @import "npm:@fortawesome/fontawesome-free/css/all.css";
   ```

3. Ejecuta `npm run dev`. ¿Qué cambios hay en la página?

### Sobre pre- y postprocesadores de estilos

#### Ideas clave

- Un preprocesador de estilos nos permite usar un lenguaje de estilos extendido, incorporando nuevas funcionalidades al lenguaje.
- UOC Boilerplate usa Sass, un lenguaje de preprocesado de estilos muy habitual. Otro lenguaje muy conocido es Less.
- Aparte, también hay postprocesadores de estilos como PostCSS. En UOC Boilerplate se usa PostCSS para tareas de postprocesado, como la minificación de las hojas de estilo o el prefijado automático de CSS moderno para navegadores antiguos. Además, puedes instalar cualquier otro plugin de PostCSS.
- Nos familiarizaremos con los conceptos más habituales de este lenguaje de preprocesado de estilos: variables, anidado, importación, *mixins* y funciones.

#### Actividad 1

Lee las secciones de variables, anidado, parciales, importación, *mixins* y operadores de la [guía básica de Sass](https://sass-lang.com/guide). Lee también la documentación sobre los módulos que Sass lleva incorporados por defecto. Puedes ampliar tus conocimientos sobre Sass en la documentación completa.

Abre la carpeta `src/assets/styles/` de UOC Boilerplate. ¿Cuáles de las funcionalidades de Sass estudiadas están aplicadas en estos ficheros?

#### Actividad 2

Ejecuta el comando `npm run dev`. Experimenta con los elementos DOM del fichero `src/index.html` y con las normas de estilos que quieras de los ficheros de `src/assets/styles/`. Incorpora algunas de las funcionalidades de Sass que vimos en el punto anterior. ¿Qué ocurre si hay algún error sintáctico en tus hojas de estilos? (por ejemplo, puedes añadir un `}` en un sitio donde no corresponda para comprobarlo).

Detén la ejecución del entorno de desarrollo con `ctrl+c`. Ejecuta el comando `npm run build`. ¿Se han compilado correctamente para producción los cambios que has incorporado en el proyecto?

#### Actividad 3

Lee la documentación de Parcel sobre PostCSS. Si quisiéramos añadir un plugin de PostCSS, ¿qué fichero deberíamos añadir a nuestro proyecto? Lo haremos más adelante, en el módulo 4.2.

### Sobre postprocesadores de HTML

#### Ideas clave

- Un postprocesador de HTML nos sirve para transformar el HTML escrito mediante plugins.
- UOC Boilerplate usa PostHTML e incorpora por defecto el plugin `posthtml-include`, que nos permite incluir ficheros HTML parciales. Además, puedes instalar cualquier otro plugin de PostHTML.

#### Actividad 1

Lee la documentación de Parcel sobre PostHTML. Explora el fichero `.posthtmlrc`. ¿Para qué sirve este fichero? ¿Qué plugins hay configurados y para qué sirven?

#### Actividad 2

Explora el fichero `index.html` y detecta la etiqueta HTML no estándar. ¿Cómo crees que funciona? Ejecuta `npm run dev` y realiza modificaciones a los ficheros `index.html` y `views/footer.html`. ¿Qué ocurre? Ejecuta `npm run build` y explora los ficheros HTML generados. ¿Qué ha sucedido con ambos ficheros HTML?

### Publicación de la web en internet

#### Ideas clave

- Para que una web sea visible para todo el mundo (no solo desde el entorno de desarrollo local), hay que publicarla en un servidor web.
- La versión de la web que debe estar en el servidor es, evidentemente, la versión de producción que genera Parcel.
- Actualmente existen decenas de servicios donde publicar webs sencillas de forma gratuita y cómoda. La mayoría usan el contenido publicado en algún servicio de alojamiento de repositorios Git.
- Git es un sistema de control de versiones. Los contenidos se guardan en repositorios. El contenido de estos repositorios es abierto al público, de forma que cualquier usuario podrá ver el código del proyecto.
- En este módulo nos basaremos en GitHub como plataforma donde crear el repositorio Git, y en Netlify como proveedor del servidor donde publicar la web.
- No hay ningún problema en utilizar servicios alternativos a GitHub (GitLab, Bitbucket) o a Netlify (GitHub Pages, Vercel). En cualquier caso, no hay que gastar dinero en esta actividad.

#### Actividad 1

1. Asegúrate de haber creado tu cuenta (gratuita) en GitHub.
2. A continuación, crea un repositorio Git y vincula tu carpeta local (donde tienes el código actualmente). En [esta guía oficial](https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/adding-locally-hosted-code-to-github) encontrarás las instrucciones que debes ejecutar detalladas paso a paso.

#### Actividad 2

1. Asegúrate de haber creado tu cuenta (gratuita) en Netlify.
2. A continuación, crea un nuevo sitio web a partir del código disponible en GitHub. En [este vídeo](https://www.youtube.com/watch?v=4h8B080Mv4U) puedes seguir paso a paso el proceso para vincular Netlify y GitHub.
3. Accede a la URL generada y comprueba que la web es visible.

#### Actividad 3

Una de las muchas funcionalidades interesantes de Netlify es que actualiza tu web a medida que actualizas el repositorio Git (lo que se conoce como *continuous deployment*).

1. Para probarlo, realiza cualquier cambio en tu código en local (un texto, una imagen, un color…). A continuación, carga este cambio en el repositorio Git. Para hacerlo, vuelve a seguir los pasos *commit* y *push* que viste en la guía de Git. Cada vez que realices cambios significativos en tu código, deberás repetir estos dos pasos.
2. Accede al panel de control de Netlify, y asegúrate de que la plataforma detectó el cambio y de que empezó el proceso para publicar la versión actualizada de la web.
3. Accede a la URL generada y comprueba que la nueva versión de la web es visible.

### Otras formas de usar las herramientas propuestas

#### Ideas clave

- En esta asignatura te recomendamos el uso de UOC Boilerplate, una plantilla de inicio basada en Parcel que nos sirve para generar un sitio web estático.
- No obstante, si ya has usado Parcel u otros *module bundlers*, como Webpack, Turbopack o Vite, puedes instalar y usar las herramientas propuestas que necesites (o alternativas compatibles) en tu proyecto.
- La mayoría de los *frameworks* de JS modernos, como React, Angular, Vue o Astro, usan por defecto Vite, Turbopack o Webpack como *module bundler*, aunque a veces tienen herramientas o configuraciones por encima que nos facilitan su uso, o pueden ser usados con otros *module bundlers*, como Parcel. Puedes consultarlo en las documentaciones de dichos *frameworks*.
- Por ejemplo, en un proyecto con React, Angular, Vue o Astro, podrías instalar (o comprobar si ya tienes instalado) PostCSS y alguno de los plugins recomendados. En cambio, PostHTML no sería necesario, ya que solo tiene sentido en el contexto de un sitio web basado en ficheros HTML estáticos.

#### Actividad 1

Solo si tienes los conocimientos necesarios, crea un nuevo proyecto basado en React, Angular, Vue o Astro, o abre algún proyecto de pruebas que ya tengas creado. Instala Font Awesome, siguiendo los pasos que viste anteriormente, e incluye un icono en una de las páginas o componentes.

Comprueba si tu proyecto incluye Sass o no y, en caso de que no, sigue las instrucciones para hacerlo (por ejemplo, al inicializar un proyecto nuevo con Angular, puedes pasarle el *flag* `--style`: `ng new project-name --style=sass`).

Responde las siguientes preguntas:

- ¿Qué diferencias encuentras entre usar UOC Boilerplate o cualquier otra plantilla de inicio, por ejemplo las basadas en Angular o React?
- ¿Cuáles de las herramientas que vimos en este módulo no tendrían sentido en un proyecto con Angular o React? ¿Qué sería el equivalente de usar `posthtml-include` en el *framework* que estés usando?
- ¿Cuáles de las herramientas propuestas en este módulo ya tenías instaladas (o podías instalar fácilmente con un *flag*, o buscando la plantilla correcta) en la plantilla que usaste?
