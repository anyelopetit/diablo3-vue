Diablo III Profile Finder 🛡
============================

**D3PF**: aplicación Vue.js creada desde cero que consume las API oficiales de Diablo III, el famoso juego de Blizzard. Ofrece un buscador de jugadores reales del juego para mostrar sus estadísticas y personajes.

  

![main.png](https://static.platzi.com/media/user_upload/main-d03978d4-65b7-4f10-8eaf-79fb628621c6.jpg)

*   **Demo**: revisa esta demo online para que veas qué es lo que vamos a construir juntos · [https://diablo3.netlify.com](https://diablo3.netlify.com). Puedes utilizar este usuario en el formulario `SuperRambo#2613` para probar en la region `EU`.
*   **GitHub**: en este enlace encontrarás el repositorio completo · [https://github.com/baumannzone/diablo3-vue-platzi](https://github.com/baumannzone/diablo3-vue-platzi)

Vue CLI
=======

📗 [https://cli.vuejs.org/](https://cli.vuejs.org/)

Vue CLI (es decir, la interfaz de línea de comandos) es una herramienta para crear proyectos de Vue.js de forma rápida, desarrollada por el equipo de Vue.js.

Para usar esta herramienta deberás tenerla instalada (recomendado de manera global). Si ya la tienes instalada, puedes saltarte este paso.

Y recuerda, para seguir este curso es obligatorio que tengas Vue CLI instalado.

Instalar Vue CLI
----------------

Desde tu terminal escribe el siguiente comando:

```bash
npm install -g @vue/cli
# O
yarn global add @vue/cli
```

Una vez instalada la herramienta, podemos empezar a crear nuestro proyecto. Existen dos formas de crear un proyecto con el CLI de Vue:

*   A través de la terminal: `vue create nombre_proyecto` (esta es la que vamos a usar nosotros).
*   A través de una interfaz gráfica: `vue ui` (a través del navegador, vas seleccionando con el ratón las opciones que te interesan).

Crear el proyecto con Vue CLI
-----------------------------

Desde la terminal escribe el siguiente comando:

vue create diablo3

Elige la forma `manual` y después te debería aparecer lo siguiente:

![create-1.png](https://static.platzi.com/media/user_upload/create-1-5df4fda8-f52c-4fe5-bdea-40a1d3beedcc.jpg)

El CLI de Vue está preguntando qué _features_ quieres instalar en el proyecto. Vamos a instalar todas las que están marcadas en verde (para marcar una opción usa la tecla `space` y para moverte usa las flechas de ⬆️ / ⬇️).

*   Babel.
*   VueRouter para el manejo de rutas.
*   Vuex para la gestión del estado.
*   Pre-procesador CSS.
*   Linter estricto. Si no has usado uno antes, seguro que te cuesta adaptarte. Pero verás que merece la pena.
*   Ahora todo tu código, incluso si trabajas con varias personas en el proyecto, va a tener el mismo estilo, pues de esto se va a encargar el linter. ¡Le va a dar un toque muy profesional a tu aplicación! 😉
*   Testing: unitario y end to end (E2E).

Cuando tengas todo marcado, presiona la tecla `enter` y al terminar empezará a hacer preguntas que irás respondiendo una a una hasta llegar al final.

Estas son las opciones que debes elegir:

![create-2.png](https://static.platzi.com/media/user_upload/create-2-292801ab-8a8d-4c93-b33c-372875285f96.jpg)

*   History mode: elige **no**. Esto sirve para dejar o quitar el hash (#) de la url. En nuestro caso lo hemos dejado.
*   El pre-procesador de CSS que vamos a elegir es **Stylus**, me gusta porque es potente, simple y elegante.
*   Linter, vamos a tener dos opciones:
*   La primera: **Standard Config**. Es la configuracion de linteado que mas me gusta. Está basada en [Standard Js](https://standardjs.com/).
*   La segunda: marcamos las dos opciones **Lint on save** y **Lint and fix on commit**. Con esta configuración no vamos a poder hacer commit si tenemos algún error de linteado.
*   Como herramienta de testing unitario utilizaremos **Jest**.
*   Para testing E2E usaremos **Cypress**.
*   En esta opción elegimos **In package.json**. Esto guardará las configuraciones de algunas librerías dentro de ese fichero.
*   Y por último, pregunta si queremos guardar estas opciones para poder usarlas por defecto en el futuro. Puedes elegir la que quieras, en esta ocasión vamos a marcar **no**.

Ahora empezará a instalarse todo lo que hemos ido marcando. Cuando termine, si todo ha ido bien, deberías ver la siguiente pantalla:

![create-3.png](https://static.platzi.com/media/user_upload/create-3-8781c668-6e57-4a88-85cf-e87255fa7fbb.jpg)

Si no tienes instalado `yarn`, puedes usar `npm`, es (casi) lo mismo.

Por lo tanto, para arrancar la aplicación desde la terminal hacemos lo siguiente:

*   Vamos a la carpeta del proyecto: `cd diablo3/`.
*   Ejecutamos el servidor en modo desarrollo. Bien con `npm run serve` o con `yarn serve`.

Cuando el servidor esté levantando verás algo como esto:

![create-4.png](https://static.platzi.com/media/user_upload/create-4-adbd07f6-330b-4ef3-9cf4-5223d2f98b4a.jpg)

Ahí nos indica que nuestra aplicación Vue está levantada en la url [http://localhost:8080](http://localhost:8080) con el siguiente contenido:

![create-5.png](https://static.platzi.com/media/user_upload/create-5-c2d49f1a-7c21-44e4-b59f-d330cf8fc414.jpg)

💡 Para evitar que nos salga un **error** en la terminal, como el de aquí abajo, vamos a modificar el fichero `package.json`, en concreto el bloque de `devDependencies`.

Esto se debe a un error no corregido por parte de la librería `babel-eslint`.

![error-babel.png](https://static.platzi.com/media/user_upload/error-babel-64b1b98f-c2a4-40ef-8082-2e3a3b972570.jpg)

```diff
    "@vue/cli-service": "^4.2.0",
    "@vue/eslint-config-standard": "^5.1.0",
    "@vue/test-utils": "1.0.0-beta.31",
-   "babel-eslint": "^10.0.3",
+   "babel-eslint": "7.2.3",
    "eslint": "^6.7.2",
    "eslint-plugin-import": "^2.20.1",
    "eslint-plugin-node": "^11.0.0",
```

Actualiza la versión que tengas de `babel-eslint` a la `7.2.3`. En mi caso, he pasado de la versión `^10.0.3` a la `7.2.3`.

Hazlo ahora, para que luego en el futuro no te de problemas.

**¡Enhorabuena!** Ya has creado tu app con el CLI de Vue.

En la siguiente sección repasaremos la documentación de las API de Blizzard para saber cómo usarlas y empezar a construir nuestra aplicación.


## 2. Blizzard Developer Portal :heavy_check_mark:

> En esta sección vamos a explicar algunos conceptos del portal de desarrolladores de Blizzard que vamos a necesitar para el desarrollo de nuestra app.

![Main](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/main.png)

Este es el portal oficial de desarrolladores de Blizzard. Aquí encontrarás toda la información necesaria.

> 📗 [https://develop.battle.net/](https://develop.battle.net/)

Crear Cuenta
------------

> 📗 [https://us.battle.net/account/creation/es/](https://us.battle.net/account/creation/es/)

Para poder usar las APIs de Blizzard es necesario crearse una cuenta. Crea tu cuenta desde el siguiente enlace: [https://us.battle.net/account/creation/es/](https://us.battle.net/account/creation/es/)

Blizzard Authenticator
----------------------

Una vez hayas creado tu cuenta, el siguiente paso es que te instales en el móvil la aplicación “Blizzard Authenticator”.

El Authenticator de Blizzard es obligatorio y ofrece una capa extra de seguridad contra accesos no autorizados a tu cuenta.

**Descarga** la aplicación Blizzard Authenticator de la App Store o desde Google Play para continuar.

*   Android: [https://play.google.com/store/apps/details?id=com.blizzard.bma](https://play.google.com/store/apps/details?id=com.blizzard.bma)
*   iPhone: [https://apps.apple.com/app/blizzard-authenticator/id306862897](https://apps.apple.com/app/blizzard-authenticator/id306862897)

### Uso

Cuando entres a tu cuenta, recibirás una solicitud de autenticación en tu equipo. Si el código de tu equipo es el mismo que el de tu ordenador, presiona Aprobar.

Abre la aplicación de Blizzard Authenticator, verás algo parecido a esto:

![mobile-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/mobile-1.png)

Desde el formulario de iniciar sesión, pon tu usuario y tu contraseña. Antes de terminar el inicio de sesión, te pedirán que confirmes el acceso

![auth-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/authenticator-1.png)

Ahora, en la app Blizzard Authenticator, te aparecerá el código. Pulsa el botón de “Autorizar”

![mobile-2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/mobile-2.png)

Una vez que hayas aceptado desde la app en tu teléfono móvil verás algo como esto:

![auth-2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/authenticator-2.png)

### Seguridad

Si inicias sesión siempre desde la misma ubicación, puede que no se te pida un código de Authenticator. Esto permite iniciar sesión más rápido cuando te encuentras en una ubicación segura.

Si recibes una solicitud de autenticación que no hayas iniciado, haz clic en **Denegar** y cambia tu contraseña de Blizzard.

  

Client Credentials Flow
-----------------------

> 📗 [https://develop.battle.net/documentation/guides/using-oauth/client-credentials-flow](https://develop.battle.net/documentation/guides/using-oauth/client-credentials-flow)

Para consumir las APIs de Diablo III (o cualquier otro juego de Blizzard) es necesario previamente haber obtenido un **token** de acceso, que a partir de ahora lo llamaremos el “token”. El token de acceso es una credencial usada para acceder a los recursos protegidos de la API. Este tipo de flujo, el flujo “Client Credentials Flow” se usa para la mayoría de las solicitudes a las APIs de Blizzard.

Cuando entras en la aplicación ([https://diablo3.netlify.com/](https://diablo3.netlify.com/)), lo primero que ves es un “Loading”. Eso es porque la aplicación está obteniendo el token. Más adelante entenderás cómo se hace.

![Loading](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/loading.gif)

Puedes ver el [RFC de OAuth](https://tools.ietf.org/html/rfc6749#section-1.3.4) si quieres saber más acerca del “Client Credentials Flow”

Regiones
--------

> 📗 [https://develop.battle.net/documentation/guides/regionality-and-apis](https://develop.battle.net/documentation/guides/regionality-and-apis)

Blizzard emplea varios conceptos basados en la región para administrar y servir los datos de los juegos.

Los datos de las APIs están limitados a regiones específicas. Por ejemplo, las APIs de Europa (eu) a las que se acceden a través de `eu.battle.net` solo contienen datos de grupos de batalla y reinos de Europa.

En este caso nos vamos a centrar en las regiones para Diablo III. Puede ser que esta información cambie para otros juegos como Starcraft o WoW.

Las regiones y los datos a los que tienen acceso son los siguientes:

Región Datos US [Battle.net](http://Battle.net), WoW, D3, SC2 EU [Battle.net](http://Battle.net), WoW, D3, SC2 KR [Battle.net](http://Battle.net), WoW, D3, SC2 TW [Battle.net](http://Battle.net), WoW, D3, SC2 CN [Battle.net](http://Battle.net), WoW, D3, SC2 Aunque estas son todas las regiones que podemos utilizar, la región de China (CN) no la vamos a usar en nuestra aplicación. Tiene un funcionamiento distinto al resto de las regiones. Por eso, para este curso la dejaremos de lado.

Diablo III APIs
---------------

Diablo III nos ofrece dos tipos de APIs, que tienen URLs diferentes y usaremos de forma distinta en nuestra aplicación.

En este curso, construirás la aplicación de D3PF utilizando estos dos tipos de APIs. Guárdate los enlaces a la documentación de las APIs, pues las usaremos a menudo para consultar cómo se traen los datos, parámetros requeridos, etc.

### APIs de comunidad

Las APIs de comunidad de Diablo III, nos van a traer **datos del perfil** del usuario que estemos buscando, como por ejemplo, los héroes que tiene o élites que ha matado a lo largo del tiempo.

Consulta la información detallada aquí: [https://develop.battle.net/documentation/diablo-3/community-apis](https://develop.battle.net/documentation/diablo-3/community-apis)

### APIs de datos

A través de las APIs de datos del juego de Diablo III, podemos obtener información sobre las temporadas, los rankings y las eras (las eras son parecidas a las temporadas, un espacio temporal limitado)

> 📗 Consulta la información detallada aquí: [https://develop.battle.net/documentation/diablo-3/game-data-apis](https://develop.battle.net/documentation/diablo-3/game-data-apis)

Acceso a las APIs: Clientes
---------------------------

Para poder consumir las APIs de Diablo III, como ya sabes, vas a necesitar un token. Dicho token es el resultado de hacer una llamada http de tipo POST a un servidor de Blizzard con unos parámetros específicos.

Lo que nos devuelva dicha llamada será, si todo ha ido bien, el token. Una vez que tengamos el token, lo guardaremos en nuestra aplicación de forma temporal. Y cada vez que hagamos una llamada a una API del juego usaremos este token.

Para poder obtener el token, vas a tener que crear un cliente. Deberías crear un cliente por cada aplicación, no utilices el mismo cliente en varias aplicaciones.

Crea tu cliente de acceso a APIs desde este enlace: [https://develop.battle.net/access/clients/create](https://develop.battle.net/access/clients/create)

![Formulario](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/create-client.png)

Rellena el formulario y dale a crear:

*   **Client Name**: te va a servir para identificar los distintos clientes que tengas. Puedes poner, por ejemplo, “D3PF” que es el nombre de la app.
*   **Redirect URIs**: Este campo no lo vamos a usar por el tipo de flujo OAuth que estamos usando.
*   **Service URL**: De momento lo dejas en blanco. No te olvides de marcar el checkbox de “I do not have a service URL for this client.” Cuando tengas tu app subida en la nube, deberás volver a editar la información de este cliente y actualizar este campo.
*   **Intended Use**: ¿Para qué lo vas a usar? ¿Cómo lo vas a usar? Responde a estas preguntas.
*   Para el caso de esta app puedes poner algo parecido a esto: “_Try the new apis and provide players information about their D3 characters_”, que significa que vas a usar las APIs para “probar las nuevas APIs y proporcionar información sobre los personajes de D3”

Una vez se haya creado, deberías ver algo parecido a esto:

![Client](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/01/edit-client.png)

Durante este curso, aprenderás a obtener un token de acceso de los servidores de Blizzard. Para ello, vas a usar el `clientID` y el `clientSecret`.

No compartas tu `clienteSecret` con nadie, intenta guardarlo en un lugar seguro.

Más adelante verás un posible método para tener estos datos de forma privada, pero accesibles desde la aplicación. ¿Cómo te imaginas que lo haremos?

Todos los clientes tienen unos límites a la hora de consumir APIs. Para evitar sobrecargas en los servidores, las APIs tienen las siguientes restricciones:

*   Cuota a largo plazo: `36,000` peticiones por hora
*   Cuota a corto plazo: `100` peticiones por segundo

Puedes gestionar todos tus clientes desde aquí: [https://develop.battle.net/access/clients](https://develop.battle.net/access/clients)

  

Antes de pasar a la siguiente lectura deberías haber creado tu cliente y tener tu `ClientId` y tu `ClientSecret`.

¡Perfecto! Ya tienes todo lo necesario para empezar a darle forma a la app en Vue. ¡Dejemos la teoría de lado y empecemos a _picar_ código!


## 3. Comandos del Proyecto :heavy_check_mark:

Estos son los comandos de la aplicación que tenemos disponibles desde la terminal, cuando estamos en la carpeta del proyecto. Puedes verlos en el bloque de `scripts` del fichero `package.json`.

De momento solo estamos usando el de ejecutar el entorno de desarrollo, más adelante explicaremos el resto:

```bash
# Instala las dependencias del proyecto
npm install

# Ejecuta el entorno de desarrollo
npm run serve

# Compila y construye para producción
npm run build

# Ejecuta los test unitarios
npm run test:unit

# Ejecuta los test end-2-end
npm run test:e2e

# Linting y corrección de archivos
npm run lint
```

Estructura de carpetas
======================

En esta lectura vas a entender cuáles son las carpetas que vamos a utilizar durante el curso.

Después de crear el proyecto con `vue create`, deberías tener una estructura de carpetas como esta:

![project-files](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/02/project-files.png)

Lo primero que vamos a hacer es crear todas las carpetas que va a utilizar la aplicación. Para posteriormente explicarlas.

A partir de ahora trabajaremos sobre la carpeta `/src`

Por lo tanto, dentro la carpeta `/src`, crearemos las siguientes carpetas: `api`, `directives`, `filters`, `layouts`, `mixins`, `plugins` y `utils`.

Esta es la estructura de directorios que deberías ver:

![project-files](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/02/folders.png)

Estos son los directorios que vamos a usar durante el desarrollo de esta aplicación. Esto no quiere decir que siempre tengas que seguir este modelo. Esto es solo un ejemplo, que es el que suelo usar habitualmente en mis proyectos.

Esta es una de las características que me gustan de Vue, la libertad que ofrece para hacer las cosas a tu manera.

Carpetas
========

Vamos a explicar que haremos con cada carpeta:

*   `/api`: Archivos con las llamadas HTTP a las APIs. Importaremos [_axios_](https://github.com/axios/axios) y lo utilizaremos para obtener los datos del juego.
*   `/assets`: En esta carpeta tendremos archivos CSS globales e imágenes, es decir, contenido estático.
*   `/componets`: Aquí estarán los componentes reusables de nuestra aplicación. Piensa por ejemplo, en un componente _loading_ que podrá ser usado varias veces a lo largo de la app.
*   `/directives`: Las directivas personalizadas que hagas estarán aquí. Ejemplos de directivas en vue son: `v-if`, `v-for`, etc. Cuando creemos una directiva personalizada, la alojaremos en esta carpeta.
*   `/filters`: Dentro de esta carpeta estarán los filtros que usaremos para darle formato a los datos de nuestra vista.
*   `/layouts`: Los layouts de nuestra app. Serán la estructura base sobre la que inyectaremos nuestras vistas. Suelen tener el _header-bar_ y el _footer_ común a toda la app.
*   `/mixins`: Los mixins (fragmentos de código reusable por nuestros componentes) los encuentras en esta carpeta.
*   `/plugins`: Esta carpeta puede llevar a confusión porque, realmente, lo que alojaremos aquí no son plugins que creemos para Vue, sino que tendremos librerías de terceros.
*   Por ejemplo [_Bootstrap-Vue_](https://bootstrap-vue.js.org/), la librería de componentes que usaremos a lo largo del curso.
*   `/router`: Controlaremos las rutas de nuestra aplicación desde aquí.
*   `/store`: El estado de nuestra aplicación. Lo gestionaremos a través de [_Vuex_](https://vuex.vuejs.org/).
*   `/utils`: Carpeta con funciones generales o que no tienen una temática definida. No es conveniente abusar de esto. Si tienes mucho contenido aquí quiere decir que deberías agrupar funcionalidades en otro directorio.
*   `/views`: Aquí estarán todas las vistas de nuestra aplicación. Hay que recordar que, en Vue, todo son componentes, y, en este caso, dichos componentes hacen de vistas de nuestra aplicación.

Estas son las carpetas que usaremos a lo largo de nuestro proyecto. Ya sabes que Vue nos da flexibilidad, por lo tanto no es obligatorio seguir estas pautas a la hora de crear nuestro proyecto.

Una buena manera de ver otras formas o estructuras es revisar cómo están hechos los proyectos de otras personas, por ejemplo, en GitHub.

> **¿Tienes proyectos de Vue en GitHub? ¿Qué arquitectura utilizas? Muestra tus proyectos en el sistema de comentarios**

Vistas
======

Vamos a cambiar la forma de trabajar con las vistas. Actualmente tienes esto:

![default-views](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/02/default-views.png)

Dentro de la carpeta `/views` vamos a cambiar los componentes de `Home.vue` y `About.vue`.

Para este proyecto la forma de trabajar con la mayoría de ficheros va a ser la siguiente:

*   Primero creamos una carpeta que tendrá el nombre de nuestro componente (en este caso, de nuestra vista). Por lo tanto, creamos la carpeta `/Home`.
*   Lo segundo, es mover el componente `Home.vue` a la carpeta `/Home`.
*   Por último, tenemos que renombrar el componente vista que acabamos de mover. Le cambiamos el nombre de `Home.vue` a `Index.vue`. (Recuerda, todos los nombres de las carpetas dentro de la carpeta de vistas (`/views`) los vas a crear con la primera letra en mayúscula)
*   Durante este proyecto, todos los componentes que veas que se llamen `Index.vue` van a ser el componente de entrada principal, del cual dependerán los demás componentes.

Repite estos pasos con el componente `About.vue` y al final tendrías algo como esto:

![views-complete](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/02/views-complete.png)

Si tienes tu servidor del proyecto levantado, seguramente te hayan aparecido un par de errores en la terminal.

![views-complete](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/02/terminal-err-1.png)

Esto es porque hemos cambiado el path de nuestros componentes vistas, y no hemos cambiado el archivo que controla las rutas. Vamos a cambiarlo.

Rutas
=====

Por defecto, en nuestro fichero de rutas `/router/index.js`, tenemos estas rutas:

```javascript
import Vue from 'vue'
import VueRouter from 'vue-router'
import Home from '../views/Home.vue'

Vue.use(VueRouter)

const routes = [
  {
    path: '/',
    name: 'Home',
    component: Home
  },
  {
    path: '/about',
    name: 'About',
    // route level code-splitting
    // this generates a separate chunk (about.[hash].js) for this route
    // which is lazy-loaded when the route is visited.
    component: () => import(/\* webpackChunkName: "about" \*/ '../views/About.vue')
  }
\]

const router = new VueRouter({
  routes
})

export default router
```

El error de consola viene porque los componentes vista que teníamos antes han cambiado de lugar.

Actualizamos el path de nuestras vistas con el siguiente contenido:

```javascript
import Vue from 'vue'
import VueRouter from 'vue-router'
-import Home from '../views/Home.vue'
+import Home from '../views/Home/Index.vue'

Vue.use(VueRouter)

const routes = [
  {
    path: '/',
    name: 'Home',
    component: Home
  },
  {
    path: '/about',
    name: 'About',
    // route level code-splitting
    // this generates a separate chunk (about.\[hash\].js) for this route
    // which is lazy-loaded when the route is visited.
-    component: () => import(/\* webpackChunkName: "about" \*/ '../views/About.vue')
+    component: () => import(/\* webpackChunkName: "about" \*/ '../views/About/Index.vue')
  }
\]

const router = new VueRouter({
  routes
})

export default router
```

Una vez hayas cambiado esto, no deberías tener ningún error en la consola. Más adelante retomaremos este fichero, pero de momento lo dejamos así.


## 4. Instalar librerías :heavy_check_mark:

En este paso, vamos a instalar todas las librerías que va a usar nuestro proyecto de Diablo III.

Utilizaremos Bootstrap con Vue como framework de componentes. Esto nos ayudará a generar y crear rápidamente la estructura de nuestro proyecto: [Bootstrap-vue](https://bootstrap-vue.js.org/)

Para hacer las llamadas a las APIs utilizaremos [axios](https://github.com/axios/axios.git), que es potente y muy fácil de usar.

En algunas ocasiones, necesitaremos formatear algunos valores numéricos. Para ello usaremos [numeral.js](http://numeraljs.com/) a través de un filtro que implementaremos más adelante.

Más adelante instalaremos [_fontawesome_](https://fontawesome.com/), la fuente de íconos que tanto nos gusta. Por ahora la dejaremos de lado, volveremos a esto más tarde.

Para instalar las librerías, escribimos el siguiente comando en la terminal:

```bash
npm install bootstrap-vue axios numeral --save
```

Esto nos instalará las tres librerías y actualizará el `package.json` de nuestro proyecto. El bloque de dependencias (_dependencies_) se vería así:

```diff
"dependencies": {
+ "axios": "^0.19.2",
+ "bootstrap-vue": "^2.4.0",
	"core-js": "^3.6.4",
+ "numeral": "^2.0.6",
	"vue": "^2.6.11",
	"vue-router": "^3.1.5",
  "vuex": "^3.1.2"
}
```

Hora de configurar **Bootstrap-Vue** para poder usarlo en nuestro proyecto.

En el fichero principal donde se instancia Vue, `main.js` , agregamos las siguientes líneas:

```javascript
// Traer la librería
import BootstrapVue from 'bootstrap-vue'

// Traer el css
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

// Darlo de alta
Vue.use(BootstrapVue)
```

> Puedes ver más acerca de los plugins en Vue [aquí](https://vuejs.org/v2/guide/plugins.html).

Tu fichero `main.js`, cuando lo actualices, debería tener el siguiente contenido:

```javascript
// Paquetes de npm
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'

// Archivos locales de nuestra App
import App from './App.vue'
import router from './router'
import store from './store'

// CSS global
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

// Configuración extra
Vue.use(BootstrapVue)
Vue.config.productionTip = false

// Instancia principal de Vue
new Vue({
  router,
  store,
  render: h => h(App)
}).$mount('#app')
```

Hemos dado de alta la librería de componentes Bootstrap-Vue a nivel global en nuestro proyecto. A continuación tenemos que probar que funciona.

Cambia el contenido del archivo `/components/HelloWorld.vue`. Hay que borrar todo el contenido del `template` (es decir, del HTML) y poner lo siguiente:

```javascript
<template>
  <div class="hello">
    <b-button>Just a Button!</b-button>
  </div>
</template>
```

Si vas al navegador, y abres tu aplicación, deberías ver el botón que acabamos de insertar:

![BS-vue](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/03/bootstrap-vue.png)

¡Genial! Ya hemos instalado y configurado Bootstrap. ¡Vamos a la siguiente lectura!


## 5. Carpeta API :heavy_check_mark:

Hora de configurar **axios**, la librería que utilizaremos para hacer las llamadas a las APIs de Diablo III. Vamos a tener dos tipos de llamadas a las APIs:

*   La llamada de OAuth, para obtener el token de acceso.
*   Las llamadas a las APIs que nos van a devolver los datos del juego: perfil de usuario, objetos, etc.

Por lo tanto, en la carpeta `/api` vamos a crear varios ficheros JavaScript, que contendrán las funciones con las llamadas a las APIs que necesitemos. Creamos los tres ficheros: `oauth.js`, `search.js` y `season.js`.

Dentro de nuestra carpeta `/api` deberían estar los archivos de la siguiente forma:

```markdown
📂 src/
└──📂 api/
   ├── oauth.js
   ├── search.js
   └── season.js
```

> Puedes leer la documentación del flujo OAuth desde este enlace: [https://develop.battle.net/documentation/guides/using-oauth/client-credentials-flow](https://develop.battle.net/documentation/guides/using-oauth/client-credentials-flow)

Abrimos el fichero `oauth.js` con nuestro editor de texto, y vamos a empezar a configurar axios para utilizarlo y hacer una llamada HTTP de tipo POST para obtener el token.

Recuerda que el `clientId` y el `clientSecret` los hemos creado anteriormente y puedes acceder a ellos en este enlace: [https://develop.battle.net/access/clients/](https://develop.battle.net/access/clients/)

```javascript
// oauth.js

// Traemos el método post de 'axios'
import { post } from 'axios'

// Cogemos los datos de nuestra cuenta de Blizzard
// 🔥 Recuerda que debes usar tus datos a la hora de hacer las llamadas a las APIs
// 🔥 Como dice la documentación, tienes un máximo de llamadas por segundo y por hora a la API. 
// 🔥 Estos datos deberían ser privados
const clientId = process?.env?.clientId || 'db5d7d6e7db543e0a3e13cf5812ce76'
const clientSecret = process?.env?.clientSecret || 'wuf4Ym9jX5kOurOUnmnB8wdBO6VKSm6'

// API URL para hacer oauth
const region = 'eu'
const API_URL = `https://${region}.battle.net/oauth/token`
```

Ya tenemos los datos necesarios para obtener el token definidos. Es hora de crear la función que haga uso de estos datos. Por lo tanto, en nuestro fichero `oauth.js` añadimos el siguiente contenido:

> 💡 Puedes ver la documentación completa de la configuración de axios en [este enlace](https://github.com/axios/axios#request-config).

```javascript
// ...oauth.js

// Creamos la función getToken
function getToken () {
  
  // Creamos un objeto de tipo 'FormData', que es un conjunto de pares clave/valorconst body = new FormData()
  
  // Con 'append', le agregamos la clave 'grant_type' y el valor 'client_credentials'
  body.append('grant_type', 'client_credentials')
  
  // En este objeto llamado 'config' vamos a insertar algunos parámetros de configuración
  // que necesitamos para hacer la llamada.
  const config = {
    headers: { 'Content-Type': 'multipart/form-data' },
    // Nuestros datos de cliente para OAuth: id y secret
    auth: { username: clientId, password: clientSecret }
  }

  // Hacemos una peticion POST
  // Le pasamos la URL como primer parámetro
  // Como segundo, el body, que es un FormData
  // Y la configuración como tercer argumento
  return post(API_URL, body, config)
}

// Exportamos la función para poder usarla más tarde
export {
  getToken
}
```

Lo único que hemos hecho ha sido seguir lo que dice la [documentación](https://develop.battle.net/documentation/guides/using-oauth/client-credentials-flow) de [battle.net](http://battle.net) acerca de cómo obtener un token para utilizarlo en las llamadas a las APIs:

> To request access tokens, an application must make a POST request with the following multipart form data to the token URI: **grant_type=client_credentials**

> The application must pass basic HTTP auth credentials using the **client_id** as the user and **client_secret** as the password.

🔥 Bonus: Los formularios de HTML tienen 3 tipos de _encoding_:

*   `application/x-www-form-urlencoded` (valor por defecto)
*   `multipart/form-data` (este es el que hemos usado)
*   `text/plain` (no deberías usar este nunca)

Ya tenemos la función para obtener el token. Prueba a hacer una llamada de prueba con [Postman](https://www.postman.com/) para ver si funciona.

> **¿No usas Postman? ¿Qué alternativa a Postman usas?**

Lo siguiente que vamos a hacer es ir al fichero principal (`main.js`) y trabajar sobre él para hacer la llamada a la API, obtener el token de acceso y posteriormente guardarlo.


## 6. Obtener el token :heavy_check_mark:

En el fichero `main.js` tenemos la instancia principal de Vue. Aquí es donde vamos a trabajar para obtener el token y posteriormente guardarlo en el _Store_ con Vuex.

El proceso que hay que seguir es el siguiente:

*   En el momento en el que la instancia principal de Vue dispare el hook `created`, hay que llamar a la función que acabamos de crear para obtener el token
*   Lo segundo es guardar el token en el estado de nuestra aplicación con la ayuda de Vuex

Existen varias formas de hacer esto. Vamos a aprender a llamar a una acción (_dispatch_) de Vuex desde la instancia principal de Vue, que aunque no es la mejor forma de hacerlo, a efectos prácticos es muy efectivo.

Creamos una función llamada _init_ dentro de _methods_ y el único código que vamos a poner de momento es un `console.log`. A continuación, llamamos a esta función desde el hook _created_.

Tu código se vería así:

```javascript
// main.js

new Vue({
  router,
  store,
  methods: {
    // Nuestra función
    init () {
      console.log('Hola 🌝')
    }
  },
  // Hook created
  created () {
    this.init()
  },
  render: h => h(App)
}).$mount('#app')
```

Ve al navegador, abre la consola y fíjate que se imprima el mensaje.

![c.log](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/05/console-log.png)

Vuex + Módulos
--------------

En nuestra función _init_ vamos a llamar a otra función que estará en Vuex. Vamos a crear dicha función en el módulo correspondiente.

Para ello, abrimos la carpeta del store de nuestra app `/src/store` y creamos un nuevo directorio llamado `modules`. Dentro, creamos un archivo JavaScript: `oauth.js`. Deberías tener algo como esto:

```markdown
📂 /src
└──📂 /store
   ├──📂 /modules
   │  └── oauth.js
   └── index.js
```

Como buenos profesionales que somos, vamos a separar nuestro _store_ en módulos (aunque, para este proyecto tan pequeño, no sea necesario), para tenerlo mejor ordenado, y, además, estaremos usando _namespaces_, para que nos sea más fácil gestionar el estado en caso de que nuestro proyecto crezca, por lo tanto, más escalable.

> 📗 Puedes leer más acerca de los módulos en Vuex en este enlace: [https://vuex.vuejs.org/guide/modules.html](https://vuex.vuejs.org/guide/modules.html)

Abrimos el recién creado módulo `oauth.js` y escribimos lo siguiente:

```javascript
// oauth.js

// Importamos nuestra función que obtiene el token
// @ es un alias para /src
import * as oauth from '@/api/oauth'

// Creamos el objeto con "Espacio de Nombres"
export default {
  namespaced: true,
  state: {},
  mutations: {},
  actions: {}
}
```

Estos son los tres bloques que vamos a usar en nuestro módulo:

*   _state_ (el estado de nuestro módulo)
*   _mutations_ (las mutaciones que, valga la redundancia, mutarán nuestro estado)
*   _actions_ (las acciones que llamarán a nuestras mutaciones).

Necesitamos hacer varios cambios en nuestro código. Lo primero es crear una variable que guarde el token, que por defecto tendrá `null` como valor. Lo creamos de la siguiente forma:

```javascript
state: {
  accessToken: null
},
```

Lo segundo es crear la función que cambie (mute) el estado que le estemos pasando. Esta función recibe 2 parámetros como argumentos: el estado de nuestro módulo y el payload (o valor que queremos guardar). Con esto podemos indicarle que cambie el `accessToken` por el valor que le pasemos en el _payload_. Cuando lo queramos borrar, le pasamos `null`.

```javascript
mutations: {
  SET_ACCESS_TOKEN (state, payload) {
    state.accessToken = payload
  }
}
```

Ya tienes la variable y la función que cambia el valor de dicha variable. Veamos ahora cómo se obtiene el token y cómo se guarda en el estado de nuestra aplicación. Entra en juego el bloque de _actions_:

```javascript
actions: {

  // Creamos la función getToken, que recibe como parámetro el objeto `context`
  // Gracias a la asignación de desestructuración de JavaScript, recogemos `commit` como argumento
  getToken ({ commit }) {
    // Pasos:
    //  1 - Hacer llamada HTTP para obtener el token
    //  2 - Si va OK, guardar el token en 'accessToken'. Continuar el flujo normal
    //  3 - Si hay errror, limpiar el token de 'accessToken', mostrar log del error

    // Paso 1
    oauth.getToken()
      .then(({ data }) => {
        // Paso 2: Guardamos el valor del token llamando a nuestra mutación
        commit('SET_ACCESS_TOKEN', data.access_token)
      })
      .catch((err) => {
        // Paso 3: En caso de error limpiamos el token
        commit('SET_ACCESS_TOKEN', null)
        console.log('Error OAuth: ', err)
      })
      .finally(() => {
        // Por ahora no hacemos nada más aquí
        console.log('Done!')
      })
  }
}
```

> 📗 Puedes ver la documentación relativa al constructor de Vuex aquí: [https://vuex.vuejs.org/api/](https://vuex.vuejs.org/api/#vuex-store-constructor-options)

Ya tenemos nuestra funcionalidad para obtener el token creada. Ahora solo queda llamarla desde la instancia principal de Vue y probar que todo funciona.

Las acciones en Vuex se llaman a través de _dispatch_. Esto es lo que vamos a hacer desde nuestro método `init` en el archivo `main.js`.

```javascript
// main.js

methods: {
  init () {
    store.dispatch('oauth/getToken', null, { root: true })
  }
}
```

Si abres la consola de tu navegador, verás que hay un error:

```javascript
🚫 \[vuex\] unknown action type: oauth/getToken
```

Eso quiere decir que Vuex no sabe de que le estamos hablando. Es normal, ya que no hemos dado de alta nuestro módulo de _OAuth_ en Vuex. ¡Vamos a ello!

Tenemos que editar el archivo `/store/index.js`:

Antes teníamos esto:

```javascript
// store/index.js

import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)

export default new Vuex.Store({
  state: {},
  mutations: {},
  actions: {},
  modules: {}
})
```

Lo que vamos a hacer ahora es borrar todo, excepto el bloque de modules, a la vez que importamos el módulo de `oauth.js` y lo damos de alta en el Store.

```javascript
// store/index.js

import Vue from 'vue'
import Vuex from 'vuex'

// Importar oauth
import oauth from './modules/oauth'

Vue.use(Vuex)

export default new Vuex.Store({
  // Aquuí registramos todos los módulos
  modules: {
    oauth
  }
})
```

Si cargas la aplicación y abres la consola del navegador, deberías ver el mensaje que pusiste en el `finally()`, en este caso verías el log del `Hola` y del `Done!`.

Si revisas la pestaña de “Network” o “Red” en las herramientas para desarrolladores de tu navegador, deberías ver algo como esto:

![network-tab](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/05/network-tab.png)

Vemos que la petición se está haciendo y nos devuelve los datos. Para comprobar si están guardándose o no, tienes que ir a las DevTools de Vue y revisar la pestaña de Vuex.

> Si no conoces las Vue DevTools, una extensión para el navegador, ¡instálalas ahora mismo!: [https://github.com/vuejs/vue-devtools](https://github.com/vuejs/vue-devtools)

![dev-tools](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/05/dev-tools.png)

En la parte derecha se ve un registro (log) de las mutaciones que han ocurrido hasta el momento, y a la izquierda se ve el estado actual del _Store_ o estado de nuestra app.

¡Perfecto! Hemos obtenido el token y lo hemos guardado. Está disponible desde cualquier parte de la aplicación. Ahora podrás usarlo cuando lo necesites.


## 7. Componente Loading :heavy_check_mark:

Componente Loading
==================

Actualmente, cuando la app carga por primera vez, estamos haciendo una llamada http de tipo POST a una API de Blizzard, cuya respuesta es el token de acceso.

Estaría bien si pudiéramos mostrar un componente de “cargando” (o loading) mientras se está haciendo la llamada a la API y una vez haya terminado la petición, mostrar el contenido de nuestra app.

Lo más probable es que a dicho componente _Loading_ tengamos que usarlo en más zonas del proyecto, no solo desde el `main.js`. Por lo tanto, puede ser una buena idea crear el componente _Loading_ en `/components` y dejarlo preparado para pueda usarse desde cualquier parte de nuestra app.

Vamos a nuestra carpeta `/components` y creamos un archivo con el nombre `BaseLoading.vue`. Dentro escribimos lo siguiente:

```javascript
<template>
  <!--Clases CSS de Bootstrap-->
  <div class="loading-wrapper text-center py-5">
    <div class="spinner-wrapper w-100">
      <!--Componente Spinner de Bootstrap 🔄-->
      <b-spinner class="spinner" label="Loading..." :type="type" :variant="variant"/>
    </div>
    <h1 class="my-5">Loading...</h1>
  </div>
</template>

<script>
export default {
  name: 'Loading',
  // Propiedades que soporta nuestro componente
  props: {
    variant: {
      required: false,
      type: String,
      // Valor por defecto, en caso de que no le pasemos esta propdefault: 'info',
      validator: (value) => {
        // Función validadora:// El valor de la prop debe coincidir con una de estas palabras
        return [
          'primary',
          'secondary',
          'danger',
          'warning',
          'success',
          'info',
          'light',
          'dark'
        ].indexOf(value) !== -1
      }
    },
    type: {
      required: false,
      type: String,
      default: 'border',
      validator: (value) => {
        return ['border', 'grow'].indexOf(value) !== -1
      }
    }
  }
}
</script>

<style lang="stylus">
  .spinner-wrapper.spinner
    width 4rem
    height 4rem
</style>
```

Copiamos el siguiente código en nuestro archivo, que lo único que va a hacer es poner un componente de _Spinner_ de Bootstrap en nuestra página, de forma centrada y con un margen y un padding específico.

Además, a través de las `props` le hemos dicho a nuestro componente que puede soportar 2 atributos (o propiedades):

*   `variant`: que es el color del spinner (puede ser ‘primray’, ‘secondary’, etc). No es obligatorio pasarle esa propiedad, y en caso de que no se le pase ningún valor, por defecto el `variant` será `info`.
*   `type`: puede ser de dos tipos: un círculo que crece (_grow_) o un spinner que gira sobre si mismo (_border_), por defecto, si no le pasamos ningún valor, será `border`.

Ambas propiedades tienen una función que valida el valor de nuestra prop:

*   Tiene que ser de tipo `String`
*   No es obligatorio pasarle un valor
*   Definimos un valor por defecto
*   Validamos, a través de una función, que el valor de la cadena de texto que le pasemos sea una de las que hemos definido en nuestra función validadora

Ahora que tenemos el componente _Loading_ creado, vamos a usarlo de modo que, cuando se esté haciendo la petición HTTP para obtener el token, mostremos este componente. Lo ocultaremos cuando se haya obtenido el token (o en caso de error).

Esto es lo que haremos en la siguiente lectura.


## 8. ¡Limpiemos el proyecto! :heavy_check_mark:

Antes de continuar, vamos a limpiar y a organizar un poco más el proyecto 🧹, a darle forma y color. ¡Una app de Diablo III no puede tener el fondo blanco!

Si te fijas bien, todavía tenemos el componente `HelloWorld.vue` dentro de `/src/components`. Vamos a eliminarlo, que ya no nos hace falta.

Una vez borrado, verás un error en la terminal, porque la vista _Home_ está haciendo uso de este componente que ya no existe. Tenemos que actualizar el contenido de la vista Home (`/views/Home/Index.vue`), que hacía uso de este componente. Podemos dejarlo así:

```javascript
<template>
  <div class="home">
    <img alt="Vue logo" src="../../assets/logo.png">
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: 'Home'
}
</script>
```

Del componente vista `/views/Home/Index.vue` vamos a borrar también la imagen con el logo de Vue. Podemos dejar una etiqueta `h1` con el nombre de la página, algo como esto:

```javascript
<template>
  <div class="home">
    <h1>Home Page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home'
}
</script>
```

Tu página _Home_ se vería así:

![HomePage](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/07/home-page.png)

La temática de nuestra aplicación esta basada en el juego Diablo III, por ello vamos a darle un toque más oscuro a nuestra web.

Vamos a cambiar los estilos de CSS de nuestro fichero `App.vue` y vamos a dejarlo así:

```javascript
<template>
  <!-- Esta parte no la hemos tocado aún -->
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>
      |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="stylus">
  #app
    padding 60px 0
    font-family 'Avenir', Helvetica, Arial, sans-serif
    -webkit-font-smoothing antialiased
    -moz-osx-font-smoothing grayscale
    color #ffffff // Le ponemos un color de letra blanco para que resalte
    background-color #15202b // Le cambiamos el color de fondo por un azul marino oscuro
</style>
```

Stylus
------

> 📗 Recuerda que estamos usando [Stylus Lang](https://github.com/stylus/stylus) como pre-procesador CSS. Lo que me gusta de Stylus es que es sencillo y limpio, a la vez que potente y funcional.

No hace falta que uses `;` para terminar las sentencias, o los `:` para separar la clave del valor, puedes omitir las llaves (`{`, `}`) de abrir/cerrar clases. Desde mi punto de vista, se ve mejor y más elegante. Aunque al final, cuando se “compile”, se verá como CSS normal y corriente.

Durante este curso, intentaremos seguir este estilo a la hora de escribir CSS con **Stylus**:

*   No llaves `{}`
*   No punto y coma `;`
*   No dos puntos `:`

Como son opcionales, los puedes usar si lo prefieres. Durante el curso, intentaremos seguir este estilo, lo más minimalista posible. Menos cosas que escribir 😉.


## 9. Layouts y Vuex Modules

Aunque la app se ve mejor sigue estando la falta de estilo, ya que se ve todo alineado a la izquierda.

![AlLeft](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/08/al-left.png)

Para arreglar esto vamos a hacer uso de las clases CSS de _Bootstrap_ y a crear un _Layout_. Con los _layouts_ conseguimos reutilizar código o componentes que se utilizan en todas las páginas, implementándolo una sola vez.

Creamos, dentro de la carpeta `/layouts` un archivo con el nombre `MainLayout.vue`

Y le damos el siguiente contenido:

```javascript
<template>
  <div class="container">
    <router-view/>
  </div>
</template>

<script>

export default {
  name: 'MainLayout'
}
</script>
```

> 📗 La etiqueta `<router-view />` es parte de la API de Vue Router. Lee la documentación aquí: [https://router.vuejs.org/api/#router-view](https://router.vuejs.org/api/#router-view)

Todas nuestras vistas que hagan _match_ a una ruta se van a inyectar dentro de esta etiqueta, `<router-view />`.

Por lo tanto, en el _layout_ principal podemos poner componentes como la barra de navegación (Navbar) o el footer, que van a ser iguales para todas las páginas.

Lo más probable es que dichos componentes no cambien entre páginas, por lo que es perfecto que estén aquí.

Los componentes de tipo _layout_ (recuerda, en Vue todo son componentes), son útiles cuando queremos tener varios tipos de páginas, por ejemplo, podemos tener un _layout_ específico para la página del _Login_, otro para las páginas de error y otro _layout_ para el resto de páginas.

En este curso vamos a crear 2 layouts distintos, uno para el loading y otro para el resto de páginas.

Debes crear los layouts según las necesidades de tu proyecto.

Ya tenemos el _layout_ principal de nuestra app. Vamos a crear el _layout_ de _Loading_, y para ello tenemos que crear otro componente dentro de la carpeta `/layouts`, con el nombre `LoadLayout.vue` y le dotamos del siguiente contenido:

```javascript
<template>
  <div class="loading-layout">
    <slot/>
  </div>
</template>

<script>

export default {
  name: 'LoadLayout'
}
</script>
```

> 📗 Un Slot en Vue es una funcionalidad inspirada en la especificación de Web Components con la finalidad de poder definir zonas de contenido distribuido. Puede contener cualquier plantilla de código, incluyendo HTML.

> Lee más acerca de los slots de Vue aquí: [https://es.vuejs.org/v2/guide/components-slots.html](https://es.vuejs.org/v2/guide/components-slots.html)

Bien, ya tenemos nuestro componente _Loading_, nuestro _MainLayout_ y nuestro _LoadingLayout_, pero nos sigue faltando un elemento. ¿Cómo controlamos si debemos mostrar el layout de _Loading_ o el layout principal?

Vamos a crear una variable en nuestro _Store_ que nos indique el estado de nuestra app, es decir, si está _loading_ o no.

Esto lo vamos a usar durante la petición del token de autenticación, es decir, mientras hacemos la llamada HTTP estaremos mostrando el _LoadingLayout_ con el componente _Loading_.

Por lo tanto, vamos a nuestra carpeta de `/store/modules` y creamos un nuevo módulo (archivo) llamado `loading.js`, que es el que va a gestionar el estado _Loading_ inicial de nuestra app.

No olvidemos que esto es solo una práctica y lo más probable es que hacer esto en un proyecto pequeño (como este) no tenga sentido.

```javascript
// store/modules/loading.js

export default {
  namespaced: true,
  state: {
    isLoading: false
  },
  mutations: {
    SET_LOADING (state, payload) {
      state.isLoading = payload
    }
  }
}
```

Hemos creado una variable (estado) `isLoading` con un espacio de nombres y una función (mutación) que cambia el valor de `isLoading`. Extremadamente sencillo, pero vamos a ver como trabajar con módulos y namespaces con Vuex.

Ahora sí, tenemos todos los ingredientes necesarios para crear nuestro _Loading_ mientras se hace la petición POST para obtener el token.

Por defecto, `isLoading` tiene valor `false`, por lo tanto, el primer paso es cambiarlo a `true` cuando estemos haciendo la petición de token.

Esto lo hacemos desde nuestro módulo `oauth.js` del Store, en nuestra función (acción) `getToken`.

```javascript
export default {
  // ...
  actions: {
    getToken ({ commit }) {
      commit('loading/SET_LOADING', true, { root: true })

      oauth.getToken()
        .then(({ data }) => {
          commit('SET_ACCESS_TOKEN', data.access_token)
        })
        .catch((err) => {
          commit('SET_ACCESS_TOKEN', null)
          console.log('Error OAuth: ', err)
        })
        .finally(() => {
          commit('loading/SET_LOADING', false, { root: true })
        })
    }
  }
}
```

Mientras dure la llamada HTTP ponemos el valor a `true` y cuando termine (con error o con éxito) lo ponemos a `false`.

Lo bueno de tener _namespaces_ con Vuex, aparte de modularizar por funcionalidad, es que no tendremos problemas con el nombrado de nuestras acciones y mutaciones porque llevan el prefijo del módulo, en este caso `loading/XXX`.

Ahora sí, ya tenemos todo listo para ir a nuestro fichero `App.vue` y decirle que mientras este esperando al token muestre el loading, y que cuando termine, muestre el layout principal, que contiene las vistas.

Aprovechamos para borrar los enlaces que venían por defecto. Nuestro fichero `App.vue`, en el bloque de _template_, es decir el HTML, se vería así:

```javascript
<template>
  <div id="app">

    <LoadLayout v-if="isLoading"><BaseLoading/></LoadLayout>

    <MainLayout v-else/>

  </div>
</template>
```

Y la parte del `<script>` tendría este contenido:

```javascript
<script>
import { mapState } from 'vuex'

import LoadLayout from './layouts/LoadLayout'
import MainLayout from './layouts/MainLayout'
import BaseLoading from '@/components/BaseLoading.vue'

export default {
  name: 'App',
  components: {
    MainLayout,
    LoadLayout,
    BaseLoading
  },
  computed: {
    // Uso: mapState(moduleName, { state })
    ...mapState('loading', {
      isLoading: 'isLoading'
    })
  }
}
</script>
```

> 📗 Lee más acerca de los mapState de vuex aquí: [https://vuex.vuejs.org/guide/state.html#the-mapstate-helper](https://vuex.vuejs.org/guide/state.html#the-mapstate-helper)

El proceso es el siguiente:

*   Desde Vuex nos traemos la funcionalidad de `mapState`
*   Importamos los 3 componentes que necesitamos (los 2 layouts que acabamos de crear y el componente de Loading)
*   A través de `mapState` podemos acceder a los valores del estado de nuestro módulo (en este caso nos interesa el módulo de `loading`) y utilizarlos en nuestro componente.
*   Para usar `mapState` con _namespaces_ lo único que tenemos que hacer es indicarle, antes de empezar a mapear el estado, a qué módulo nos referimos, es decir, ‘loading’. El nombre del módulo se corresponde con el nombre del fichero.
*   Como el módulo se llama `loading.js` tendremos que usar de nombre `loading` (sin la extensión). Con esto le decimos que solo nos interesa el estado del _loading_.
*   Con las directivas `v-if` y `v-else` mostramos un componente u otro según esté cargando o no. Si está _loading_ mostramos loading, en caso contrario mostramos la vista.

En el navegador, abrimos las Herramientas para desarrolladores (o DevTools), vamos a la pestaña de console y recargamos la app. Deberías ver el siguiente error:

![Vuex-Err](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/08/error-vuex.png)

¿Adivinas por qué es? Efectivamente, no hemos dado de alta el módulo en nuestro Store. Vamos a ello. Desde el fichero de `/store/index.js` agregamos lo siguiente:

```javascript
import Vue from 'vue'
import Vuex from 'vuex'

import oauth from './modules/oauth'
import loading from './modules/loading'

Vue.use(Vuex)

export default new Vuex.Store({
  modules: {
    oauth,
    loading
  }
})
```

Si vas al navegador deberías ver, si no hay ningún error, el componente Loading durante un pequeño espacio de tiempo y que después se carga la vista de la página _Home_

![Loading](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/08/loading.png)

El código completo de `App.vue` es el siguiente:

```javascript
<template><div id="app">

    <LoadLayout v-if="isLoading"><BaseLoading/></LoadLayout>

    <MainLayout v-else/>

  </div>
</template>

<script>
import { mapState } from 'vuex'

import LoadLayout from './layouts/LoadLayout'
import MainLayout from './layouts/MainLayout'
import BaseLoading from '@/components/BaseLoading.vue'

export default {
  name: 'App',
  components: {
    MainLayout,
    LoadLayout,
    BaseLoading
  },
  computed: {
    ...mapState('loading', {
      isLoading: 'isLoading'
    })
  }
}
</script>

<style lang="stylus">
  #app
    padding 60px 0
    font-family 'Avenir', Helvetica, Arial, sans-serif
    -webkit-font-smoothing antialiased
    -moz-osx-font-smoothing grayscale
    color #ffffff
    background-color #15202b
</style>
```

Vamos a la siguiente lectura, en la que veremos cómo mejorar nuestro _Layout

## 10. Assets

Antes de continuar, necesitamos tener un directorio en el cual guardar nuestros _assets_ (imágenes, estilos CSS, tipografías, etc.).

Por defecto, al crear el proyecto tenemos la carpeta `/assets` creada, con una imagen, el logo de Vue.

Lo primero que tenemos que hacer es borrar todo el contenido de la carpeta `/assets`.

Una vez que esté vacía, vamos a crear 3 carpetas: `img` (para las imágenes), `css` (para nuestros estilos CSS globales) y `fonts` (donde guardaremos las tipografías que instalemos en el proyecto).

Tu carpeta `/assets` debería verse así:

```markdown
📂 /assets 
   ├── 📂 /css
   ├── 📂 /fonts
   └── 📂 /img
```

Imágenes
========

Para agilizar el desarrollo del curso, descarga todas las imágenes de este repositorio ([https://github.com/baumannzone/diablo3-vue-platzi](https://github.com/baumannzone/diablo3-vue-platzi/tree/master/src/assets/img)) y guárdalas dentro de la carpeta de imágenes, en `/assets/img`. Las iremos explicando según las vayamos utilizando.

Fuentes
=======

Si has jugado alguna vez al juego de Diablo (al I, al II o al III) y has visto el resultado final de la app [https://diablo3.netlify.com](https://diablo3.netlify.com), te habrás dado cuenta que, en ciertas partes de la app, se hace uso de una tipografía muy especial.

Esta es la fuente que usa nuestra aplicación:

![d3pf-font](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/09/d3pf-font.png)

Esta es la tipografía oficial del juego:

![d3-font](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/09/d3-font.png)

El juego de Diablo tiene una tipografía o fuente muy reconocible. Para intentar aproximarnos lo máximo posible a esto, nos vamos a descargar una fuente que se asemeja bastante y que, desde mi punto de vista, ¡es muy chula!

La fuente se llama **DiabloHeavy** y la puedes descargar de manera gratuita desde aquí: [https://fontzone.net/font-details/diablo-heavy](https://fontzone.net/font-details/diablo-heavy).

En caso de que no esté disponible, puedes ir al [repositorio del proyecto](https://github.com/baumannzone/diablo3-vue-platzi/tree/master/src/assets/fonts) y descargar los archivos de la carpeta `/fonts`, en `assets`.

Estilos CSS
===========

Otra cosa que vamos a ver, es como tener estilos de CSS globales en nuestra aplicación. Esto puede sernos útil en varias ocasiones, cuando queremos sobrescribir los estilos de alguna librería externa, por ejemplo.

En este caso, no era necesario crear un archivo global de CSS, pero lo vamos a hacer por motivos prácticos.

Dentro de nuestra carpeta de `/css`, en `/assets`, vamos a crear un fichero css con extensión de Stylus (recuerda, el pre-procesador CSS del que hablamos antes). Crea el archivo con nombre `main.styl`. Aquí dentro, tendremos nuestro CSS global. Empezaremos cargando la fuente que acabamos de descargarnos, para tenerla disponible en nuestra aplicación.

Le agregamos este contenido a nuestro archivo `main.styl`:

```stylus
// ---------------------
// Diablo-Like Font · DiabloHeavy Font
// ---------------------

// Damos de alta la fuente con el nombre "DiabloHeavy" y cargamos todos los formatos
@font-face
  font-family "DiabloHeavy"
  src url("../fonts/diabloh.eot")
  src url("../fonts/diabloh.eot?#iefix") format("embedded-opentype"),
  url("../fonts/diabloh.otf") format("opentype"),
  url("../fonts/diabloh.svg") format("svg"),
  url("../fonts/diabloh.ttf") format("truetype"),
  url("../fonts/diabloh.woff") format("woff"),
  url("../fonts/diabloh.woff2") format("woff2")
  font-style normal
  font-weight normal

// Creamos una clase que tenga de tipografía la fuente de Diablo
.font-diablo
  font-family "DiabloHeavy", sans-serif
```

Más adelante retomaremos este fichero, pero de momento, podemos dejarlo así.

En cuanto tengamos registrado nuestro archivo CSS global en la aplicación, podremos usar la clase `.diablo-font` en cualquier elemento (con texto) de nuestra aplicación, en el que queramos renderizar dicha fuente.

Para registrarlo, lo único que tenemos que hacer es importarlo desde el fichero principal, `main.js`:

```javascript
// CSS global
import './assets/css/main.styl'
```

Puedes ponerlo debajo del CSS de la librería BootstrapVue. De esta forma estarás registrando dicho archivo CSS de manera global en tu proyecto y todas las clases que pongas ahí podrán ser usadas desde cualquier parte.

> Al crear el proyecto con el CLI de Vue, una de las opciones que teníamos era la de los “preprocesadores CSS”.

> Nosotros le indicamos que queríamos Stylus para el CSS, por lo tanto, cuando estamos escribiendo CSS con formato de Stylus, Webpack y sus amigos están transformando el código de Stylus a CSS válido. Y lo mejor, ¡no hemos tenido que configurar nada! 💃

Creo que ya podemos pasar al siguiente bloque de contenido, donde trabajaremos sobre el layout principal.

## 11. NavBar y Footer

En este bloque vamos a agregarle un poco más de contenido a nuestro layout principal. Vamos a crear el _NavBar_ y el _Footer_, que será genérico a toda la apliación.

Bootstrap nos proporciona un componente de [Navbar](https://bootstrap-vue.js.org/docs/components/navbar/#navbar) que soporta múltiples opciones.

Empezamos creando la carpeta `/HeaderBar` dentro de nuestro directorio de componentes `/components`, y dentro de esta creamos nuestro archivo principal: `Index.vue`.

Deberías tener el archivo creado en esta ruta: `/components/HeaderBar/Index.vue`, con este contenido:

<template><div class="header-bar"><div class="navigation-bar"><b-navbar toggleable="lg" type="dark" variant="dark"><b-navbar-brand :to="{ name: 'Home' }"><img src="@/assets/img/diablo-iii.svg" alt="D3" width="30"><span class="font-diablo ml-2">D3PF</span></b-navbar-brand></b-navbar></div>

  </div>
</template>

<script>

export default {
  name: 'HeaderBar'
}
</script>

En el proyecto original hay más componentes que no vamos a tocar en este curso, para que no se haga muy largo.

Recuerda que puedes revisar en cualquier momento el código fuente completo del proyecto en [https://github.com/baumannzone/diablo3-vue-platzi](https://github.com/baumannzone/diablo3-vue-platzi)

Vamos a crear el componente **Footer** del proyecto en `/components/Footer/Index.vue`. Para el Footer, puedes copiar esto:

<template><footer class="footer-bar mt-5"><PoweredByFoot :icons="icons"/>

    <hr class="my-5">

    <div class="row"><div class="col-sm-6 mb-sm-0 mb-5"><FootLinks/></div><div class="col-sm-6"><MadeByFoot/></div></div>

  </footer>
</template>

<script>
import MadeByFoot from './MadeByFoot'
import PoweredByFoot from './PoweredByFoot'
import FootLinks from './FootLinks'

export default {
  name: 'FooterBar',
  components: { FootLinks, PoweredByFoot, MadeByFoot },
  data () {
    return {
      icons: \[
        {
          classes: \[ 'fab', 'vuejs' \],
          color: '#4fc08d',
          href: 'https://vue.js.org/'
        },
        {
          classes: \[ 'fab', 'bootstrap' \],
          color: '#7952b3',
          href: 'https://bootstrap-vue.js.org/'
        },
        {
          classes: \[ 'fab', 'battle-net' \],
          href: 'https://develop.battle.net/documentation/diablo-3/community-apis'
        },
        {
          classes: \[ 'fab', 'github' \],
          color: '#e4e4e4',
          href: 'https://github.com/baumannzone'
        },
        {
          classes: \[ 'fab', 'font-awesome' \],
          color: '#0e95ff',
          href: 'https://fontawesome.com/'
        }
      \]
    }
  }
}
</script>

Dentro de este componente hay 3 componentes más. Vamos a crearlos:

###### `/Footer/FootLinks.vue`

<template><div><b-nav small align="start"><b-nav-item :to="{name: 'Home'}">Home</b-nav-item><b-nav-item :to="{name: 'About'}">About</b-nav-item><b-nav-item href="https://github.com/baumannzone/diablo3-vue-platzi" target="_blank">Github</b-nav-item></b-nav></div>
</template>

<script>
export default {
  name: 'FootLinks'
}
</script>

###### `/Footer/MadeByFoot.vue`

<template><p class="text-muted m-0 pt-1 pl-3 text-left text-sm-right"><small>
      Made by
      <a href="https://twitter.com/baumannzone" target="_blank">Jorge Baumann</a>
      for
      <a href="https://platzi.com/" target="_blank">Platzi</a></small></p>
</template>

<script>
export default {
  name: 'MadeByFoot'
}
</script>

###### `/Footer/PoweredByFoot.vue`

<template><div class="text-center "><p class="text-muted">Powered by</p>

    <ul class="list-inline"><li class="list-inline-item mx-2" v-for="(icon, idx) in icons" :key="idx"><a :href="icon.href" target="_blank" :title="icon.href"><font-awesome-icon :icon="icon.classes" class="fa-lg" :style="{'color': icon.color}"/></a></li></ul></div>
</template>

<script>
export default {
  name: 'PoweredByFoot',
  props: {
    icons: {
      required: true,
      type: Array
    }
  }
}
</script>

Hemos creado el footer de nuestra app con algunos links de utilidad, íconos de Fontawesome, etc.

Para poder ver la barra de navegación y el footer en nuestra app, tenemos que dar de alta en el layout principal dichos componentes.

Para ello, nos vamos a `/layouts/MainLayout.vue` y agregamos los componentes de _Footer_ y _NavBar_ que acabamos de crear:

<template><div class="container"><HeaderBar/>

    <router-view/>

    <FooterBar/></div>
</template>

<script>
import HeaderBar from '@/components/HeaderBar/Index'
import FooterBar from '@/components/FooterBar/Index'

export default {
  name: 'MainLayout',
  components: {
    HeaderBar,
    FooterBar
  }
}
</script>

Si te fijas, en la consola hay un error. Abrimos el navegador y en la terminal también hay un error:

![Error-fa](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/10/error-fa.png)

El error es el siguiente:

> 🚫 Unknown custom element: <font-awesome-icon> - did you register the component correctly? For recursive components, make sure to provide the “name” option.

Lo que quiere decir es que hay un componente, en concreto este `<font-awesome-icon>`, que estamos usando, pero que Vue no lo entiende, o no lo hemos dado de alta. Tal vez lo hayas visto, pero si no, en el footer que acabamos de crear estamos usando dicho componente para mostrar los íconos de los links.

Necesitamos hacer 2 cosas, primero instalar [FontAwesome](https://fontawesome.com/) (con npm) y lo segundo dar de alta dicho componente. Las instrucciones para instalarlo las tienes en este enlace: [https://fontawesome.com/how-to-use/on-the-web/using-with/vuejs](https://fontawesome.com/how-to-use/on-the-web/using-with/vuejs). Vamos a seguir la documentación para instalar este paquete.

Para instalar, escribe lo siguiente desde tu terminal:

npm i --save @fortawesome/fontawesome-svg-core @fortawesome/free-solid-svg-icons @fortawesome/vue-fontawesome @fortawesome/free-brands-svg-icons

Estamos instalando varios paquetes a la vez y le estamos indicando que queremos que nos los guarde en nuestro `package.json`.

Una vez instalados vamos a nuestro archivo principal `main.js` y le agregamos el siguiente contenido:

import { library } from '@fortawesome/fontawesome-svg-core'
// Iconos de tipo "Solid"
import { faSkull, faCrown, faDungeon, faHatWizard, faHammer, faGem } from '@fortawesome/free-solid-svg-icons'
// Iconos de tipo "Brand" (marcas o logos de empresas)
import { faVuejs, faBootstrap, faFontAwesome, faGithub, faBattleNet } from '@fortawesome/free-brands-svg-icons'
// El componente que vamos a utilizar
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

// Le añadimos los iconos que acabamos de importar (todos, los de tipo solid y de tipo brand)
library.add(
  faSkull,
  faCrown,
  faDungeon,
  faHatWizard,
  faHammer,
  faGem,
  faVuejs,
  faBootstrap,
  faFontAwesome,
  faGithub,
  faBattleNet
)

Vue.component('font-awesome-icon', FontAwesomeIcon)

Nuestro fichero `main.js` completo quedaría así:

import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'

// Font Awesome
import { library } from '@fortawesome/fontawesome-svg-core'
import { faSkull, faCrown, faDungeon, faHatWizard, faHammer, faGem } from '@fortawesome/free-solid-svg-icons'
import { faVuejs, faBootstrap, faFontAwesome, faGithub, faBattleNet } from '@fortawesome/free-brands-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

import App from './App.vue'
import router from './router'
import store from './store'

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

// CSS global
import './assets/css/main.styl'

// Le añadimos los iconos que acabamos de importar (todos, los de tipo solid y de tipo brand)
library.add(
  faSkull,
  faCrown,
  faDungeon,
  faHatWizard,
  faHammer,
  faGem,
  faVuejs,
  faBootstrap,
  faFontAwesome,
  faGithub,
  faBattleNet
)

Vue.use(BootstrapVue)
Vue.config.productionTip = false
Vue.component('font-awesome-icon', FontAwesomeIcon)

new Vue({
  router,
  store,
  methods: {
    // Nuestra función
    init () {
      console.log('Hola 🌝')
      store.dispatch('oauth/getToken')
    }
  },
  // Hook created
  created () {
    this.init()
  },
  render: h => h(App)
}).$mount('#app')

Ahora sí, Vue ya sabe como interpretar el componente que antes le parecía desconocido. Si abres la web de la aplicación, deberías ver algo como esto:

![app-footer](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/10/app-with-footer.png)Por ahora tenemos un token (OAuth) necesario para las llamadas a las APIs de Blizzard, un componente Loading, dos tipos de layouts diferentes (uno que carga el componente _Loading_ y otro donde se inyectan las vistas de nuestras rutas, que a su vez tiene un _Header_ y un _Footer_ bien estructurado en componentes).

Además hemos visto como instalar varias librerías, entre ellas _FontAwesome_, y hemos visto cómo darla de alta en nuestra app Vue.

¡Ya podemos continuar por donde lo habíamos dejado antes! Nos vemos en la siguiente lectura.


## 12. Refactorizando

Nuestro proyecto va creciendo, poco a poco, con librerías, configuraciones y demás contenido.
El fichero de arranque main.js está haciéndose un poco difícil de manejar debido a todo el contenido que le estamos metiendo.

Una buena idea puede ser llevarse todo el código de librerías de terceros a una carpeta externa. Esta carpeta ya la tenemos creada y se llama /plugins. Vamos a meter ahí el código de Bootstrap-Vue y de FontAwesome. Luego lo importaremos en el main.js y así quedará mas limpio y legible nuestro código.

Empezamos creando el fichero BootstrapVue.js dentro de /plugins, y le damos el siguiente contenido:

```javascript
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

Vue.use(BootstrapVue)
```
Tal y como dice la documentación, importamos BootstrapVue, nos traemos el CSS y después hacemos ‘uso’ de BootstrapVue desde Vue.

Hacemos lo mismo con FontAwesome, creamos el fichero fontAwesome.js dentro de /plugins y movemos todo el contenido que había en main.js a este fichero:

```javascript
import Vue from 'vue'

import { library } from '@fortawesome/fontawesome-svg-core'
import { faSkull, faCrown, faDungeon, faHatWizard, faHammer, faGem } from '@fortawesome/free-solid-svg-icons'
import { faVuejs, faBootstrap, faFontAwesome, faGithub, faBattleNet } from '@fortawesome/free-brands-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

library.add(
 faSkull,
 faCrown,
 faDungeon,
 faHatWizard,
 faHammer,
 faGem,
 faVuejs,
 faBootstrap,
 faFontAwesome,
 faGithub,
 faBattleNet
)

// Esta es la forma de registrar un componente global con Vue
// El primer parámetro es cómo queremos que se use/llame nuestro componente desde el HTML
// El segundo parámetro es la referencia al componente (que acabamos de importar)
Vue.component('font-awesome-icon', FontAwesomeIcon)
```
Tu carpeta de /plugins se vería así:

```markdown
📂 /plugins
   ├── bootstrapVue.js
   └── fontAwesome.js
```
Lo que hemos hecho es mover el todo el contenido de dichas librerías fuera del main.js y ponerlo en archivos independientes.
Ahora queda hacer referencia a estos archivos desde el main.js para que todo siga funcionando tal y como estaba antes. Lo puedes hacer de la siguiente forma:

```javascript
// BootstrapVue
import './plugins/bootstrapVue'

// Vue Font-Awesome
import './plugins/fontAwesome'
```
Ya que estamos en el apartado de refactorizar y estamos tocando el main.js, podemos quitar el console.log('Hola 🌝') que pusimos al principio, que ya no nos sirve para nada.
Tu fichero main.js completo se vería así:

```javascript
import Vue from 'vue'
// BootstrapVue
import './plugins/bootstrapVue'

// Vue Font-Awesome
import './plugins/fontAwesome'

import App from './App.vue'
import router from './router'
import store from './store'

// CSS global
import './assets/css/main.styl'

Vue.config.productionTip = false

new Vue({
  router,
  store,
  methods: {
    // Nuestra función
    init () {
      store.dispatch('oauth/getToken')
    }
  },
  // Hook created
  created () {
    this.init()
  },
  render: h => h(App)
}).$mount('#app')
```
Te habrás dado cuenta de que hemos importado Vue 2 veces, una para el fichero de BootstrapVue.js y otra vez para el de fontAwesome.js.
No te preocupes, no vamos a tener código duplicado y nuestra aplicación no va a ser el doble de grande. De esto se encarga Webpack, solo lo incluirá una vez en el bundle final.

¡Fíjate!, ahora nuestro archivo queda más limpio y legible 👏. Hemos agrupado contenido por funcionalidad. A partir de ahora, todas las librerías que vayamos metiendo las podemos dejar dentro de la carpeta /plugins para tener nuestro código más ordenado.

## 13. Home Page

Llevamos bastante tiempo trasteando con nuestro proyecto, pero apenas estamos avanzando. Hora de empezar a darle forma a nuestro buscador de perfiles de Diablo III.

Lo primero que tenemos que hacer es crear un formulario que busque el usuario según la región en la que estemos. Esto es importante ya que un usuario puede existir en una región, pero no estar en otra. Por lo tanto necesitamos los 2 parámetros:

*   BattleTag o Identificador de usuario, con el formato: _NombreCool#1234_
*   Región, que puede ser una de las siguientes: ‘US’, ‘EU’, ‘KR’, ‘TW’. La región de CN (China) la dejamos fuera en este ejemplo, que tiene una configuración especial, distinta al resto.

Antes de empezar con el formulario vamos a poner un título grande, que le de nombre a nuestra app.

Para ello creamos, dentro de nuestra carpeta vista `/Home`, dos componentes: `HomeForm.vue` y `HomeTitle.vue`. Quedaría así:

```markdown
📂 /views
   └──📂 /Home
      ├── Index.vue
      ├── HomeForm.vue
      └── HomeTitle.vue
```

Empezamos con el título, un componente bastante sencillo.

```javascript
<template>
  <div class="home-title text-center">
    <h1 class="my-5 font-diablo">Diablo 3 Profile Finder</h1>
    <p class="lead text-muted">
      Enter your
      <em>
        <a href="https://eu.battle.net/support/es/article/75767" target="_blank" title="Format: YourProfile#1234">battle-tag</a>
      </em>
      and select your region to see your profile!
    </p>
    <hr class="mt-5">
  </div>
</template>

<script>
export default {
  name: 'HomeTitle'
}
</script>
```

Ya estamos haciendo uso de nuestra tipografía _DiabloHeavy_. Mira la etiqueta `<h1>` y la clase que le hemos puesto. Dejamos el título centrado con un buen espaciado. Ya podemos incluirlo en nuestra _Home_ y ver que tal queda.

Para ello, simplemente vamos a traer el componente que acabamos de crear y a modificar nuestra vista (corresponde al archivo `/views/Home/Index.vue`) para dejarla de esta forma:

```javascript
<template><div class="home"><HomeTitle/></div>
</template>

<script>
import HomeTitle from './HomeTitle'

export default {
  name: 'Home',
  components: {
    HomeTitle
  }
}
</script>
```

Tu aplicación se debería ver así:

![con-titulo](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/12/con-titulo.png)

Para el formulario, vamos al componente `/Home/HomeForm.vue`. Vamos a crear un formulario con 2 inputs; uno va a ser una caja de texto y el otro será un select.

En la caja de texto el usuario podrá escribir su _BattleTag_. En el selector, podrá elegir entre una de las regiones que le mostremos.

Necesitaremos también un botón para controlar el envío del formulario. Bootstrap nos proporciona unos buenos componentes para trabajar con formularios, que en el fondo se renderizan en etiquetas HTML válidas.

Lo bueno de esto es que al pulsar la tecla _Enter_ de tu teclado se hará el _Submit_ (envío) del formulario. Nos aprovecharemos de esta funcionalidad por defecto que traen los formularios de HTML para mejorar la experiencia del usuario en nuestra app web.

Por último, haciendo uso del estándar de HTML, podemos indicarle a los _input_ de nuestro formulario que son requeridos con el atributo `required`. Esta será nuestra pequeña (y única) validación para nuestro proyecto. En el caso de un proyecto real, deberías validar tus formularios meticulosamente: formato, tamaño, nº caracteres, etc.

> 📗 Infórmate acerca de los atributos de un `<input>` de un formulario HTML en este enlace: [https://developer.mozilla.org/es/docs/Web/HTML/Elemento/input](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/input)

> Para la etiqueta `<select>`, puedes leer esto: [https://developer.mozilla.org/es/docs/Web/HTML/Elemento/select](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/select)

La parte del HTML de nuestro componente `HomeForm.vue` es la siguiente:

```javascript
<template>
  <div class="search-form my-5">
    <div class="row">
      <div class="col-12 col-md-8 offset-md-2">
        <!-- Formulario -->
        <b-form @submit.prevent="onSubmit">

          <!-- Grupo 1 (Input texto) -->
          <b-form-group id="input-group-1"label="BattleTag:"label-for="input-text"description="Format: YourProfile#1234">
            <b-form-input id="input-text"v-model="form.battleTag"type="text"size="lg"requiredplaceholder="BattleTag"/>
          </b-form-group>

          <!-- Grupo 2 (Selector de región) -->
          <b-form-group id="input-group-3" label="Region:" label-for="input-region">
            <b-form-select id="input-region" v-model="form.region" size="lg" :options="regions" required/>
          </b-form-group>

          <!-- Botón envío -->
          <div class="d-flex justify-content-end mt-5">
            <b-button type="submit" variant="primary" size="lg">
              Submit
            </b-button>
          </div>
        </b-form>
      </div>
    </div>
  </div>
</template>
```

En la parte de JavaScript de nuestro componente, vamos a necesitar el modelo asociado al formulario, el listado de regiones que queremos pintar en el selector de región y una función que haga algo cuando el formulario se envíe.

Por lo cual, el bloque `<script>` de nuestro componente quedaría así:

```javascript
import { regions } from '@/utils/regions'

export default {
  name: 'MainForm',
  data () {
    return {
      form: {
        battleTag: '',
        region: 'eu'
      }
    }
  },
  computed: {
    regions () {
      return regions.map(region => ({ value: region, text: region.toUpperCase() }))
    }
  },
  methods: {
    onSubmit () {
      const { region, battleTag } = this.form
      this.$router.push({ name: 'Profile', params: { region, battleTag: battleTag.replace('#', '-') } })
    }
  }
}
```

Para las regiones hemos creado una _computed property_ o propiedad computada que nos devuelve un array de objetos con las regiones en minúscula como _value_ y en mayúscula como texto a mostrar.

Tenemos que crear un nuevo archivo, de nombre `regions.js`, en la carpeta `/utils` para que esto funcione con el siguiente contenido:

```javascript
const regions = \['us', 'eu', 'kr', 'tw'\]

const locales = {
  us: 'en_US',
  eu: 'en_GB',
  kr: 'ko_KR',
  tw: 'zh_TW'
}

export {
  regions,
  locales
}
```

Código completo `HomeForm.vue`

```javascript
<template>
  <div class="search-form my-5">

    <div class="row">
      <div class="col-12 col-md-8 offset-md-2">
        <b-form @submit.prevent="onSubmit">

          <b-form-group id="input-group-1" label="BattleTag:" label-for="input-text" description="Format: YourProfile#1234">
            <b-form-input id="input-text" v-model="form.battleTag" type="text" size="lg" required placeholder="BattleTag"/>
          </b-form-group>

          <b-form-group id="input-group-3" label="Region:" label-for="input-region">
            <b-form-select id="input-region" v-model="form.region" size="lg" :options="regions" required/>
          </b-form-group>

          <div class="d-flex justify-content-end mt-5">
            <b-button type="submit" variant="primary" size="lg">
              Submit
            </b-button>
          </div>

        </b-form>
      </div>
    </div>
  </div>
</template>

<script>
import { regions } from '@/utils/regions'

export default {
  name: 'MainForm',
  data () {
    return {
      form: {
        battleTag: '',
        region: 'eu'
      }
    }
  },
  computed: {
    regions () {
      return regions.map(region => ({ value: region, text: region.toUpperCase() }))
    }
  },
  methods: {
    onSubmit () {
      const { region, battleTag } = this.form
      this.$router.push({ name: 'Profile', params: { region, battleTag: battleTag.replace('#', '-') } })
    }
  }
}
</script>
```

Cuando el formulario se envía, estamos haciendo un cambio de ruta (a una que aún no existe, de nombre `Profile`) y le estamos pasando por parámetro (`params`) los valores que acabamos de recuperar del formulario.

Ya casi lo tenemos, ¡probemos si funciona!

En nuestro componente principal de la vista `/Home`, es decir, en `/views/Home/Index.vue`, traemos y usamos el componente formulario que acabamos de crear; quedaría así:

```javascript
<template>
  <div class="home-view">

    <HomeTitle/>

    <MainForm/>

  </div>
</template>

<script>
import MainForm from './HomeForm'
import HomeTitle from './HomeTitle'

export default {
  name: 'HomeView',
  components: { HomeTitle, MainForm }
}
</script>
```

Se debería ver así:

![HomePage](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/12/home-page.png)

Para ver si el formulario hace lo que estamos esperando que haga, necesitamos comprobar varios casos:

*   No se envía el formulario
*   No escribimos nada en el input y enviamos el formulario a través del botón (_submit_)
*   (Con el foco en el input) no escribimos nada en el formulario y le damos a la tecla _Enter_ del teclado
*   ![input-required](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/12/input-required.png)Se envía el formulario
*   Escribimos algo en el input y le damos a la tecla _Enter_ del teclado
*   Escribimos un texto en el input y le damos a enviar
*   ![warning-router](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/12/warn-router.png)

¡Bravo!

El formulario está funcionando como es debido, pero tenemos un pequeño problema (de fácil solución). No tenemos la ruta `Profile` definida, por lo tanto Vue no sabe qué hacer en este caso.

Lo arreglaremos en las siguientes lecturas.


## 14. Vue Router

Hasta ahora teníamos 2 rutas en nuestra app, la ruta de `Home` y la de `About`.

Vamos a crear el resto de rutas (_like a pro_) que nos van a hacer falta para nuestra app de Diablo III. Las rutas que necesitaremos son las siguientes:

*   **Profile**: muestra los datos generales del usuario (BattleTag) en una región determinada.
*   **Hero**: muestra los datos específicos de un héroe (HeroId) de un usuario (BattleTag) en una región determinada.
*   **Error**: en caso de error, redireccionamos y mostramos el mensaje que nos devuelva la API.

La ruta de `Hero` es la más divertida. A través de las APIs del juego de Diablo III, traeremos los stats del héroe, los objetos (¡con imágenes!) y sus habilidades. Hay muchos más datos que nos proporcionan las APIs del juego, pero que no vamos a usar por no expandirnos mucho con el curso.

> Si te gusta este tema, siempre puedes animarte a mejorar el [proyecto original](https://github.com/baumannzone/diablo3-vue-platzi) con alguna _feature_ que creas que pueda estar bien 😉.

Antes de tocar las rutas, vamos a crear los componentes vista vacíos para poder trabajar luego con el fichero de rutas. Tenemos que crear las siguientes carpetas dentro de `/views`:

*   `/Profile`
*   `/Hero`
*   `/Error`

Ahora hay que crear, dentro de cada una, un nuevo fichero llamado `Index.vue`. Dicho componente va a ser el que renderice nuestra vista, y de momento le vamos a dar un contenido muy simple. Hasta ahora deberías tener esto dentro de `/views`, aparte de lo que ya tenías:

```markdown
📂 /views 
├──📂 /Profile
│   └── Index.vue
├──📂 /Hero
│   └── Index.vue
└──📂 /Error
    └── Index.vue
```

Vamos a dotar de contenido a nuestros recién creados archivos, para diferenciar nuestras vistas. Con un `h1` nos vale:

*   `/Profile/Index.vue`

```javascript
<template>
  <div>
    <h1>Profile View</h1>
  </div>
</template>

<script>
export default {
  name: 'ProfileView'
}
</script>
```

*   `/Hero/Index.vue`

```javascript
<template>
  <div>
    <h1>Hero View</h1>
  </div>
</template>

<script>
export default {
  name: 'HeroView'
}
</script>
```

*   `/Error/Index.vue`

```javascript
<template>
  <div>
    <h1>Error View</h1>
  </div>
</template>

<script>
export default {
  name: 'ErrorView'
}
</script>
```

Ahora ya podemos trabajar con nuestras rutas.

Tenemos que pensar, antes de empezar a picar código, qué es lo que necesitamos para poder trabajar con nuestras rutas. Tenemos varios escenarios:

*   Ruta _Home_, _About_ y _Error_: No necesitan parámetros en la URL. Renderizan contenido estático. En el caso de la pág. de error, dinámico, pero no require de parámetros en la URL.
*   Ruta _Profile_: Necesitamos la región del usuario y el identificador del usuario en la URL.
*   Ruta _Hero_: Necesitamos lo mismo que en _Profile_ más el identificador de héroe en la URL.

Ya tenemos identificados los posibles escenarios que podemos tener en nuestras rutas. Vamos a editar en nuestro fichero principal de rutas, es decir, `/router/index.js`, para ir creando lo que nos hace falta.

En el fichero hay que borrar algunas cosas y crear otras que vamos a ir comentando aquí abajo:

```javascript
// Importamos vue y vue-router
import Vue from 'vue'
import VueRouter from 'vue-router'
```

Esto se queda tal cual, necesitamos _Vue_ y _Vue-Router_.

Borramos los _import_ de los componentes vista que teníamos.

En esta ocasión, solo teníamos la vista _Home_. La vamos a borrar (ahora verás el porqué) junto con la variable `routes`.

Vamos a crear una nueva variable llamada `routerOptions` que va a ser un array de rutas con las opciones. Tiene el siguiente contenido:

```javascript
// ...
const routerOptions = \[
  { path: '/', name: 'Home' },
  { path: '/region/:region/profile/:battleTag', name: 'Profile' },
  { path: '/region/:region/profile/:battleTag/hero/:heroId', name: 'Hero' },
  { path: '/about', name: 'About' },
  { path: '/error', name: 'Error' },
  { path: '\*', redirect: { name: 'Home' } }
\]
```

Ya hemos nombrado nuestras rutas, tal y como habíamos definido antes, y les hemos dado un **path**. Como ya sabes, los dos puntos (`:`) en el `path` hacen referencia a un parámetro o variable en la ruta.

El path, en el caso de las rutas _Profile_ y _Hero_, es a gusto del consumidor.

Existen múltiples opciones a la hora de afrontar este problema, esta es solo una de ellas. Puedes cambiar si crees que hay otra solución mejor.

Por ejemplo, puedes optar por omitir `/region` del path de tu ruta, y dejarlo de esta forma: `/:region/profile/:battleTag`. O incluso, omitir `/profile` y dejar solo los parámetros: `/:region/:battleTag`.

> 📗 Puedes leer más acerca de vue-router en este link: [https://router.vuejs.org/guide/essentials/dynamic-matching.html](https://router.vuejs.org/guide/essentials/dynamic-matching.html)

Necesitamos saber la región, el identificador del usuario (que lo hemos llamado BattleTag) y el identificador del héroe. Ya lo tenemos definido en la ruta y podemos controlarlo desde nuestras vistas.

Ahora vamos a crear otra variable llamada `routes`, que va a ser el resultado de recorrer `routerOptions` con un `.map()`, junto con la propiedad `component` que vamos a adjuntarle. Con el código lo entenderás mejor.

```javascript
const routes = routerOptions.map(r => {
  return {
    ...r,
    component: () => import(\`@/views/${r.name}/Index.vue\`)
  }
})
```

Expliquemos esto. La variable `routes` es un array de objetos, que va a tener el mismo número de elementos que `routerOptions`. El contenido de dichos elementos va a ser un objeto primitivo que va a tener `path`, `name` y `component`:

*   `...r`: es decir, lo que tenía el propio elemento `routerOptions`.
*   `component`: que en vez de hacer referencia al componente, vamos a cargar el componente de manera lazy load usando los [import dinámicos de Webpack](https://router.vuejs.org/guide/advanced/lazy-loading.html).
*   Esto quiere decir que dividiremos nuestro código en pequeñas partes, y solo se cargará la parte correspondiente a la ruta que estemos visitando.

> Al crear aplicaciones con Vue, puede darse el caso de que nuestro código JavaScript sea bastante grande y, por lo tanto, que afecte al tiempo de carga de la página.

> Sería más eficiente dividir los componentes de cada ruta en un fragmento separado, y solo cargarlos cuando se visita la ruta.

Esto es lo que en inglés se conoce como _Lazy Load_. Justo lo que estamos haciendo aquí.

Y además de una manera elegante usando la función `map()`, ya que tenemos todas nuestras vistas cargadas bajo el mismo patrón: el `name` de `routerOptions` es el mismo que tenemos para agrupar las vistas por directorios, es decir, la ruta de nombre `Profile` tiene asignado el componente `/views/Profile/Index.vue`. Lo mismo para el resto de rutas.

Lo último sería instanciar el _Router_ de Vue.

```javascript
const router = new Router({
  routes
})
```

El código completo se vería así:

```javascript
import Vue from 'vue'
import Router from 'vue-router'

Vue.use(Router)

// Configuración rutas
const routerOptions = \[
  { path: '/', name: 'Home' },
  { path: '/region/:region/profile/:battleTag', name: 'Profile' },
  { path: '/region/:region/profile/:battleTag/hero/:heroId', name: 'Hero' },
  { path: '/about', name: 'About' },
  { path: '/error', name: 'Error' },
  { path: '\*', redirect: { name: 'Home' } }
\]

// Rutas
const routes = routerOptions.map(r => {
  return {
    ...r,
    // Lazy load
    component: () => import(\`@/views/${r.name}/Index.vue\`)
  }
})

const router = new Router({
  routes
})

export default router
```

En `component`, en vez de referenciar el componente vista que queremos cargar, estamos llamando a una función que es la que se va a encargar de traer el componente cuando sea necesario. Con esto estamos mejorando el rendimiento de nuestra web app.

Vamos a ver en acción el posible impacto en el rendimiento de nuestra app. Para probarlo podemos hacer uso del comando `npm run build`. Esto nos permite ver los _chunks_ (o fragmentos) que se generan de nuestra app. A medida que la aplicación vaya creciendo, estos fragmentos irán siendo más grandes. Hagamos la prueba.

Desde la terminal, en la carpeta raíz del proyecto, ejecuta el siguiente comando: `npm run build`. Una vez que haya terminado verás algo parecido a esto:

![terminal-chunks](https://github.com/baumannzone/d3pf-images/blob/master/13/chunks.png?raw=true)

Los _chunks_ son los fragmentos que el _build_ ha creado en vez de hacer un sólo paquete con todo el proyecto.

Por lo cual, en el momento de la carga de la app, se irán cargando los bloques que se vayan necesitando en vez de cargar todo el paquete completo.

Wow! Esto está bastante bien, pero… ¿Cómo saber a qué parte de la aplicación corresponde cada _chunk_? Webpack nos da un método para saberlo.

En la función donde hacemos el import, podemos poner un comentario JavaScript `/* Comentario JS */` indicándole el nombre que queremos que tenga ese chunk. Veámoslo en marcha:

```javascript
// router.js - Ejemplo simplificado

import Vue from 'vue'
import Router from 'vue-router'

Vue.use(Router)

const routes = [
  {
    path: '/',
    name: 'Home',
    component: () => import(/\* webpackChunkName: "Home" \*/ '@/views/Home/Index.vue')
  },
  {
    path: '/about',
    name: 'About',
    component: () => import(/\* webpackChunkName: "About" \*/ '@/views/About/Index.vue')
  },
  {
    path: '/error',
    name: 'Error',
    component: () => import(/\* webpackChunkName: "Error" \*/ '@/views/Error/Index.vue')
  }
\]

const router = new Router({
  routes
})

export default router
```

![named-chunks](https://github.com/baumannzone/d3pf-images/blob/master/13/named-chunks.png?raw=true)

Si te fijas, ahora los _chunks_ tienen un nombre aparte del hash. Tenemos los vendors (de librerías externas) de JS y CSS, el fichero app y el resto, que son los _chunks_ nombrados. Muy útil a la hora de desarrollar, para tener controlado el tamaño de nuestros fragmentos.

Una cosa más; esto también lo podemos ver desde las _DevTools_ del navegador, en la pestaña `network`. Para esto tienes que tener el servidor de desarrollo levantado, es decir, tienes que ejecutar `npm run serve` (o si usas yarn, `yarn serve`):

![home-chunks](https://github.com/baumannzone/d3pf-images/blob/master/13/home-chunk.png?raw=true)

Estamos en la vista _Home_, y aunque se han cargado las referencias de los tres _chunks_, realmente solo hemos cargado los datos de la vista _Home_. Si cambiamos de ruta y nos vamos a _Error_ ([http://localhost:8080/#/error](http://localhost:8080/#/error)) veremos lo siguiente:

![error-chunks](https://github.com/baumannzone/d3pf-images/blob/master/13/error-chunk.png?raw=true)

Se ha cargado el fichero `Error.js`, el archivo tiene ese nombre porque se lo hemos indicado nosotros, tú puedes poner lo que quieras.

![about-chunks](https://github.com/baumannzone/d3pf-images/blob/master/13/about-chunk.png?raw=true)

Si cambiamos de ruta a [http://localhost:8080/#/about](http://localhost:8080/#/about), verás que ahora ha cargado el último fragmento.

Esto nos permite repartir el peso de la app en múltiples trozos, en vez de tener uno extremadamente grande.

Lo malo de tener un solo _chunk_ es que probablemente no llegas a utilizar todo, y, sin embargo, estás consumiendo recursos para que la app lo cargue todo de golpe.

Quédate con este concepto de _Lazy Loading_ en rutas, pues más adelante lo veremos también en componentes.

Vamos a dejar el router.js como estaba antes de que le agregáramos los comentarios de _webpackChunkName_:

```javascript
import Vue from 'vue'
import Router from 'vue-router'

Vue.use(Router)

const routerOptions = \[
  { path: '/', name: 'Home' },
  { path: '/region/:region/profile/:battleTag', name: 'Profile' },
  { path: '/region/:region/profile/:battleTag/hero/:heroId', name: 'Hero' },
  { path: '/about', name: 'About' },
  { path: '/error', name: 'Error' },
  { path: '\*', redirect: { name: 'Home' } }
\]

// Rutas
const routes = routerOptions.map(r => {
  return {
    ...r,
    // Lazy load
    component: () => import(\`@/views/${r.name}/Index.vue\`)
  }
})

const router = new Router({
  routes
})

export default router
```

![unnamed chunks](https://github.com/baumannzone/d3pf-images/blob/master/13/unnamed-chunks.png?raw=true)

Mira cómo se ve en la pestaña _network_ del navegador cuando no tienes los _chunks_ nombrados. Es más difícil identificarlos.

Ahora ya sabes cómo hacer lazy loading de rutas en tus proyectos Vue. Ya podemos pasar a la siguiente lectura.


## 15. Vista Profile

En esta vista vamos a trabajar con muchos componentes que a su vez tienen más componentes hijos.

Tenemos los componentes divididos en 2 grandes bloques:

*   Bloque Principal (_MainBlock_), que a su vez contiene:
*   **Top Héroes**: los tres últimos héroes del juego con los que el usuario ha jugado
*   **Listado de héroes**: listado restante de héroes.
*   **Progreso de actos**: si hemos completado la historia o campaña del juego.
*   **Estadísticas generales**: élites, nivel de leyenda, etc.
*   **Tiempo de jugado**: porcentaje de tiempo jugado por héroe.
*   Bloque Artesanos (_ArtisansBlock_): información de los artesanos.

En la mayoría de los casos no nos detendremos a comentar los componentes que vayamos creando, puesto que son bastante sencillos.

Reciben unas _props_ (que serán los datos de la API) y los pintaremos en pantalla. Habrán algunos casos específicos que sí comentaremos.

Si retomamos una de las lecturas anteriores, nos habíamos quedado en que al hacer el _submit_ del formulario en la página principal, no nos hacía el cambio de ruta porque dicha ruta no existía. Ahora la ruta ya existe y si haces el envío del formulario, debería llevarte a la vista de _Profile_:

![profile](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/14/profile.png)

Los pasos a seguir son los siguientes:

*   Recuperar los datos a través de la ruta (URL): región y _battleTag_.
*   Llamar a la API oficial de Diablo III para que nos devuelva los datos del jugador de esa región
*   Si hay error, redirigir a la página de error y mostrar el mensaje de error
*   Si no hay error, mostrar los datos a través de los componentes que vamos a ir creando

Parámetros de Ruta
------------------

Si recuerdas, a nuestra ruta _Profile_ la definimos de la siguiente forma:

```javascript
{ path: '/region/:region/profile/:battleTag', name: 'Profile' },
```

En las _Vue DevTools_ del navegador, hay una pestaña en la cual podemos ver la información de todas las rutas.

![vdt-routing-2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/14/vdt-routing-2.png)

![vdt-routing-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/14/vdt-routing-1.png)

¿No te parece genial? Ahora, para ver los datos de la ruta (_route object_), no vas a tener que estar haciendo inspecciones usando `console.log` en los componentes. Utilizando las _Developer Tools_ te será mucho más cómodo inspeccionar las rutas y ver su configuración.

> 📗 Documentación oficial del objeto enrutador (_route object_), con el que vamos a trabajar ahora: [https://router.vuejs.org/api/#the-route-object](https://router.vuejs.org/api/#the-route-object)

En la segunda imagen, en el bloque de la derecha, vemos dicho _route object_, con los siguientes valores:

```javascript
path: "/region/eu/profile/SuperRambo-2613"
fullPath: "/region/eu/profile/SuperRambo-2613"
params: Object
  battleTag: "SuperRambo-2613"
  region: "eu"
name: "Profile"
matched: Array\[1\]
  0: Object
    path: "/region/:region/profile/:battleTag"
```

Nos vamos a fijar en el bloque `params`, ahí es donde están definidos los parámetros que nos interesan de nuestra ruta.

Como bien dice la documentación, desde un componente cualquiera podemos acceder a este objeto de ruta a través de `this.$route`.

El siguiente paso es hacer la llamada a la API del juego correspondiente pasándole los parámetros que acabamos de capturar del path de la ruta.

Para ello, en el _hook_ `created` de nuestro componente, vamos a crear una función que se encargue de llamar a la API y que nos devuelva una promesa, que en caso de éxito nos devuelva los datos correspondientes y en caso de error nos devuelva un mensaje, y, si es posible, el código de error.

El _endpoint_ al que vamos a apuntar desde nuestra web para que nos devuelva los datos, lo encontramos aquí ([https://develop.battle.net/documentation/diablo-3/community-apis](https://develop.battle.net/documentation/diablo-3/community-apis)) en el bloque de **D3 Profile API** / **getApiAccount**:

![endpoint](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/14/endpoint.png)

```javascript
// views/Profile/Index.vue

export default {
  name: 'ProfileView',
  created () {
    // this.$route.params -> { region: "eu", battleTag: "SuperRambo-2613" }this.fetchData()
  },
  methods: {
    fetchData () {
      // Llamada API
    }
  }
}
```

Para hacer la llamada a la API vamos a necesitar varias cosas:

*   El token de acceso, que lo tenemos guardado en el _Store_ de nuestra app.
*   El **BattleTag** del usuario.
*   La **región** en la cual se encuentra dicho usuario.
*   El **_locale_** o lenguaje en el que queremos que nos devuelva los datos. Esto lo dejaremos fijo, es decir, cada región tendrá asociado un _locale_ por defecto, a través de una funcionalidad (muy sencilla) que explicaremos más abajo.

La llamada a la API de Blizzard la vamos a hacer desde el fichero llamado `search.js`, que hemos creado anteriormente dentro de `/api`. Tendrá el siguiente contenido:

```javascript
// /api/search.js

// Axios para hacer la llamada HTTP
import { get } from 'axios'
// Store, donde tenemos almacenado nuestro token
import store from '../store/index'
// Útil de regiones, que nos devolverá el 'locale' por defecto correspondiente a cada región
import { locales } from '../utils/regions'

// API URL
// https://{region}.api.blizzard.com, donde {region} puede ser 'us', 'eu', 'kr' o 'tw'
const protocol = 'https://'
const host = '.api.blizzard.com/'
```

> 📗 Puedes ver la lista de _locales_ disponibles en este enlace ([https://develop.battle.net/documentation/guides/regionality-and-apis](https://develop.battle.net/documentation/guides/regionality-and-apis)), en el apartado de **Region Host List**.

Continuamos, ahora sí, con el proceso de creación de nuestra función encargada de llamar a la API. La llamaremos `getApiAccount`, al igual que se la llama en la documentación para que haya correspondencia entre nuestras funciones y la documentación de la API.

```javascript
// /api/search.js

/\*\*
 \* Returns the specified account profile.
 \* GET – /d3/profile/{account}
 \* Los parámetros que hemos obtenido a través de la URL
 \*  - @param region {String}
 \*  - @param account {String}
 \* @returns {Promise}
 \*/
function getApiAccount ({ region, account }) {
  // Recurso de la API al que queremos accederconst resource = \`d3/profile/${account}/\`// API URL completaconst API_URL = \`${protocol}${region}${host}${resource}\`// Localeconst locale = locales\[region\]

  // Parámetros:// - Token de acceso (recuperado desde Vuex)// - Localeconst params = {
    access_token: store.state.oauth.accessToken,
    locale
  }

  // Retornamos el resultado de hacer la llamada a la API, es decir, una promesa// que controlaremos (éxito / error) desde el componentereturn get(API_URL, { params })
}
```

Lo último que tenemos que hacer para poder usar esta funcionalidad desde nuestro componente Vue, es exponerla para que pueda ser importada desde fuera. Esto lo hacemos de la siguiente forma:

```javascript
export {
  getApiAccount
}

El código completo de `/api/search.js` se vería así:

import { get } from 'axios'
import store from '../store/index'
import { locales } from '../utils/regions'

// https://{region}.api.blizzard.com, where {region} is one of us | eu | kr | tw
const protocol = 'https://'
const host = '.api.blizzard.com/'

/\*\*
 \* Returns the specified account profile.
 \* GET – /d3/profile/{account}
 \* @param region {String}
 \* @param account {String}
 \* @returns {Promise}
 \*/
function getApiAccount ({ region, account }) {
  const resource = \`d3/profile/${account}/\`const API_URL = \`${protocol}${region}${host}${resource}\`const locale = locales\[region\]

  const params = {
    access_token: store.state.oauth.accessToken,
    locale
  }

  return get(API_URL, { params })
}

export {
  getApiAccount
}
```

Con esto creado, ya podemos hacer la llamada a la API desde nuestro componente y controlar si sale por error o por éxito.

Volvemos al componente principal de _Profile_ en `/views/Profile/Index.vue` y desde nuestro método `fetchData` llamamos a esta función. Recuerda que, para usarla, tienes que importarla primero.

```javascript
// /Profile/Index.vue

import { getApiAccount } from '@/api/search'

export default {
  name: 'ProfileView',
  created () {
    this.fetchData()
  },
  methods: {
    fetchData () {
      // Desestructuración
			const { region, battleTag: account } = this.$route.params
      // Llamada a la API con los datos necesarios
      getApiAccount({ region, account })
        .then()
        .catch()
    }
  }
}
```

La llamada a `getApiAccount` , que recibe como parámetro un objeto con `region` y `account` como claves, nos va a devolver una promesa que puede terminar exitosamente (_then_) o con error (_catch_):

*   **Éxito**: guardamos los datos en una variable local al componente. Con esto ya podemos propagar los datos (_props_) por los componentes hijos que vayamos creando.
*   **Error**: guardar respuesta de error en el _Store_, cambiar de ruta a vista de _Error_ y recuperar los datos.

Mixins
------

Lo que vamos a hacer, en caso de que nuestra llamada a la API nos devuelva un error, es guardar dicho error en el _Store_ y hacer un cambio de ruta a la página de _Error_.

Esta funcionalidad de guardar datos que se mostrarán en la pág. de error, la podemos usar cada vez que llamemos a una API y nos salte un error.

Por lo tanto, en vez de duplicar código a través de varios componentes, lo que vamos a hacer es crear un _mixin_ que contenga dicha funcionalidad. De esta forma, cuando queramos utilizar esta funcionalidad, estaremos reutilizando código en vez de duplicarlo.

> 📗 Documentación a mixins: [https://es.vuejs.org/v2/guide/mixins.html](https://es.vuejs.org/v2/guide/mixins.html)

Para crear nuestro mixin nos vamos a la carpeta `/mixins` de nuestro proyecto y creamos un nuevo fichero llamado, por ejemplo, `setError.js`.

Este fichero va a interactuar con el _Store_ de nuestra app, por lo que antes de continuar, necesitamos crear dicho código en el módulo Vuex correspondiente de nuestra aplicación.

Como vamos a establecer el objeto de error que nos devuelva la API, podemos crear el fichero con el nombre de `error.js`, dentro de nuestro directorio de Vuex: `/store/modules`. Deberías tener creado el fichero en esta ruta: `/store/modules/error.js`.

El contenido que va a tener es muy simple, una variable _error_ que por defecto sea `null` y una función (mutación) que se encargue de mutar el valor de _error_.

```javascript
// /store/modules/error.js

export default {
  namespaced: true,
  state: {
    error: null
  },
  mutations: {
    SET_ERROR (state, payload) {
      state.error = payload
    }
  }
}
```

Cuando tengamos un error, llamamos a `SET_ERROR` y le pasamos por parámetro el objeto. Cuando queramos limpiar el error, podemos pasarle `null` como parámetro.

Ahora queda darlo de alta en el _Store_ de nuestra app, y para ello nos vamos una carpeta atrás `/store`, al fichero `index.js` y le añadimos el módulo que acabamos de crear.

```diff
  import Vue from 'vue'
  import Vuex from 'vuex'

  import oauth from './modules/oauth'
  import loading from './modules/loading'
+ import error from './modules/error'

  Vue.use(Vuex)

  export default new Vuex.Store({
    modules: {
      oauth,
      loading,
+     error
    }
  })
```

Con esto, como ya sabes, lo tenemos disponible desde cualquier parte de nuestra app. Volvamos a retomar el tema de los _mixins_, en concreto nuestro archivo `setError.js`.

Creo que el nombre del fichero te da una pista de que es lo que tenemos que hacer, ¿no?

```javascript
// /mixins/setError.js

import { mapMutations } from 'vuex'

export default {
  methods: {
    ...mapMutations('error', {
      setError: 'SET_ERROR'
    }),
    /\*\*
     \* API response error.
     \* @param params {Object || null} Error Object
     \*/
    setApiErr (params) {
      this.setError(params)
    }
  }
}
```

Para trabajar con las mutaciones de nuestro _Store_ en nuestros componentes, _Vuex_ nos ofrece un elegante método que nos permite mapear el nombre de nuestra mutación (del _Store_) con una función en nuestro componente.

> 📗 Documentación completa de [mapMutations](https://vuex.vuejs.org/guide/mutations.html#committing-mutations-in-components).

Para hacer uso de este método, lo primero que tenemos que hacer es importarlo desde _Vuex_.

Su uso es muy sencillo. En este ejemplo, `mapMutations` recibe 2 argumentos:

*   El primer argumento es el _bloque_ al que hacemos referencia, en este caso, lleva por nombre `error`.
*   El segundo argumento es un objeto con las funciones que queremos mapear, es decir, le hemos dicho que nuestra mutación `SET_ERROR`, se convierta en un método de nombre `setError` en nuestro componente.
*   De esta forma podemos usarlo como un componente local con la sintaxis de siempre `this.setError()`.

Lo que hemos hecho es crear un _mixin_, es decir, código que puede ser reutilizado. Dentro de este código (que va a formar parte de un componente) estamos exponiendo un método (_methods_) que se llama `setApiErr`, que recibe un argumento por parámetro.

Lo único que hace este método es llamar a nuestra función mapeada de _Vuex_, que en realidad es como si estuviéramos llamando la mutación del _Store_ `SET_ERROR`.

Es decir, desde un componente (en el cual tengamos importado el mixin) podemos llamar al método `setApiErr()`, como si fuera un método local más de nuestro componente.

Ya tenemos implementado un mixin que se comunica con el _Store_ de nuestra aplicación. Solo nos queda usarlo.

  

Ahora ya tenemos nuestra funcionalidad _Vuex_ y nuestro _mixin_ listo para usarse. Es hora de volver a nuestra vista _Profile_ y retomar la llamada a la API. Nos quedaría algo así:

```javascript
// /views/Profile/Index.vue

// Traemos el mixin
import setError from '@/mixins/setError'
import { getApiAccount } from '@/api/search'

export default {
  name: 'ProfileView',
  // Lo damos de alta
  mixins: \[
    setError
  \],
  data () {
    return {
      profileData: null
    }
  },
  created () {
    // llamada a la APIthis.fetchData()
  },
  methods: {
    fetchData () {
      const { region, battleTag: account } = this.$route.params
      getApiAccount({ region, account })
        .then(({ data }) => {
        	// Guardamos los datos en una variable localthis.profileData = data
        })
        .catch((err) => {
          this.profileData = null
        	// Creamos el objeto errorconst errObj = {
            routeParams: this.$route.params,
            message: err.message
          }
          if (err.response) {
            errObj.data = err.response.data
            errObj.status = err.response.status
          }
        	// Hacemos uso del Mixin
	        // Guardamos el objeto en el Storethis.setApiErr(errObj)
	        // Navegamos a la ruta de nombre 'Error'this.$router.push({ name: 'Error' })
        })
    }
  }
}
```

Si hacemos la prueba con el usuario `SuperRambo#2613` y con la región `EU`, hacemos el envío del formulario y vamos al navegador, deberíamos ver algo como esto:

![api-request](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/14/api-request.png)

![vue-data](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/14/vue-data.png)

Ya tenemos todo lo necesario para pintar nuestra pantalla de _Profile_. Vamos a ir creando los componentes necesarios y les iremos pasando la información necesaria en forma de _props_.

![wireframe](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/14/wireframe.png)Según esta imagen, vamos a dividir el contenido en 2 grandes bloques, en base a la maquetación que vamos a hacer. El bloque de artesanos va a ser un bloque (_ArtisansBlock_) y el resto de componentes va a ser otro bloque (_MainBlock_).

Dentro del bloque principal (_MainBlock_) vamos a posicionar nuestro contenido con _CSS Grid Layout_ y con las clases de que nos proporciona Bootstrap.

> 📗 CSS Grid está fuera del alcance de este curso, pero como buen front-end developer deberías tener conocimientos para saber cómo funciona y poder entenderlo.

> Si no conoces _Grid_, esta guía te puede ser de ayuda: [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)

Al navegar a la ruta _Profile_ estamos haciendo una llamada a una API. Sería lógico mostrar un mensaje de ‘Loading’ mientras obtenemos los datos.

Seguramente recuerdes que tenemos un componente _Loading_ que nos encaja a la perfección en este momento. Vamos a traerlo y a usarlo.

Lo primero que tenemos que hacer es importarlo desde `/components`. Lo segundo es darlo de alta dentro del bloque `components` de nuestro componente vista _Profile_. Por último, solo nos queda usarlo.

```javascript
import BaseLoading from '@/components/BaseLoading'
```
```javascript
components: { BaseLoading }
```
```javascript
<BaseLoading/>
```

Para controlar el componente _BaseLoading_ vamos a crear una nueva variable llamada `isLoading` dentro de nuestras variables. En el _hook_ `created` vamos a igualar esta variable a `true` y cuando la llamada a la API termine, la igualaremos a `false`.

Veamos como queda el código completo hasta ahora.

```javascript
<template>
  <div>
    <BaseLoading v-if="isLoading"/>
    <h1>Profile View</h1>
  </div>
</template>

<script>
import BaseLoading from '@/components/BaseLoading'
import setError from '@/mixins/setError'
import { getApiAccount } from '@/api/search'

export default {
  name: 'ProfileView',
  mixins: \[
    setError
  \],
  components: { BaseLoading },
  data () {
    return {
      isLoading: false,
      profileData: null
    }
  },
  created () {
    this.isLoading = trueconst { region, battleTag: account } = this.$route.params
    this.fetchData(region, account)
  },
  methods: {
    /\*\*
     \* Obtener los datos de la API
     \* Guardarlos en 'profileData'
     \*/
    fetchData (region, account) {
      getApiAccount({ region, account })
        .then(({ data }) => {
          this.profileData = data
        })
        .catch((err) => {
          this.profileData = nullconst errObj = {
            routeParams: this.$route.params,
            message: err.message
          }
          if (err.response) {
            errObj.data = err.response.data
            errObj.status = err.response.status
          }
          this.setApiErr(errObj)
          this.$router.push({ name: 'Error' })
        })
        .finally(() => {
          this.isLoading = false
        })
    }
  }
}
</script>
```

Ya tenemos el _loading_ funcionando. Es hora de crear los componentes que muestren por pantalla datos reales de la API. ¡Lo veremos en la siguiente lectura!


## 16. ¡Más Componentes!

Como anunciamos en la lección anterior, ya tenemos todo el material para crear nuestros componentes.

MainBlock
---------

El primer componente que vamos a crear se llama `MainBlock` y como va a ser un componente que a su vez va a tener muchos componentes hijos, vamos a crear una carpeta y dentro el componente (`Index.vue`, como siempre).

Creamos el componente en `/views/Profile/MainBlock/Index.vue`. La prop que le vamos a pasar la llamaremos `profileData` y será de tipo objeto y requerido.

Con esto en mente, el contenido debería ser el siguiente:

```javascript
<template><div><h1>Main Block</h1></div>
</template>

<script>
export default {
  name: 'MainBlock',
  props: {
    profileData: {
      type: Object,
      required: true
    }
  }
}
</script>

<style lang="stylus">
</style>
```

Ahora desde el componente padre (es decir `/views/Profile/Index.vue`) podemos pasarle los datos como _props_.

En este caso le vamos a pasar el valor de `profileData`, que es dónde acabamos de guardar la información traída de la API.

Como siempre los pasos serán:

*   Importar componente
*   Dar de alta
*   Usar el componente

```javascript
import MainBlock from './MainBlock/Index'
...
components: { BaseLoading, MainBlock },
...
<MainBlock :profile-data="profileData"/>
```

> 📗 Puedes leer más acerca de las _props_ de Vue desde aquí: [https://vuejs.org/v2/guide/components-props.html](https://vuejs.org/v2/guide/components-props.html)

En el componente `MainBlock` hemos definido una propiedad llamada `profileData`. Desde el padre se puede usar de 2 formas:

*   `:profile-data="profileData"`
*   `:profileData="profileData"`

Elije la forma que más te guste e intenta no mezclar ambos estilos, para mantener la consistencia a lo largo del proyecto. En este caso, usaremos la primera:

```javascript
<MainBlock :profile-data="profileData"/>
```

Comprobemos que funciona y que el hijo tiene los datos correspondientes. Vamos al navegador, y, si abrimos la consola, vemos que tenemos un error. Seguramente te pase a menudo y vamos a ver como solucionarlo. El error es el siguiente:

![error-if](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/error-if.png)

> Invalid prop: type check failed for prop “profileData”. Expected Object, got Null

Esto ocurre porque nuestro componente tiene definida la propiedad (_profileData_) que espera un valor de tipo objeto y le está llegando un `null`. Nos está avisando.

Para resolverlo lo que vamos a hacer es indicarle a nuestro componente que se renderice cuando tenga los datos de la API, de esta forma no deberíamos ver el error en consola.

El HTML completo del componente Profile (`/views/Profile/Index.vue`) se vería así:

<template><div><BaseLoading v-if="isLoading"/><template v-if="profileData !== null"><MainBlock :profile-data="profileData"/></template></div>
</template>

En Vue, podemos usar la etiqueta `<template></template>` para agrupar contenido dentro. La etiqueta _template_ no renderiza nada en el HTML, por lo que es perfecta para este caso, cuando no queremos añadir una capa (`div`) extra a nuestro código.

![main-block-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/main-block-1.png)

Ya tenemos los datos cargados en nuestro componente hijo y no tenemos ningún error en consola.

MainBlock: Componentes Hijos y CSS
----------------------------------

Dentro de este componente, como ya vimos en una imagen anteriormente, vamos a crear varios componentes que van a convivir en un _Grid_ de CSS que vamos a crear ahora mismo.

Nuestro grid se divide en 2 bloques principales: bloque izquierdo y bloque derecho.

*   En el izquierdo vamos a tener un listado de héroes, los últimos héroes jugados y el progreso en la historia del juego.
*   En el derecho mostraremos algunas de las estadísticas del jugador como: número de bichos normales y jefes asesinados, tiempo de juego por personaje, etc.

Empecemos con el CSS:

```stylus
  .grid-containerdisplay grid
    grid-template-columns 1fr

    .grid-item
      &.item-left
        grid-column span 1

      &.item-right
        grid-column span 1

  @media (min-width: 992px)
    .grid-containerdisplay grid
      grid-template-columns repeat(6, 1fr)

      .grid-item
        &.item-left
          grid-column span 4

        &.item-right
          grid-column span 2
```

Lo que me gusta de _Stylus_ es que el código te queda muy limpio, sin puntos o llaves, solo trabajando con la tabulación.

A modo resumen, lo que estamos haciendo es crear una vista para pantallas pequeñas (hasta 992px) con una sola columna, donde el contenido de la ‘izquierda’ se verá primero y debajo el del bloque de la ‘derecha’.

A partir de `992px` tendremos 6 columnas, de las cuales 4 irán para el bloque de la izquierda y 2 para el bloque de la derecha.

> 📗 Si te interesa el tema de CSS Grid, te recomiendo que uses el navegador de Firefox para desarrolladores ([https://www.mozilla.org/es-ES/firefox/developer/](https://www.mozilla.org/es-ES/firefox/developer/)) que tiene muy buenas herramientas para trabajar con CSS Grid. Además tienen una guía muy chula de [CSS Grid](https://mozilladevelopers.github.io/playground/css-grid/).

> ![firefox-dev](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/firefox-dev.png)

El HTML de nuestro Grid quedaría así:

<template><div class="grid-container"><div class="grid-item item-left"><h1>Izquierda</h1></div><div class="grid-item item-right"><h1>Derecha</h1></div></div>
</template>

Y deberías verlo de esta forma:

> ![grid-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/grid-1.png)

Empecemos con el primer componente del bloque de la derecha.

### Top Heroes

En este componente vamos a pintar los 3 primeros elementos (en caso de que haya alguno) que nos lleguen en el array de héroes de _profileData_.

Para ver el potencial de nuestro CSS global, vamos a crear unas clases de CSS globales para pintar la cara de nuestros posibles personajes.

Son 7 tipos de personajes (bárbaro, médico brujo, cazador de demonios, mago, monje, nigromante y cruzado) y hay 2 géneros (masculino y femenino), por lo tanto vamos a tener 14 imágenes distintas que procesar con CSS.

Para hacerlo más profesional, (porque esto es lo que somos, profesionales 😏), vamos a usar _Sprites CSS_.

Aunque no está dentro del scope del curso, vamos a explicar brevemente que es eso de los _Sprites_ CSS.

Un sprite de imagen es una colección de imágenes puestas en una sola imagen. Es bastante habitual usar esta técnica. Seguro que, si inspeccionas alguna web conocida, te des cuenta de que estan usando _sprites_ CSS en alguna parte de su sitio web.

> **Te propongo buscar ejemplos de sprites de sitios web**

Para nuestra app lo vamos a usar en varios casos, y este es uno de ellos.

Es decir, en vez de tener 14 imágenes con las caras de los héroes, vamos a tener una sola imagen con las 14 caras.

¿Qué ganamos con esto? Por un lado reducir el número de peticiones al servidor, por otro lado agrupar contenido.

Piensa en qué es lo que haces con el JavaScript y con el CSS cuando lo compilas o minimizas: lo sueles dejar en un solo archivo.

Esto es similar, pero con imágenes.

Vamos a cargar la imagen correspondiente a las caras de los personajes y despues vamos a jugar con la propiedad de `background-position` para ir mostrando el contenido que nos interesa.

La imagen que nos interesa está en: `/src/assets/img/heroes-faces.png`.

#### Sprites CSS

Volvamos al fichero de CSS global en `/src/assets/css/main.styl` y agreguemos, a lo que ya teníamos, el siguiente código:

```stylus
// ---------------------
// Sprite image · Heroes faces
// ---------------------

.hero-barbarian,
.hero-witch-doctor,
.hero-demon-hunter,
.hero-wizard,
.hero-monk,
.hero-necromancer,
.hero-crusaderbackground-image: url('../img/heroes-faces.png')
  background-size 203%width 136pxheight 106px

.hero-barbarian
  &.malebackground-position 0 0

  &.femalebackground-position 100% 0

.hero-witch-doctor
  &.malebackground-position 0 16.538462%

  &.femalebackground-position 100% 16.538462%

.hero-demon-hunter
  &.malebackground-position 0 33.247754%

  &.femalebackground-position 100% 33.247754%

.hero-wizard
  &.malebackground-position 0 50%

  &.femalebackground-position 100% 50%

.hero-monk
  &.malebackground-position 0 66.666667%

  &.femalebackground-position 100% 66.666667%

.hero-necromancer
  &.malebackground-position 0 83.333333%

  &.femalebackground-position 100% 83.333333%

.hero-crusader
  &.malebackground-position 0 100%

  &.femalebackground-position 100% 100%


// Small devices (landscape phones, 576px and up)
@media (min-width: 576px)
  .hero-barbarian,
  .hero-witch-doctor,
  .hero-demon-hunter,
  .hero-wizard,
  .hero-monk,
  .hero-necromancer,
  .hero-crusaderbackground-size 200%width 100%height 115px

// Medium devices (tablets, 768px and up)
@media (min-width: 768px)
  .hero-barbarian,
  .hero-witch-doctor,
  .hero-demon-hunter,
  .hero-wizard,
  .hero-monk,
  .hero-necromancer,
  .hero-crusaderheight 161px

// Large devices (desktops, 992px and up)
@media (min-width: 992px)
  .hero-barbarian,
  .hero-witch-doctor,
  .hero-demon-hunter,
  .hero-wizard,
  .hero-monk,
  .hero-necromancer,
  .hero-crusaderheight 143px

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px)
  .hero-barbarian,
  .hero-witch-doctor,
  .hero-demon-hunter,
  .hero-wizard,
  .hero-monk,
  .hero-necromancer,
  .hero-crusaderheight 174px
```

Aquí hemos definido unas clases CSS principales (`.hero-barbarian`, `.hero-witch-doctor`, `.hero-demon-hunter`, `.hero-wizard`, `.hero-monk`, `.hero-necromancer`, `.hero-crusader`)

para después poder agregarle modificadores (`.male` o `.female`).

Aparte, hemos añadido un par de _media queries_ para que las caras se vean bien en todos los tamaños de pantalla.

Vamos a crear un par de componentes más para pintar nuestros _Top Heroes_. Creamos un directorio llamado `/TopHeroes` y dentro creamos 2 nuevos componentes Vue:

`Index.vue` y `TopHero.vue`. Tal que así:

\# src/views/Profile/MainBlock/TopHeroes/Index.vue

```markdown
📂 /src 
└──📂 /views
    └──📂 /Profile
       └──📂 /MainBlock
            └──📂 /TopHeroes
               ├── Index.vue
               └── TopHero.vue
```

En `/TopHeroes`, `Index.vue` va a ser el listado de héroes y `TopHero.vue` un solo elemento de ese listado, es decir, un héroe a pintar, que se repetirá 3 veces.

### TopHero

En el componente `TopHero.vue`, de momento, vamos a tener este contenido:

<template><div><h1>TopHero</h1></div>
</template>

<script>
export default {
  name: 'TopHero',
  props: {
    hero: {
      type: Object,
      required: true
    }
  }
}
</script>

Al componente `TopHeroes`, que va a pintar el listado de tres héroes, le dotamos del contenido siguiente:

<template><div class="top-heroes"><h1>Top Heroes</h1></div>
</template>

<script>

export default {
  name: 'TopHeroes',
  props: {
    heroes: {
      required: true,
      type: Array
    }
  }
}
</script>

Hemos definido una propiedad obligatoria de tipo Array llamada `heroes`. Por lo tanto, desde el padre (_MainBlock_) deberemos filtrar y sacar los tres primeros elementos del array y pasársela bajo este nombre.

Actualizamos `/views/Profile/MainBlock/Index.vue`:

```javascript
// Importamos
import TopHeroes from './TopHeroes/Index'

export default {
  name: 'MainBlock',
  components: { TopHeroes },
  props: {
    profileData: {
      type: Object,
      required: true
    }
  },
  computed: {
    // Comprobamos que hay héroes
    hasHeroes () {
      return this.profileData.heroes.length > 0
    },
    // Devolvemos los 3 primeros
    topHeroes () {
      return this.profileData.heroes.slice(0, 3)
    }
  }
}
```

> 📗 Si no te queda claro que son las _computed properties_ o propiedades computadas, piensa en que son expresiones JavaScript.

> Por ejemplo `2 + 2` es una expresión. Esto lo puedes poner en un componente o puedes crear una _computed_ para no dejar la lógica en el HTML y llevarla al JavaScript.

> La documentación lo explica muy bien: [https://vuejs.org/v2/guide/computed.html](https://vuejs.org/v2/guide/computed.html)

*   Comprobamos que, en el array de héroes que nos llega del componente padre, haya elementos.
*   En caso de que haya elementos, nos quedamos con los tres primeros y se los pasamos al componente hijo para que los pinte.

```
<TopHeroes v-if="hasHeroes" :heroes="topHeroes"/>

Ahora tenemos que dotar de contenido a nuestro componente `TopHeroes`.

`/views/Profile/MainBlock/TopHeroes/Index.vue`

<template><div><h1>TopHeroes</h1><div>{{ heroes }}</div></div>
</template>

<script>
export default {
  name: 'TopHeroes',
  props: {
    heroes: {
      required: true,
      type: Array
    }
  }
}
</script>
```

Por ahora, nuestra app web se vería así:

![preview-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/preview-1.png)Y la estructura de carpetas debería ser esta:

![folders-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/folders-1.png)Y los componentes, de abajo hacia arriba, por el momento tienen este contenido:

*   `/views/Profile/MainBlock/TopHeroes/TopHero.vue`

```javascript
<template>
  <div>
    <h1>TopHero</h1>
  </div>
</template>

<script>
export default {
  name: 'TopHero',
  props: {
    hero: {
      type: Object,
      required: true
    }
  }
}
</script>
```

*   `/views/Profile/MainBlock/TopHeroes/Index.vue`

```javascript
<template>
  <div>
    <h1>TopHeroes</h1>
    <div>{{ heroes }}</div>
  </div>
</template>

<script>
export default {
  name: 'TopHeroes',
  props: {
    heroes: {
      required: true,
      type: Array
    }
  }
}
</script>
```

*   `/views/Profile/MainBlock/Index.vue`

```javascript
<template>
  <div class="grid-container">
    <div class="grid-item item-left">
      <TopHeroes v-if="hasHeroes" :heroes="topHeroes"/>
    </div>
    <div class="grid-item item-right">
      <h1>Derecha</h1>
    </div>
  </div>
</template>

<script>
import TopHeroes from './TopHeroes/Index'

export default {
  name: 'MainBlock',
  components: { TopHeroes },
  props: {
    profileData: {
      type: Object,
      required: true
    }
  },
  computed: {
    hasHeroes () {
      return this.profileData.heroes.length > 0
    },
    topHeroes () {
      return this.profileData.heroes.slice(0, 3)
    }
  }
}
</script>

<style lang="stylus">
  .grid-containerdisplay grid
    grid-template-columns 1fr

    .grid-item
      &.item-left
        grid-column span 1

      &.item-right
        grid-column span 1

  @media (min-width: 992px)
    .grid-containerdisplay grid
      grid-template-columns repeat(6, 1fr)

      .grid-item
        &.item-left
          grid-column span 4

        &.item-right
          grid-column span 2
</style>
```

Ya tenemos los tres héroes que necesitábamos en nuestro componente _TopHeroes_. Analicemos que datos le estamos pasando desde el padre:

![preview-2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/preview-2.png)El objeto que tenemos por cada uno de los tres héroes es similar a este. Vamos a estar utilizando principalmente el id, el nombre, el nivel, la clase y el género (donde `0` representa el personaje masculino y `1` al femenino).

```javascript
 {
    "id": 129570533,
    "name": "ElMicroYyo",
    "class": "crusader",
    "classSlug": "crusader",
    "gender": 0,
    "level": 70,
    "kills": { "elites": 3529 },
    "paragonLevel": 828,
    "hardcore": false,
    "seasonal": false,
    "dead": false,
    "last-updated": 1579274331
}
```

Ahora que tenemos claro qué es lo que podemos mostrar, vamos a iterar con la directiva `v-for` de Vue para recorrer el array de héroes y pintarlos por pantalla.

Vamos a traer y a dar de alta el componente hijo `TopHero.vue` y también vamos a hacer uso de algunas directivas (clases) de [bootstrap-vue](https://bootstrap-vue.js.org/docs/components/layout/#layout-and-grid-system).

La parte del HTML de `/TopHeroes/Index.vue`se vería así:

```html
<template>
  <div class="top-heroes">
    <!-- Título con nuestra fuente Diablo-like -->
    <h2 class="my-4 font-diablo">Top Heroes</h2>
    <!-- 3 columnas, una para cada TopHero -->
    <b-row>
      <!-- No te olvides de poner el key cuando uses v-for -->
      <b-col sm="4" v-for="hero in heroes" :key="hero.id">
        <!-- TopHero con datos como prop -->
        <TopHero :hero="hero"/>
      </b-col>
    </b-row>
  </div>
</template>
```

> 📗 ¿Por qué debes usar `key`?: [https://vuejs.org/v2/guide/list.html#Maintaining-State](https://vuejs.org/v2/guide/list.html#Maintaining-State)

El JavaScript de este componente se vería así de simple:

```javascript
import TopHero from './TopHero'

export default {
  name: 'TopHeroes',
  components: { TopHero },
  props: {
    heroes: {
      required: true,
      type: Array
    }
  }
}
```

Y nuestro árbol de componentes, en las _DevTools_ del navegador, se vería como esto:

![preview-3](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/preview-3.png)Ahora queda terminar de implementar nuestro componente `TopHero.vue` en el cual pintaremos la cara de nuestro personaje y el nombre.

Indicaremos también que si el personaje es de temporada será representado con una hoja verde, y si está en modo _Hardcore_, lo representaremos con un fondo rojo.

Este componente va a tener un poco de CSS bastante simple: el nombre y la capa circular que muestre el nivel.

Creamos el bloque `style` de nuestro componente `/TopHeroes/TopHero.vue` con el siguiente contenido:

```stylus
.hero-portrait-wrapper.title-namecolor white
    font-weight 900
    
  .level-circlewidth 26pxheight 26pxpadding 4pxfont-weight bold
    text-align center
    border-radius 13pxbackground-color #15202bbox-shadow 0 0 0 2px #6c757d
```

Para que tengas una idea, esto es lo que queremos conseguir:

![hero-season-hardcore.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/hero-season-hardcore.png)En esta imagen se ven los tres _Top Heroes_ de los cuales dos son de temporada (🍃) y uno de ellos es _Hardcore_ (en rojo).

> Los personajes hardcore son exactamente los mismos que los personajes normales, excepto que son mortales.

> Si no has jugado a Diablo III, cuando un personaje _Hardcore_ (HC) muere, ya no puedes volver a jugar con el: la muerte del personaje es definitiva.

Seguimos con nuestro componente, esta vez con el HTML. Copiamos el siguiente contenido:

```html
<template>
  <!-- Contenedor principal -->
  <div class="hero-portrait-wrapper mb-5 mb-sm-0">
    <!-- Avatar -->
    <div class="bg-secondary d-flex justify-content-center p-3 p-sm-0">
      <!-- Imagen de fondo, según la clase y el género -->
      <div :class="heroClass"></div>
    </div>
  <div class="p-2 bg-dark">
    <!-- Nombre héroe -->
    <!-- Si es hardcore, pintamos el fondo rojo -->
    <h5 class="text-truncate m-0 text-center title-name font-diablo" :class="{'bg-danger': hero.hardcore}">
      {{ hero.name }}
      <!-- Si es condicional, pintamos la hoja verde -->
      <img v-if="hero.seasonal" src="@/assets/img/leaf.png" width="12px" class="">
    </h5>
    <div class="d-flex justify-content-between border-top border-secondary pt-2 align-items-center mt-2">
      <small class="elite-kills">
        <!-- Jefes (Élites) asesinados -->
        <span class="text-monospace">
          {{ hero.kills.elites }}
        </span>
        Elite kills
      </small>
      <!-- Nivel. De color rojo si el héroe está muerto -->
      <small class="level-circle" :class="{'text-danger': hero.dead}">
        {{ hero.level }}
      </small>
    </div>
    </div>
  </div>
</template>
```

> 📗 La mayoría de clases que estamos usando en este componente (y a lo largo del proyecto) las puedes encontrar aquí: [https://getbootstrap.com/docs/4.4/utilities/spacing/](https://getbootstrap.com/docs/4.4/utilities/spacing/)

> Son un conjunto de utilidades. Por ejemplo `mb-0` significa `margin-bottom: 0`. Son clases CSS que tenemos disponibles gracias a Bootstrap.

Hasta aquí nada complicado. Como ya sabrás, todos los atributos de un elemento HTML (como el `id`, una `class`, el `src` de una imagen) pueden ser estáticos o dinámicos.

Para hacerlos dinámicos lo único que tenemos que hacer es poner `:` delante del atributo. Es decir, para tener un `id` dinámico sería así: `:id`. Para una clase de CSS sería `:class`.

Esto nos permite pasarle una expresión (por ejemplo, el resultado de sumar `30 + 2`), un método (`:id="getRandomValue()"` que tomará como valor el resultado retornado por dicha función)

o una _computed property_, que ya sabes lo que son, entre otros.

> 📗 Existen varias formas de trabajar con clases.

> Te dejo el enlace a la [documentación oficial](https://es.vuejs.org/v2/guide/class-and-style.html) que lo explica muy bien y de manera sencilla.

Excepto `<div :class="heroClass">
  </div>`, lo único que estamos haciendo en nuestro componente `TopHero.vue` es mostrar los datos que nos manda el padre (`hero.name`, `hero.level`, etc.).

Para mostrar en la web el rostro adecuado de nuestro personaje tenemos que asignarle la clase CSS correspondiente (recuerda que las clases CSS ya las creamos hace un rato).

Según lo que hemos definido en el CSS global, si queremos mostrar la cara del _Bárbaro hombre_ tendríamos que tener la siguiente clase CSS en nuestro `div`:`.hero-barbarian.male`. Es decir, se vería así:

`<div class="hero-barbarian male"></div>`.

Para controlar esto, vamos a crear una propiedad computada que nos diga qué clase es la que nos corresponde según el héroe que tengamos.

Necesitamos dos cosas para poder generar la clase CSS correcta:

*   El género (masculino o femenino)
*   Tipo de personaje (mago, cruzado, monje, etc.)

Podríamos crear algo como esto y añadirlo al componente:

```javascript
export default {
  computed: {
    heroClass () {
      const gender = this.hero.gender === 0 ? 'male' : 'female'return \`hero-${this.hero.classSlug} ${gender}\`
    }
  }
}
```

Este es el código del componente `TopHero.vue`, es decir, del componente `/views/Profile/MainBlock/TopHeroes/TopHero.vue`:

```javascript
<template>
  <div class="hero-portrait-wrapper mb-5 mb-sm-0">
    <div class="bg-secondary d-flex justify-content-center p-3 p-sm-0">
      <!-- Bg Img -->
      <div :class="heroClass"></div>
    </div>
    <div class="p-2 bg-dark">
      <h5 class="text-truncate m-0 text-center title-name font-diablo" :class="{'bg-danger': hero.hardcore}">
        {{ hero.name }}
        <img v-if="hero.seasonal" src="@/assets/img/leaf.png" width="12px">
      </h5>
      <div class="d-flex justify-content-between border-top border-secondary pt-2 align-items-center mt-2">
        <small class="elite-kills">
          <span class="text-monospace">{{ hero.kills.elites }}</span>
          Elite kills
        </small>
        <small class="level-circle" :class="{'text-danger': hero.dead}">
          {{ hero.level }}
        </small>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopHero',
  props: {
    hero: {
      type: Object,
      required: true
    }
  },
  computed: {
    heroClass () {
      const gender = this.hero.gender === 0 ? 'male' : 'female'return \`hero-${this.hero.classSlug} ${gender}\`
    }
  }
}
</script>

<style lang="stylus">.hero-portrait-wrapper.title-namecolor whitefont-weight 900

    .level-circlewidth 26pxheight 26pxpadding 4pxfont-weight boldtext-align centerborder-radius 13pxbackground-color #15202bbox-shadow 0 0 0 2px #6c757d
</style>
```

Y se vería así de sensacional 😏:

![preview-4](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/15/preview-4.png)**Prueba a cambiar los estilos de background position de las caras de los héroes desde el navegador a ver qué pasa**

Este tema ha sido un poco largo, pero hemos trabajado los estilos CSS globales de los rostros de nuestros personajes, hemos visto como trabajar con Sprites CSS, CSS Grid, como asociar clases y estilos dinámicos, etc.

Además, estamos creando una buena estructura de carpetas y componentes y lo más importante, ¡estamos pintando nuestro primer componente con datos reales del juego!

Continuamos en la siguiente lectura.


## 17. Listado de Héroes

Vamos a continuar con el resto de componentes de nuestra página de perfil de jugador.

En esta ocasión, tenemos que mostrar el resto de héroes que posee un jugador, si es que tiene alguno más. Para ello, haremos uso de las tablas de _bootstrap-vue_, que son muy fáciles de usar y versátiles.

> Recuerda, si no eres jugador de Diablo III y/o no tienes perfil propio, puedes usar este battle-tag `SuperRambo#2613`

> Además, si estás en _localhost_, puedes usar esta URL: [http://localhost:8080/#/region/eu/profile/SuperRambo-2613](http://localhost:8080/#/region/eu/profile/SuperRambo-2613)

Como vamos a crear otro bloque de componentes, tenemos que crear los directorios correspondientes. Lo que vamos a mostrar es un listado de héroes en una tabla, por lo tanto, suena razonable llamar a la carpeta de nuestro componente `HeroesList`. Creamos esta carpeta al mismo nivel que la de `TopHeroes`, es decir, dentro de `MainBlock`. Dentro de esta, vamos a crear tres componentes: `Index.vue` (el componente principal, como ya es habitual), `HeroIco.vue` y `HeroClassLevel.vue`.

```markdown
📂 MainBlock/
└──📂 HeroesList/
   ├── Index.vue
   ├── HeroIco.vue
   └── HeroClassLevel.vue
```

Al componente `Index` le vamos a dar este contenido, para poder usar luego:

```javascript
<template>
  <div>
    <h1>Heroes List</h1>
  </div>
</template>

<script>
export default {
  name: 'HeroesList'
}
</script>
```

Lo primero que vamos a hacer es ir a `MainBlock` (es decir, `/MainBlock/Index.vue`) para traer y usar el componente de `HeroesList`.

```javascript
// MainBlock/Index.vue
import HeroesList from './HeroesList/Index'
components: {
  HeroesList
}
```

En el componente `TopHeroes` hemos usado los tres primeros héroes del array de héroes que nos devolvía la API. En este caso vamos a usar el resto de héroes que no se hayan usado en `TopHeroes`.

Antes de poder usarlo, tenemos que comprobar que el array de héroes tiene más de tres elementos, por lo tanto vamos a crear dos _computed_ que nos ayuden con estas tareas:

```javascript
// ¿Hay más de tres elementos en el array?
hasHeroesList () {
  return this.profileData.heroes.length > 3
}
```

En caso afirmativo, dame todos los elementos del array sin contar los tres primeros. Seguimos con la otra propiedad computada:

```javascript
heroesList () {
  return this.profileData.heroes.slice(3, this.profileData.heroes.length)
}
```

Ahora sí, está listo para usarse en el HTML del componente `MainBlock`.

```html
<HeroesList v-if="hasHeroesList" :heroes="heroesList"/>
```

Sin contar la parte del CSS (que no ha cambiado), el componente `MainBlock/Index.vue` tiene este contenido:

```javascript
<template>
  <div class="grid-container">
    <div class="grid-item item-left">
      <TopHeroes v-if="hasHeroes" :heroes="topHeroes"/>
      <HeroesList v-if="hasHeroesList" :heroes="heroesList"/>
    </div>
    <div class="grid-item item-right">
      <h1>Derecha</h1>
    </div>
  </div>
</template>

<script>
import TopHeroes from './TopHeroes/Index'
import HeroesList from './HeroesList/Index'

export default {
  name: 'MainBlock',
  components: {
    TopHeroes,
    HeroesList
  },
  props: {
    profileData: {
      type: Object,
      required: true
    }
  },
  computed: {
    hasHeroes () {
      return this.profileData.heroes.length > 0
    },
    topHeroes () {
      return this.profileData.heroes.slice(0, 3)
    },
    hasHeroesList () {
      return this.profileData.heroes.length > 3
    },
    heroesList () {
      return this.profileData.heroes.slice(3, this.profileData.heroes.length)
    }
  }
}
</script>
```

Y se ve de esta forma:

![preview-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-1.png)Ahora que tenemos inyectados en el hijo los datos de los héroes que faltan por pintar, podemos empezar a trabajar con ellos en el componente `HeroesList/Index.vue`.

Lo primero que vamos a hacer es definir las _props_, que se las estamos pasando desde el padre pero el componente hijo no las tiene definidas:

```javascript
props: {
  heroes: {
    required: true,
    type: Array
  }
}
```

Para pintar la tabla en pantalla lo que tenemos que hacer es usar el componente tabla y pasarle como _prop_ el array de héroes.

Como tenemos el fondo oscuro, el texto negro de la tabla casi no se vería. Le agregamos la _prop_ `dark`:

```html
<b-table dark :items="heroes"/>
```

![preview-2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-2.png)

> 📗 La documentación de las tablas de _bootstrap-vue_, muy bien explicadas: [https://bootstrap-vue.js.org/docs/components/table](https://bootstrap-vue.js.org/docs/components/table)

Nosotros no queremos mostrar todos los elementos del array de héroes, por lo tanto vamos a definir que campos (columnas) queremos mostrar en nuestra tabla de héroes.

Para ello, siguiendo la documentación, creamos un objeto `fields` con las opciones y las columnas que queremos mostrar de nuestra tabla. Lo hacemos de la siguiente forma:

```javascript
data () {
  return {
    fields: \[
      {
        key: 'name',
        label: 'Name',
      },
      {
        key: 'class',
        label: 'Class',
        sortable: true
      },
      {
        key: 'kills',
        label: 'Elite Kills',
        sortable: true
      }
    \]
  }
}
```

Ya tenemos las columnas y las opciones que nos interesan listas para ser usadas. Actualicemos nuestra tabla agregando una nueva _prop_ `fields` que recibirá como valor el objeto con los campos que acabamos de definir:

```html
<b-table :items="heroes" :fields="fields" dark/>
```

Ahora nuestra tabla se ve mejor. Aún seguimos teniendo acceso a todos los demás datos, simplemente no los estamos mostrando.

![preview-3](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-3.png)

El componente tabla de _bootstrap-vue_ soporta muchas opciones. Vamos a personalizarlo un poco más con esta configuración:

```html
<b-table :items="heroes" :fields="fields" dark hover small striped stacked="sm"/>
```

Si seguimos lo que dice la documentación de las tablas de _bootstrap-vue_, podemos entender qué hace cada propiedad.

Aparte de los _items_ que le hemos pasado y la definición de las columnas que queremos, le estamos dando un tema oscuro, con efecto “on mouse hover” en cada fila, tamaño pequeño, diferenciado por colores, y, por último, una alternativa responsive para cuando la tabla tenga un tamaño pequeño.

OJO: Las propiedades de tipo `Boolean` de un componente _Vue_, cuando estas pasando el valor `true`, las puedes usar de 2 formas:

*   Forma larga:

```html
<b-table :items="heroes" :fields="fields" :dark="true" :hover="true" :small="true" :striped="true" stacked="sm"/>
```

*   Forma corta

```html
<b-table :items="heroes" :fields="fields" dark hover small striped stacked="sm"/>
```

Es decir, si queremos que la tabla tenga el tema oscuro, según la definición de su propiedad _dark_, podemos usar `<b-table dark/>` o `<b-table :dark="true"/>`.

Estos nos permite tener, por ejemplo, una _computed property_ que controle el estado de la propiedad _dark_. En ese supuesto caso podríamos alternar entre el tema oscuro y el tema claro de la tabla así: `<b-table :dark="tableTheme"/>`.

> 📗 Puedes ver más acerca de las _props_ y los _Boolean_ en este enlace: [https://es.vuejs.org/v2/guide/components-props.html#Pasando-un-booleano](https://es.vuejs.org/v2/guide/components-props.html#Pasando-un-booleano)

Ahora tenemos que darle formato a las filas de la tabla, por ejemplo, en base a la `class` que tenga el `heroe`. Es decir, en base al tipo de personaje que sea, podemos mostrar su ícono o rostro correspondiente. Lo mismo con el resto de valores; si es leyenda, si es hardcore, etc.

Para personalizar el contenido de la tabla vamos a hacer uso de los _Scoped Slots_ de _Vue_ junto con la funcionalidad de las tablas de _Bootstrap-vue_:

*   [https://vuejs.org/v2/guide/components-slots.html#Scoped-Slots](https://vuejs.org/v2/guide/components-slots.html#Scoped-Slots)
*   [https://bootstrap-vue.js.org/docs/components/table#scoped-field-slots](https://bootstrap-vue.js.org/docs/components/table#scoped-field-slots)

Los _Scoped Slots_ nos brindan un mayor control sobre cómo aparecen los datos de la tabla. Podemos usar _Scoped Slots_ para proporcionar una vista personalizada para un campo (columna) en particular.

Para poder continuar con los _slots_, necesitamos darle contenido a los componentes que hemos creado anteriormente (`HeroIco` y `HeroClassLevel`).

Estaría bien mostrar la imagen correspondiente al héroe, que representa su clase y género. Además del nombre, el nivel y la clase, deberíamos indicar de alguna forma si es de temporada y si es hardcore. Por último, deberíamos mostrar el nº de _kills_ que tiene actualmente ese personaje.

En el componente `HeroIco` vamos a encargarnos de mostrar: la imagen del héroe, el nombre, si es de temporada o no (🍃) y si es hardcore.

*   `HeroIco.vue`:

```html
<template>
  <div class="hero-ico d-flex align-items-center">
    <span class="hero-image border" :class="heroClassImg"/>
      <span class="hero-name ml-2 font-weight-bold" :class="{'text-danger': hero.hardcore}">
        {{ hero.name }}
      </span>
    <img v-if="hero.seasonal" src="@/assets/img/leaf.png" width="12px" class="ml-2" alt="seasonal_leaf">
  </div>
</template>
```

Este HTML es bastante sencillo. Reusamos clases CSS para mostrar el rostro de nuestro héroe a través de una clase según el tipo y el género. Si el _hero_ es hardcore, le ponemos el _border_ de la imagen rojo al igual que el texto del nombre. Si es de temporada, mostramos la ya reconocida hojita verde.

La lógica del componente es la siguiente:

```javascript
<script>
export default {
  name: 'HeroIco',
  props: {
    hero: {
      required: true,
      type: Object
    }
  },
  computed: {
    heroClassImg () {
      const gender = this.hero.gender === 1 ? 'female' : 'male'const hardcore = this.hero.hardcore ? 'border-danger' : ''return \`hero-${this.hero.classSlug} ${gender} ${hardcore}\`
    }
  }
}
</script>
```

Definimos las propiedades que va a recibir el componente y con una _computed_ generamos la clase CSS que va a tener: según el género, si es hardcore y el tipo (o clase) de héroe.

Recuerda que esto lo tenemos definido en el CSS global, que lo usamos con los _Sprites_ de CSS.

Ya por último, un par de líneas de CSS para personalizar un poco más el diseño de nuestro componente:

```javascript
<style lang="stylus">
  .hero-icovertical-align middle

    .hero-imagewidth 30pxheight 26pxdisplay inline-block
      background-size 210%

    .hero-nameheight 24pxdisplay inline-block
</style>
```

*   `HeroClassLevel.vue`:

En este componente vamos a incorporar algo que no hemos usado hasta el momento, los _Mixins_.

Los mixins son una forma flexible de crear funcionalidades reutilizables. Un objeto mixin puede contener cualquier opción de componente.

> 📗 Puedes leer más acerca de los Mixins de Vue en este enlace: [https://es.vuejs.org/v2/guide/mixins.html](https://es.vuejs.org/v2/guide/mixins.html)

Al igual que a los componentes, a los mixins los podemos crear de manera global o de manera local. Con un ejemplo lo entenderás mejor.

Crea el archivo `heroName.js` dentro de `/src/mixins` y dale este contenido:

import classes from '../utils/heroClasses'

```javascript
export default {
  methods: {
    classToName (classSlug) {
      return classes\[classSlug\]
    }
  }
}
```

Lo único que estamos haciendo en este mixin es exponer un _method_. Cuando importemos el mixin en un componente, en este componente tendremos acceso a este método `classToName`, como si de un método normal se tratara.

Además, estamos haciendo uso de otro archivo (`heroClasses`), que tenemos que crear ahora mismo dentro de `/src/utils`, con el nombre de `heroClasses.js` y que tiene un contenido muy simple:

```javascript
const classes = {
  barbarian: 'Barbarian',
  crusader: 'Crusader',
  'demon-hunter': 'Demon Hunter',
  monk: 'Monk',
  necromancer: 'Necromancer',
  'witch-doctor': 'Witch Doctor',
  wizard: 'Wizard'
}
```

export default classes

De esta forma, si necesitamos pintar el tipo de una clase de personaje, podemos usar esto.

Para usar esta funcionalidad, tenemos que importar y dar de alta el mixin de manera local en nuestro componente. Una vez hayamos hecho esto, podremos acceder al método que acabamos de crear (`classToName`) como si fuese un _method_ interno del componente.

Para hacer esto en nuestro componente `HeroClassLevel.vue`, en el bloque de `javascript`, hacemos lo siguiente:

```javascript
<script>
// Traemos el mixin
import heroName from '@/mixins/heroName.js'

export default {
  name: 'HeroNameLevel',
  // Lo damos de alta
  mixins: \[heroName\],
  props: {
    hero: {
      required: true,
      type: Object
    }
  }
}
</script>
```

Ahora tenemos acceso al método desde cualquier parte del componente, como si fuera un _method_ normal:

*   En el HTML, `classToName(val)`
*   Desde JavaScript, `this.classToName(val)`

Ahora sí, podemos crear el HTML de nuestro componente `HeroClassLevel.vue`:

```html
<template>
  <div class="hero-name-level">
  <span> {{ classToName(hero.classSlug) }} </span>
  <span>·</span>
  <span class="text-monospace font-weight-bold">
    {{ hero.level }}
  </span>
  </div>
</template>
```

Haciendo uso del mixin, estamos mostrando el tipo de héroe normalizado. Es decir, si el tipo es `demon-hunter`, lo que vamos a renderizar en la vista es `Demon Hunter`. Además estamos mostrando el nivel. Es un componente muy básico.

Este componente no necesita clases CSS, por lo que ya estaría completo.

Hemos creado un mixin de Vue que hace uso de otros archivos y lo hemos usado en nuestro componente.

  

El código completo de lo que hemos hecho hasta el momento se vería así:

*   `HeroIco.vue`

```javascript
<template>
  <div class="hero-ico d-flex align-items-center">
    <span class="hero-image border" :class="heroClassImg"/>
    <span class="hero-name ml-2 font-weight-bold" :class="{'text-danger': hero.hardcore}">
      {{ hero.name }}
    </span>
    <img v-if="hero.seasonal" src="@/assets/img/leaf.png" width="12px" class="ml-2" alt="seasonal_leaf">
  </div>
</template>

<script>
export default {
  name: 'HeroIco',
  props: {
    hero: {
      required: true,
      type: Object
    }
  },
  computed: {
    heroClassImg () {
      const gender = this.hero.gender === 1 ? 'female' : 'male'const hardcore = this.hero.hardcore ? 'border-danger' : ''return \`hero-${this.hero.classSlug} ${gender} ${hardcore}\`
    }
  }
}
</script>

<style lang="stylus">.hero-icovertical-align middle

    .hero-imagewidth 30pxheight 26pxdisplay inline-blockbackground-size 210%

    .hero-nameheight 24pxdisplay inline-block
</style>
```

*   `HeroClassLevel.vue`

```javascript
<template>
  <div class="hero-name-level">
    <span> {{ classToName(hero.classSlug) }} </span>
    <span>·</span>
    <span class="text-monospace font-weight-bold"> {{ hero.level }} </span>
  </div>
</template>

<script>
import heroName from '@/mixins/heroName.js'

export default {
  name: 'HeroNameLevel',
  mixins: \[heroName\],
  props: {
    hero: {
      required: true,
      type: Object
    }
  }
}
</script>
```

Ahora que ya tenemos nuestros componentes, vamos a modificar la tabla que hemos creado anteriormente, y aprovecharemos para darle estilos CSS que mejoren el aspecto de nuestro componente.

```html
  <div class="heroes-list border-top border-secondary mt-5 pt-5">
    <b-table hover striped dark :items="heroes" :fields="fields" stacked="sm" small>
      <!-- Contenido -->
    </b-table>
  </div>
```

Ahora, haciendo uso de los _slots_ de Vue y del componente tabla, vamos a personalizar el contenido de nuestras celdas.

En la primera columna vamos a insertar el componente `HeroIco.vue`. Lo haríamos de la siguiente forma, dentro de la tabla:

```html
<template v-slot :cell(name)="data">
  <HeroIco :hero="data.item"/>
</template>
```

> 📗 En este artículo explican brevemente los _slots_: [https://vuedose.tips/tips/new-v-slot-directive-in-vue-js-2-6-0/](https://vuedose.tips/tips/new-v-slot-directive-in-vue-js-2-6-0/)

En este fragmento de código estamos indicando que la columna `name` (nombre del campo que hemos definido en la variable `fields`) de la tabla muestre el componente `HeroIco` en vez de el texto por defecto.

> ![preview-4](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-4.png)📗 Te recomiendo que leas esto, pues explican bastante bien el tema de los _slots_: [https://github.com/vuejs/rfcs/blob/master/active-rfcs/0001-new-slot-syntax.md](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0001-new-slot-syntax.md)

Tendríamos que hacer lo mismo para la columna `class` (la segunda), pero cambiando de componente. En este caso `HeroClassLevel`:

```javascript
<template v-slot:cell(class)="data">
  <HeroClassLevel :hero="{ class: data.item.class, level: data.item.level}"/>
</template>
```

A estas alturas, seguramente te hayas dado cuenta de que esto no puede funcionar si no has registrado el componente.

Por lo tanto, siguiendo en la tabla del componente `/HeroesList/Index.vue`, deberíamos hacer lo siguiente:

```javascript
<script>
import HeroIco from './HeroIco'
import HeroClassLevel from './HeroClassLevel'

export default {
  name: 'HeroesList',
  components: { HeroIco, HeroClassLevel }
  // ...
}
</script>
```

A falta de la última columna de la tabla, nuestra app debería verse así:

![preview-5](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-5.png)Lo bueno de hacer componentes es que nuestra app es más modular, y, por lo tanto, fácil de testear.

Sin embargo, podemos hacerlo sin usar un componente. Para ver cómo se haría, en la tercera columna de nuestra tabla no vamos a usar un componente para mostrar los datos, aunque no sea lo recomendado:

```html
<template v-slot :cell(kills)="data">
  <span>{{ data.item.kills.elites }}</span>
</template>
```

![preview-6](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-6.png)¡Estupendo! Ya estaría nuestra tabla lista.

La columna _kills_ de la tabla tiene (o puede tener) unos valores numéricos bastante grandes. Parece una buena idea formatear el valor de dicho campo haciendo uso de los puntos (`.`) y/o de las comas (`,`) para facilitar su lectura.

Para realizar esta tarea, en vez de desarrollar una función que haga el trabajo, vamos a usar una librería JavaScript llamada [Numeral.js](http://numeraljs.com/). _Numeral_ es, según dicen en la web, una librería para formatear y manipular números. Justo lo que necesitamos.

Vamos a crear un filtro de Vue, es decir, una función JavaScript que cuando le pasemos un número nos lo devuelva formateado.

> 📗 La documentación de los filtros de Vue: [https://es.vuejs.org/v2/guide/filters.html](https://es.vuejs.org/v2/guide/filters.html)

Para eso, en nuestra carpeta `/filters` creamos un archivo llamado `numeral.js`. Los pasos a seguir son 3:

*   Importar la librería
*   Crear la función que será nuestro filtro Vue
*   Exportar la función para que pueda ser usada

```javascript
// Paso 1
import numeral from 'numeral'

// Paso 2
// Función que recibe un argumento (Número o String numérico) y lo devuelve formateado
// Si no hay numero, devolvemos 0
const formatNumber = (num) => {
  if (!num) {
    return 0
  }
  return numeral(Number(num)).format()
}

// Paso 3
export {
  formatNumber
}
```

Esto que acabamos de hacer de manera tan sencilla, es un filtro. Para usarlo, es lo mismo que con los mixins o con los componentes.

Puedes usarlo a nivel global de la app o usarlo a nivel local en el componente que lo necesites. En este caso lo vamos a usar de manera local.

Para ello, en el componente donde tenemos la tabla que estamos usando, es decir, en `/Profile/MainBlock/HeroesList/Index.vue`, agregamos lo siguiente:

*   Lo primero, traer la función que acabamos de crear

import { formatNumber } from '@/filters/numeral'

*   Lo segundo, dar de alta esta función (`formatNumber`) en el componente, para que pueda ser usado desde el template. Como se trata de un filtro, lo haremos desde el bloque de _filters_:

```javascript
export default {
  name: 'HeroesList',
  filters: {
    formatNumber
  }
  // ...
}
```

Ahora solo queda usarlo. Usar un filtro es muy sencillo:

```html
<template v-slot:cell(kills)="data">
  <span>{{ data.item.kills.elites | formatNumber }}</span>
</template>
```

Ahora la tercera columna de nuestra tabla se vería así:

![preview-7](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-7.png)

Haciendo pruebas con usuarios de otras regiones, encontré uno de la region de Korea (`KR`) con personajes _hardcore_ de temporada: `오빠-3239`. Este usuario ([http://localhost:8080/#/region/kr/profile/오빠-3239](http://localhost:8080/#/region/kr/profile/%EC%98%A4%EB%B9%A0-3239)) se vería así:

![preview-8](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-8.png)

Como puedes ver en esta imagen, los tres _Top Heroes_ tienen los _elite kills_ sin formatear. Ahora que tenemos el filtro creado, ¿por qué no lo usamos para formatear este valor?

Abrimos el fichero `/views/Profile/MainBlock/TopHeroes/TopHero.vue`, importamos el filtro, lo habilitamos para poder usarlo en el template y lo usamos para formatear:

```javascript
// /TopHeroes/TopHero.vue
import { formatNumber } from '@/filters/numeral'
// Creamos el bloque filters
filters: { formatNumber }
<small class="elite-kills"><span class="text-monospace">{{ hero.kills.elites | formatNumber }}</span>
  Elite kills
</small>
```

Y ahora el componente de `TopHeroes` se vería así:

![preview-9](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/16/preview-9.png)A partir de ahora, cada vez que tengamos que formatear un valor numérico, podemos usar este filtro que hemos creado. Y si nos hace falta formatear otro valor con otro formato, siempre podemos crear otro.

  

Este es el código completo de los componentes que hemos usado en este tema:

*   `/HeroesList/Index.vue`

```javascript
<template><div class="heroes-list border-top border-secondary mt-5 pt-5"><b-tablehoverstripeddark:items="heroes":fields="fields"stacked="sm"small
    ><!-- Contenido --><template v-slot:cell(name)="data"><HeroIco :hero="data.item"/></template>

      <template v-slot:cell(class)="data"><HeroClassLevel :hero="{ class: data.item.classSlug, level: data.item.level}"/></template>

      <template v-slot:cell(kills)="data"><span>{{ data.item.kills.elites | formatNumber }}</span></template>

    </b-table></div>
</template>

<script>
import { formatNumber } from '@/filters/numeral'

import HeroIco from './HeroIco'
import HeroClassLevel from './HeroClassLevel'

export default {
  name: 'HeroesList',
  filters: { formatNumber },
  components: { HeroIco, HeroClassLevel },
  props: {
    heroes: {
      required: true,
      type: Array
    }
  },
  data () {
    return {
      fields: \[
        {
          key: 'name',
          label: 'Name'
        },
        {
          key: 'class',
          label: 'Class',
          sortable: true
        },
        {
          key: 'kills',
          label: 'Elite Kills',
          sortable: true
        }
      \]
    }
  }
}
</script>

*   `/HeroesList/HeroIco.vue`

<template><div class="hero-ico d-flex align-items-center"><span class="hero-image border" :class="heroClassImg"/><span class="hero-name ml-2 font-weight-bold" :class="{'text-danger': hero.hardcore}">{{ hero.name }}</span><img v-if="hero.seasonal" src="@/assets/img/leaf.png" width="12px" class="ml-2" alt="seasonal_leaf"></div>

</template>

<script>
export default {
  name: 'HeroIco',
  props: {
    hero: {
      required: true,
      type: Object
    }
  },
  computed: {
    heroClassImg () {
      const gender = this.hero.gender === 1 ? 'female' : 'male'const hardcore = this.hero.hardcore ? 'border-danger' : ''return \`hero-${this.hero.classSlug} ${gender} ${hardcore}\`
    }
  }
}
</script>

<style lang="stylus">.hero-icovertical-align middle

    .hero-imagewidth 30pxheight 26pxdisplay inline-blockbackground-size 210%

    .hero-nameheight 24pxdisplay inline-block
</style>
```

*   `/HeroesList/HeroClassLevel.vue`

```javascript
<template><div class="hero-name-level"><span> {{ classToName(hero.class) }} </span><span>·</span><span class="text-monospace font-weight-bold"> {{ hero.level }} </span></div>
</template>

<script>
import heroName from '@/mixins/heroName.js'

export default {
  name: 'HeroNameLevel',
  mixins: \[heroName\],
  props: {
    hero: {
      required: true,
      type: Object
    }
  }
}
</script>

*   `/mixins/heroName.js`

import classes from '../utils/heroClasses'

export default {
  methods: {
    classToName (classSlug) {
      return classes\[classSlug\]
    }
  }
}

*   `/utils/heroClasses.js`

const classes = {
  barbarian: 'Barbarian',
  crusader: 'Crusader',
  'demon-hunter': 'Demon Hunter',
  monk: 'Monk',
  necromancer: 'Necromancer',
  'witch-doctor': 'Witch Doctor',
  wizard: 'Wizard'
}

export default classes
```

El componente que veremos en la siguiente lectura mostrará el progreso del usuario en la historia (o campaña) del juego.


## 18. Progreso (Actos)

Uno de los valores que nos devuelve la API del juego cuando le pedimos los datos de un jugador es el progreso. Esto nos indica el estado de los actos (hay cinco), es decir, si los ha completado o no.

Vamos a crear un componente, muy sencillo, que nos indique si el usuario ha completado un acto o no. Para indicar si el acto está completado o no usaremos una imagen (Sprites CSS), que estará oscurecida y con un candado cuando esté sin completar y sin el candado y bien clara cuando esté completado.

La imagen que usaremos como Sprite CSS es esta:

![progress](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/17/progress.png)

Lo primero que vamos a hacer es crear los estilos CSS, en nuestro fichero global de CSS, `/assets/main.styl`. Vamos a añadir el siguiente contenido:

```stylus
// ---------------------
// Acts
// ---------------------

.actbackground-image: url('../img/progress.png')
  background-size 500%

  &.act1
    &.pendingbackground-position -1px 0

    &.donebackground-position -1px 57px

  &.act2
    &.pendingbackground-position -51px 0

    &.donebackground-position -51px -56px

  &.act3
    &.pendingbackground-position -101px 0px

    &.donebackground-position -101px -168px

  &.act4
    &.pendingbackground-position -151px 0px

    &.donebackground-position -151px -168px

  &.act5
    &.pendingbackground-position 50px 0

    &.donebackground-position 50px 57px
```

Hemos creado unas clases CSS que nos van a permitir mostrar la imagen correspondiente a cada acto y sus dos estados: `pending` (sin completar) y `done` (completado). Si queremos mostrar el _acto dos completado_ lo que tenemos que hacer es tan sencillo como darle las clases `"act act2 done"`.

Esto nos mostraría la porción de imagen correspondiente al acto 2 completado, que lo estamos controlando con la propiedad CSS de _background-positon_.

Ahora tenemos que crear los archivos y directorios que vamos a utilizar con este componente de progreso de la historia del juego. Cuando juegas a Diablo III puedes subir niveles y hacer misiones especiales sin necesidad de completar la historia del juego.

> 📗 Diablo 3 - Modos de juego: [https://eu.diablo3.com/es/game/guide/gameplay/game-modes](https://eu.diablo3.com/es/game/guide/gameplay/game-modes)

Es por eso que implementamos este componente. Para ello, al mismo nivel del directorio `/TopHeroes`, creamos un directorio llamado `/ProgressList`. Dentro de este, creamos 2 ficheros: `Index.vue` y `ProgressItem.vue`.

```markdown
📂 /MainBlock
└──📂 /ProgressList
   ├── Index.vue
   └── ProgressItem.vue
```

El objeto que vamos a usar para pintar nuestro componente tiene este formato:

```javascript
{ "progression": { "act1":true, "act3":true, "act2":true, "act5":true, "act4":true } }
```

Fíjate que no viene ordenado por actos, por lo que vamos a tener que realizar esta tarea de ordenamiento antes de poder iterar sobre el objeto de _progression_.

Lo primero que vamos a hacer es usar el componente (aunque esté vacío) en el componente padre, es decir, en `/MainBlock/Index.vue`. Los 3 pasos de siempre. Importar, habilitar, utilizar.

```javascript
// MainBlock/Index.vue

// ...
import ProgressList from './ProgressList/Index'

export default {
  name: 'MainBlock',
  components: { ProgressList, HeroesList, TopHeroes }
  // ...
}
```

Para usarlo, debajo del componente `HeroesList`, agregamos lo siguiente:

```html
<div class="grid-item item-left">
  <TopHeroes v-if="hasHeroes" :heroes="topHeroes"/>

  <HeroesList v-if="hasHeroesList" :heroes="heroesList"/>

  <ProgressList :acts="profileData.progression"/>
</div>
```

Al abrir la consola del navegador, es normal que veas errores o que la app no te funcione. Lo iremos corrigiendo a medida que vayamos avanzando.

  

Empezamos con el componente principal, es decir, con `/ProgressList/Index.vue`:

```javascript
<template>
  <div class="progression-bosses pt-4 mt-5 border-top">
    <h2 class="font-diablo mb-4">Progression</h2>
    <b-row>
      <b-col v-for="(val, key) in sortedActs" :key="key" class="col-12 col-md-2">
        <div class="bg-dark rounded mb-2">
          <ProgressItem :act="{actNum: key, value: val}"/>
        </div>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import ProgressItem from './ProgressItem'

export default {
  name: 'ProgressBosses',
  components: { ProgressItem },
  props: {
    acts: {
      required: true,
      type: Object
    }
  },
  computed: {
    /\*\*
       \* Order acts from 1 to 5
       \* @returns {Object} Ordered acts
       \*/
    sortedActs () {
      return Object.keys(this.acts)
        .sort()
        .reduce((a, c) => {
          a\[c\] = this.acts\[c\]
          return a
        }, {})
    }
  }
}
</script>

<style lang="stylus">.progression-bosses.boss-imgdisplay block

      .actmargin 0 autowidth 50pxheight 55px
</style>
```

Todo lo que tiene este componente no requiere explicación, puesto que es un componente muy sencillo.

A modo de resumen este componente tiene definidas una _prop_, que son los actos, que los ordenamos a través de la función _sortedActs_ (aunque en realidad es una _computed property_).

En el HTML iteramos sobre este objeto que contiene los actos ordenados del uno al cinco y cada elemento corresponde a otro componente (`ProgressItem`, que vamos a ver ahora) que recibe como parámetro un objeto con el acto (ej. `act2`) y el valor (ej. `true`).

El componente `ProgressItem.vue` tiene el siguiente contenido:

```javascript
<template>
  <div class="d-flex flex-column" :title="actTitle">
    <div class="boss-img pt-2">
      <div class="act" :class="actClass"></div>
    </div>
    <p class="d-block text-center m-0 lead font-weight-bold">
      {{ fullActName }}
    </p>
  </div>
</template>

<script>
const acts = {
  act1: 'I',
  act2: 'II',
  act3: 'III',
  act4: 'IV',
  act5: 'V'
}

export default {
  name: 'ProgressItem',
  props: {
    act: {
      required: true,
      type: Object,
      validator: (obj) => {
        return Object.keys(obj).length === 2
      }
    }
  },
  computed: {
    fullActName () {
      return \`Act ${acts\[this.act.actNum\]}\`
    },
    actClass () {
      const status = this.act.value ? 'done' : 'pending'return \`${this.act.actNum} ${status}\`
    },
    actTitle () {
      return this.act.value
        ? 'Act completed! 💃'
        : 'Act uncompleted 🙈'
    }
  }
}
</script>
```

Aunque este componente es bastante sencillo, vamos a comentar un par de cosas:

*   La prop _act_ tiene una función de validación distinta a las que hemos visto anteriormente. No es gran cosa, pero está comprobando que el numero de claves del objeto que recibe sea igual a 2. Muy simple.
*   La _computed property_ `actTitle` nos devuelve un `String` dependiendo del valor del acto, es decir, si está completado o no. Para poder ver este texto, deberías dejar el ratón encima de dicho elemento unos segundos.
*   Lo diferencial de esto es que estamos incluyendo emojis (íconos) en el texto. ¡Sí! Los emojis los podemos usar como texto normal, usando las comillas, como si de un texto se tratara. 🤘😏🤘

> 📗 _No soy muy fan de W3Schools, pero en este caso podemos hacer una excepción_. Explicación de los emojis en la web: [https://www.w3schools.com/html/html_emojis.asp](https://www.w3schools.com/html/html_emojis.asp)

Exceptuando un par de cosas, estos componentes que acabamos de crear no tenían complejidad alguna. Si has seguido todos los pasos correctamente, la app debería verse así:

![preview-1.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/17/preview-1.png)Modificando los valores desde las _Vue DevTools_ en el navegador, para ver ambos estados en acción:

![preview-2.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/17/preview-2.png)

Y esto sería todo. Ahora vamos a empezar con el bloque de la derecha de nuestro grid, donde trabajaremos con los _stats_ del usuario y el tiempo jugado por héroe.

Quédate con lo de los emojis en mente, pues los volveremos a utilizar más adelante.


## 19. Stats y Tiempo Jugado

En este apartado vamos a terminar el componente de `MainBlock`. Vamos a crear, primero, la estructura de carpetas.

Dentro de `/MainBlock` creamos una nueva carpeta `/PlayerStats`. Dentro vamos a crear `Index.vue`, `SingleStat.vue`, `TimePlayed.vue` y `TimePlayedHero.vue`:

```markdown
📂 /MainBlock
└──📂 /PlayerStats
   ├── Index.vue
   ├── SingleStat.vue
   ├── TimePlayed.vue
   └── TimePlayedHero.vue
```

Ahora, en el componente `MainBlock`, en el bloque de la derecha, quitamos el texto que teníamos puesto y ponemos el componente que acabamos de crear. El HTML de `/MainBlock/Index.vue` se vería así:

```html
<template>
  <div class="grid-container">
    <div class="grid-item item-left">

      <TopHeroes v-if="hasHeroes" :heroes="topHeroes"/>

      <HeroesList v-if="hasHeroesList" :heroes="heroesList"/>

      <ProgressList :acts="profileData.progression"/>

    </div>

    <!-- Right Bar-->
    <div class="grid-item item-right">

      <PlayerStats :stats="statsData"/>

    </div>

  </div>
</template>
```

La _prop_ que le estamos pasando a `PlayerStats` con el nombre de _stats_, es una _computed property_. `statsData` tiene el siguiente contenido:

```javascript
statsData () {
  const { paragonLevel, kills, timePlayed } = this.profileData
  return { paragonLevel, kills, timePlayed }
}
```

Lo que devuelve `statsData` son los datos que necesita nuestro componente de _stats_:

*   Paragon level: nivel de leyenda.
*   Kills: monstruos y élites.
*   Time played: Tiempo jugado por héroe en porcentaje.
*   Esto quiere decir que si has jugado 10 minutos con el monje y 5 minutos con el cruzado vas a tener el monje al 100% y el cruzado al 50%. No está basado en horas o minutos.

El código completo del componente `MainBlock` (sin contar el CSS, que no ha cambiado) es este:

```javascript
<template>
  <div class="grid-container">
    <div class="grid-item item-left">

      <TopHeroes v-if="hasHeroes" :heroes="topHeroes"/>

      <HeroesList v-if="hasHeroesList" :heroes="heroesList"/>

      <ProgressList :acts="profileData.progression"/>

    </div>

    <!-- Right Bar-->
    <div class="grid-item item-right">

      <PlayerStats :stats="statsData"/>

    </div>

  </div>
</template>

<script>

import TopHeroes from './TopHeroes/Index'
import HeroesList from './HeroesList/Index'
import ProgressList from './ProgressList/Index'
import PlayerStats from './PlayerStats/Index'

export default {
  name: 'MainBlock',
  components: { PlayerStats, ProgressList, HeroesList, TopHeroes },
  props: {
    profileData: {
      type: Object,
      required: true
    }
  },
  computed: {
    hasHeroes () {
      return this.profileData.heroes.length > 0
    },
    hasHeroesList () {
      return this.profileData.heroes.length > 3
    },
    topHeroes () {
      return this.profileData.heroes.slice(0, 3)
    },
    heroesList () {
      return this.profileData.heroes.slice(3, this.profileData.heroes.length)
    },
    statsData () {
      const { paragonLevel, kills, timePlayed } = this.profileData
      return { paragonLevel, kills, timePlayed }
    }
  }
}
</script>
```

El HTML del componente `PlayerStats` es el siguiente:

```html
<template>
  <div class="multi-stats pl-lg-4">
    <hr class="bg-white mt-5 d-lg-none">
      <h2 class="font-diablo my-4">Stats</h2>
      <div class="stats d-flex flex-column bg-dark p-3">

        <SingleStat class="mb-3" ico-name="skull" ico-color="#9E9E9E" :info="{value: stats.kills.monsters, text:'Lifetime Kills'}" />

        <SingleStat class="mb-3" ico-name="crown" ico-color="#ffc107" :info="{value: stats.kills.elites, text:'Elite Kills'}"/>

        <SingleStat ico-name="dungeon" ico-color="#795548" :info="{value: stats.paragonLevel, text:'Paragon Level'}"/>

      </div>

    <TimePlayed :timePlayed="timePlayed"/>

  </div>
</template>
```

`PlayerStats` hace uso de dos componentes distintos.

Por un lado tenemos el componente `SingleStat.vue`. Lo único distinto aquí es la propiedad `ico-name`, que se refiere al nombre del ícono de _FontAwesome_.

> 📗 Ver documentación de _Vue FontAwesome_: [https://github.com/FortAwesome/vue-fontawesome#usage](https://github.com/FortAwesome/vue-fontawesome#usage)

Por otro lado, el componente `TimePlayed.vue` itera sobre el objeto que contiene los tiempos por cada personaje, y, en su interior, hace uso del componente de barra de progreso de bootstrap-vue ([https://bootstrap-vue.js.org/docs/components/progress](https://bootstrap-vue.js.org/docs/components/progress)).

El bloque `<script></script>` del componente `PlayerStats/Index.vue` es el siguiente:

```javascript
import heroName from '@/mixins/heroName'
import SingleStat from './SingleStat'
import TimePlayed from './TimePlayed'

export default {
  name: 'PlayerStats',
  mixins: \[heroName\],
  components: {
    TimePlayed,
    SingleStat
  },
  props: {
    stats: {
      required: true,
      type: Object
    }
  }
}
```

De momento, no hay nada nuevo que explicar. Tenemos un _mixin_ y dos componentes.

Nos vamos a centrar en el segundo componente, `TimePlayed.vue`.

Antes de revisar el componente `TimePlayed`, vamos a copiar el contenido del componente `SingleStat.vue` para pegarlo en nuestro fichero:

```javascript
<!-- SingleStat.vue -->
<template>
  <div class="single-stat w-100">
    <b-card class="text-body">
      <div class="d-flex">
        <div class="d-block ico-cont">
          <div class="text-center">
            <!-- Ícono & Color-->
            <font-awesome-icon :icon="icoName" class="fa-3x" :style="{color: icoColor}"/>
          </div>
        </div>
        <div class="flex-grow-1">
          <!-- Valor & Filtro -->
          <h4 class="font-weight-bold mb-0">{{ info.value | formatNumber }}</h4>
          <!-- Texto -->
          <span class="text-muted font-weight-light mb-0">{{ info.text }}</span>
        </div>
      </div>
    </b-card>
  </div>
</template>

<script>
import { formatNumber } from '@/filters/numeral'

export default {
  name: 'SingleStat',
  filters: {
    formatNumber
  },
  props: {
    icoName: {
      required: true,
      type: String
    },
    icoColor: {
      required: true,
      type: String
    },
    info: {
      required: true,
      type: Object
    }
  }
}
</script>

<style lang="stylus" scoped>
  .single-stat.ico-contwidth 80px
</style>
```

Como has podido ver, este componente no tiene ninguna complicación. Simplemente pinta los datos que le pasamos: el ícono, color del ícono y valor numérico (formateado con el filtro de _numeral_). Deberías ver algo así:

![preview-1.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/18/preview-1.png)

Acuérdate, a los íconos los estamos pintando gracias a _FontAwesome_.

`TimePlayed.vue` tiene una configuración especial que vamos a explicar ahora. Cuando estamos definiendo las _props_ de un componente, podemos validar el valor que recibe la propiedad a través de una función y definir el tipo de variable que espera dicha propiedad. Lo hemos hecho en algún caso. Ejemplo:

```javascript
props: {
  type: {
    required: false,
    type: String,
    default: 'border',
    validator: (value) => {
      return \['border', 'grow'\].indexOf(value) !== -1
    }
  }
}
```

¿Qué pasa si yo quiero validar un tipo (_type_) de objeto específico?

Algo que no sea, por ejemplo, un _String_ o un _Object_. Vue nos permite crear nuestros propios tipos de dato y poder usarlos como _type_.

Custom Types
------------

Con un ejemplo lo verás más claro. Imagina que queremos crear un tipo que sea `Persona`. Una `Persona` tiene nombre y el apellido. Podríamos crear algo como esto:

```javascript
function Persona (nombre, apellido) {
  this.nombre = nombre
  this.apellido = apellido
}
```

Y luego, dentro de nuestro componente lo podríamos usar así:

```javascript
props: {
  author: {
    type: Persona, // Tipo que acabamos de crear
    required: true
  }
}
```

> 📗 Aquí explican, un poco más, como funciona esto de los _custom types_: [https://es.vuejs.org/v2/guide/components-props.html#Tipos-de-la-validacion](https://es.vuejs.org/v2/guide/components-props.html#Tipos-de-la-validacion)

Esto es lo que vamos a hacer en nuestro componente `TimePlayed`: vamos a crearnos un tipo de dato personalizado para poder usarlo en la definición de las _props_.

Lo primero que vamos a hacer es crear la función _tipo_. Vamos a crearla en la carpeta `/utils`. Al fichero, le vamos a dar el nombre de `typeValidation.js`. El contenido es el siguiente:

```javascript
/\*\*
 \* Used for custom validations
 \* @param hero {String}
 \* @param time {String}
 \* @param classSlug {String}
 \* @constructor
 \*/
function HeroData (hero, time, classSlug) {
  this.hero = hero
  this.time = time
  this.classSlug = classSlug
}

export {
  HeroData
}
```

Con esto hemos creado una función que usaremos como un nuevo tipo de dato. Podemos usar esta función y definir nuestra propiedad del componente como `HeroData` 💃.

A continuación, si revisas cómo está usándose el componente `TimePlayed` en `PlayerStats/Index.vue`, puedes ver que tiene este HTML:

```html
<TimePlayed :timePlayed="timePlayed"/>
```

Sin embargo, no tenemos nada definido como `timePlayed` dentro de nuestro componente `PlayerStats`.

Para crear este dato, en el componente `PlayerStats/Index.vue` creamos una _computed property_ con este nombre, de esta forma:

```javascript
computed: {
  timePlayed () {
    return Object.keys(this.stats.timePlayed)
      .sort()
      .map(hero => {
        return new HeroData(
          this.classToName(hero), 
          this.stats.timePlayed\[hero\], 
          hero
        )
      })
  }
}
```

Si inspeccionamos el navegador y analizamos el objeto de `stats.timePlayed`, vemos que tiene este contenido:

```javascript
{
  "demon-hunter":0.424,
  "barbarian":0.055,
  "witch-doctor":0.319,
  "necromancer":0.226,
  "wizard":0.103,
  "monk":1,
  "crusader":0.399
}
```

Lo que estamos haciendo en esta _computed property_ es obtener todas las claves (_keys_) de este objeto, ordenarlas con `sort`, y, sobre este array de items ordenados, usar la función `map`. Con esto estaríamos generando un array de objetos con estos datos:

```javascript
\[
  {
    hero: 'Barbarian',
    time: 0.055,
    classSlug: 'barbarian'
  }, 
  {
    hero: 'Crusader',
    time: 0.399,
    classSlug: 'crusader'
  }, 
  {
    hero: 'Demon Hunter',
    time: 0.424,
    classSlug: 'demon-hunter'
  }
  // ...
\]
```

Con esto ya tenemos el nombre del héroe normalizado y el valor del tiempo. Además, estos datos los hemos creado con nuestra función _HeroData_, que utilizaremos más adelante.

Vayamos entonces al componente `PlayerStats/TimePlayed.vue`. Este componente también es muy sencillo y no requiere una explicación extensa:

```javascript
<template>
  <div class="time-played mt-3">
    <hr class="bg-white mt-5">
    <h2 class="font-diablo my-4">Time Played</h2>
    <div class="bg-dark p-3">
      <div v-for="hero in timePlayed" :key="hero.classSlug">
        <TimePlayedHero :hero-time="hero"/>
      </div>
    </div>
  </div>
</template>

<script>
import TimePlayedHero from './TimePlayedHero'

export default {
  name: 'TimePlayed',
  components: { TimePlayedHero },
  props: {
    timePlayed: {
      required: true,
      type: Array
    }
  }
}
</script>
```

Un _v-for_ para recorrer el array de elementos de tipo _HeroData_ que le hemos pasado como _property_ y para cada elemento renderizamos el componente `TimePlayedHero`. Es aquí donde vamos a usar nuestra _custom validation_.

  

Vamos a explicar el componente `TimePlayedHero.vue`:

*   El bloque de JavaScript tiene lo siguiente:

```javascript
<script>
// Traemos nuestro tipo personalizado
import { HeroData } from '@/utils/typeValidation'

export default {
  name: 'TimePlayedHero',
  props: {
    // Definimos la propiedad con el tipo personalizado 'HeroData'
    heroTime: {
      type: HeroData,
      required: true
    }
  },
  computed: {
    // Cada héroe tiene un color// Creamos una clase por cada héroe
    classHeroBg () {
      return \`hero-bg-color-${this.heroTime.classSlug}\`
    }
  }
}
</script>
```

La propiedad `heroTime` que recibe el componente , y que es de tipo _HeroData_, tiene este formato:

```javascript
{
  "hero": "Barbarian",      // String"time": 0.055,            // Number"classSlug": "barbarian"  // String
}
```

Lo bueno de haber usado el _custom type_ es que si en vez de pasarle un dato de tipo _HeroData_ le hubiéramos pasado un dato con el mismo formato que _HeroData_ (es decir, un objeto con las 3 claves: `hero`, `time` y `classSlug`) pero que no ha sido creado con el constructor de _HeroData_, Vue nos indicará que ese tipo no es el esperado.

En este caso, para forzar el error, he usado un objeto en vez del tipo _HeroData_. Si lo cambias, deberías ver un error como este:

![custom-type-err.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/18/custom-type-err.png)Es aquí dónde vemos la verdadera utilidad de los _custom types_.

Recuerda que vamos a hacer uso del componente _progress_ de bootstrap-vue, que se utiliza bajo el nombre de `<b-progress>`.

Más info: [https://bootstrap-vue.js.org/docs/components/progress](https://bootstrap-vue.js.org/docs/components/progress)

*   El HTML (de _TimePlayedHero_) es el siguiente:

```html
<template>
  <div class="progress-time-played">
    <div class="d-flex justify-content-between">
      <h5 class="mb-0 font-weight-lighter"> {{heroTime.hero}} </h5>
      <span>
        <b-badge class="w-50p">{{ (heroTime.time \* 100).toFixed(2) }}</b-badge>
      </span>
    </div>
    <b-progress :max="1" height="14px" class="mb-3 rounded-0">
      <b-progress-bar :value="heroTime.time" :class="classHeroBg">
        {{ heroTime.hero }}
      </b-progress-bar>
    </b-progress>
  </div>
</template>
```

Como hemos establecido el valor máximo (`:max`) de la barra de progreso en `1`, no hace falta que transformemos el valor (`heroTime.time`).

Con la clase CSS resultante de ejecutar `classHeroBg`, estamos estableciendo un color para cada personaje.

![preview-2.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/18/preview-2.png)Ahora solo falta el bloque de CSS. En esta ocasión, vamos a ver cómo generar bucles y variables de CSS con _Stylus_.

```stylus
// Definimos una variable, parecida a un objeto javascript
// clave:valor
$heroesBg = {
  barbarian: #4e1c16,
  crusader: #795548,
  demon-hunter: #F44336,
  monk: #ff9800,
  necromancer: #00bcd4,
  witch-doctor: #8bc34a,
  wizard: #3f51b5
}
// Creamos las clases CSS necesarias
.progress-time-played

  h5.titlecolor #000

  .w-50pposition relative
    width 50pxbottom -2pxborder-bottom-left-radius 0border-bottom-right-radius 0


  // Bucle "for"// Itera sobre la variable $heroesBg// "hero" es la clave// "bgColor" es el valorfor hero, bgColor in $heroesBg
    .hero-bg-color-{hero}
      background-color bgColor
```

*   `{hero}` se va a sustituir por la clave en `$heroesBg`, que correspondería a: ‘barbarian’, ‘crusader’, ‘monk’, ‘necromancer’, etc.
*   `bgColor` es el valor, es decir, los colores que hemos definido: ‘#4e1c16’, ‘#795548’, etc.

Con este bucle (de tres líneas) estamos creando todas la clases CSS necesarias para cada tipo de personaje.

> 📗 Documentación de bucles con Stylus: [https://stylus-lang.com/docs/iteration.html](https://stylus-lang.com/docs/iteration.html)

Es decir, estamos generando este código (repetitivo) a través de una de las funcionalidades que nos proporciona Stylus:

```css
.progress-time-played .hero-bg-color-barbarian {
  background-color: #4e1c16;
}
.progress-time-played .hero-bg-color-crusader {
  background-color: #795548;
}
.progress-time-played .hero-bg-color-demon-hunter {
  background-color: #f44336;
}
.progress-time-played .hero-bg-color-monk {
  background-color: #ff9800;
}
.progress-time-played .hero-bg-color-necromancer {
  background-color: #00bcd4;
}
.progress-time-played .hero-bg-color-witch-doctor {
  background-color: #8bc34a;
}
.progress-time-played .hero-bg-color-wizard {
  background-color: #3f51b5;
}
```

Este es el componente de `TimePlayedHero.vue` completo:

```javascript
<template>
  <div class="progress-time-played">
    <div class="d-flex justify-content-between">
      <h5 class="mb-0 font-weight-lighter">
        {{heroTime.hero}}
      </h5>
      <span>
        <b-badge class="w-50p">
          {{ (heroTime.time \* 100).toFixed(2) }}
        </b-badge>
      </span>
    </div>
    <b-progress :max="1" height="14px" class="mb-3 rounded-0">
      <b-progress-bar :value="heroTime.time" :class="classHeroBg">
        {{ heroTime.hero }}
      </b-progress-bar>
    </b-progress>
  </div>
</template>

<script>
// Custom validator
import { HeroData } from '@/utils/typeValidation'

export default {
  name: 'TimePlayedHero',
  props: {
    heroTime: {
      type: HeroData,
      required: true
    }
  },
  computed: {
    classHeroBg () {
      return \`hero-bg-color-${this.heroTime.classSlug}\`
    }
  }
}
</script>

<style lang="stylus" scoped>
  $heroesBg = {
    barbarian: #4e1c16,
    crusader: #795548,
    demon-hunter: #F44336,
    monk: #ff9800,
    necromancer: #00bcd4,
    witch-doctor: #8bc34a,
    wizard: #3f51b5
  }

  .progress-time-played

    h5.title
      color #000

    .w-50p
      position relative
      width 50px
      bottom -2px
      border-bottom-left-radius 0
      border-bottom-right-radius 0

    for hero, bgColor in $heroesBg
      .hero-bg-color-{hero}
        background-color bgColor

</style>
```

Si todo va bien, se debería ver así:

![preview-3.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/18/preview-3.png)

### ¡Llegaste al final… De este capítulo!

No te preocupes, todavía no hemos terminado. Te espero en la siguiente lectura.


## 20. Cerrando vista Profile

Ya casi hemos terminado la vista de `Profile`. Para terminar el (gran) componente de `MainBlock` nos queda una última cosa y ya podríamos pasar al componente de los artesanos.

Lo que vamos a implementar ahora es que cuando hagamos click en un héroe, tanto si haces click en el rostro del hero en `TopHeroe` o en `HeroIco` (primera columna de la tabla), cambiemos a la ruta de detalle del héroe, es decir, a la vista `Hero`.

Para refrescar contenidos, estas son las rutas que habíamos definido:

```javascript
const routerOptions = \[
  { path: '/', name: 'Home' },
  { path: '/region/:region/profile/:battleTag', name: 'Profile' },
  { path: '/region/:region/profile/:battleTag/hero/:heroId', name: 'Hero' },
  { path: '/about', name: 'About' },
  { path: '/error', name: 'Error' },
  { path: '\*', redirect: { name: 'Home' } }
\]
```

Queremos que al hacer click en la “cara” de un _hero_, la app cambie de ruta y cargue la vista de _Hero_. Tenemos dos casos en los que controlar este comportamiento, por lo tanto, para reutilizar, vamos a crear un _mixin_ que, más tarde, lo usaremos en múltiples componentes.

Creamos nuestro mixin en la carpeta `/mixins`. Como se trata de una función (_method_) que va a navegar a la vista del _hero_, podemos llamarle `goToHero.js`. Va a tener este contenido:

```javascript
export default {
  methods: {
    /\*\*
     \* Go to hero Id
     \* @param heroId {String | Number}
     \*/
    goToHero (heroId) {
      // Sacar los datos de la URLconst { region, battleTag } = this.$route.params
      // Navegar a la ruta "Hero"this.$router.push({ name: 'Hero', params: { region, battleTag, heroId } })
    }
  }
}
```

Para poder usarlo, primero lo importamos y después lo declaramos en el componente. Vamos a usarlo en dos componentes:

### `TopHero.vue`

```diff
  <script>
+ import goToHero from '@/mixins/goToHero'

  import { formatNumber } from '@/filters/numeral'

  export default {
    name: 'TopHero',
+   mixins: \[goToHero\],
    filters: {
      formatNumber
  },
    props: {
      hero: {
        type: Object,
        required: true
    }
  },
    computed: {
      heroClass () {
        const gender = this.hero.gender === 0 ? 'male' : 'female'
        return \`hero-${this.hero.classSlug} ${gender}\`
      }
    }
  }
  </script>
- <div class="hero-portrait-wrapper mb-5 mb-sm-0">
+ <div class="hero-portrait-wrapper mb-5 mb-sm-0" @click="goToHero(hero.id)">
```

### `HeroIco.vue`

```diff
  <script>
+ import goToHero from '@/mixins/goToHero'

  export default {
    name: 'HeroIco',
+   mixins: \[goToHero\],
    props: {
      hero: {
        required: true,
        type: Object
      }
    },
    computed: {
      heroClassImg () {
        const gender = this.hero.gender === 1 ? 'female' : 'male'
        const hardcore = this.hero.hardcore ? 'border-danger' : ''
        return \`hero-${this.hero.classSlug} ${gender} ${hardcore}\`
      }
    }
  }
  </script>
- <div class="hero-ico d-flex align-items-center">
+ <div class="hero-ico d-flex align-items-center" @click="goToHero(hero.id)">
```

Si pruebas a hacer _click_ en estos elementos, debería funcionarte y cambiarte de vista.

![preview-1.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/19/preview-1.png)Sin embargo, tenemos un problema que tal vez hayas visto. La interfaz no es muy intuitiva, pues cuando pasamos el ratón por encima, el cursor no cambia a `pointer` 👆.

Podemos solucionarlo con una clase de CSS. Vamos a crear una clase CSS en nuestro fichero global de estilos CSS `/assets/css/main.styl`.

Al final de este fichero, agregamos lo siguiente:

```stylus
// ---------------------
// Utils
// ---------------------

.hover-cursor-pointer
  &:hover
    cursor pointer
```

Y aplicamos los cambios, es decir, agregamos la clase CSS `.hover-cursor-pointer` a los dos componentes:

*   `TopHero.vue`

```diff
\- <div class="hero-portrait-wrapper mb-5 mb-sm-0" @click="goToHero(hero.id)">
+ <div class="hero-portrait-wrapper mb-5 mb-sm-0 hover-cursor-pointer" @click="goToHero(hero.id)">
```

*   `HeroIco.vue`

```diff
\- <div class="hero-ico d-flex align-items-center" @click="goToHero(hero.id)">
+ <div class="hero-ico d-flex align-items-center hover-cursor-pointer" @click="goToHero(hero.id)">
```

¡Estupendo! El componente _MainBlock_ ya está listo (¡Por fin!). Podemos pasar a desarrollar el componente de los artesanos.

Y en cuanto terminemos con los artesanos podríamos dar por finalizada esta vista, la vista _Profile_.

ArtisansBlock
-------------

Este componente es también bastante sencillo: va a mostrar datos básicos de los tres artesanos (herrero, joyero y mística).

> 📗 Más info de artesanos y artesanía en Diablo III: [https://eu.diablo3.com/es/game/guide/items/crafting](https://eu.diablo3.com/es/game/guide/items/crafting)

Para empezar, vamos a crear todos los archivos necesarios. Dentro de la carpeta `/views/Profile`, al mismo nivel que `/MainBlock`, creamos una nueva llamada `/ArtisansBlock`. Dentro de esta creamos `Index.vue` y `ArtisanItem.vue`.

Ahora toca actualizar el componente vista `/views/Profile/Index.vue`, y agregarle el nuevo componente de _ArtisansBlock_ que acabamos de crear.

*   `/views/Profile/Index.vue`

En el bloque de JavaScript, importamos y habilitamos el componente (_as usual_):

```javascript
// /views/Profile/Index.vue
import setError from '@/mixins/setError'
import { getApiAccount } from '@/api/search'

import BaseLoading from '@/components/BaseLoading'
import MainBlock from './MainBlock/Index'
// Importar
import ArtisansBlock from './ArtisansBlock/Index'

export default {
  name: 'ProfileView',
  mixins: \[ setError \],
  components: {
    BaseLoading,
    ArtisansBlock,
    // Habilitar componente
    MainBlock
  }
  // ...
}
```

Usamos el componente. El HTML es el siguiente:

```html
 <template>
  <div class="profile-view">
    <BaseLoading v-if="isLoading"/>

    <template v-if="profileData !== null">
      <MainBlock :profile-data="profileData"/>
      <ArtisansBlock :artisans-data="artisansData" />
    </template>
  </div>
</template>
```

El componente está recibiendo `artisansData` como _prop_. Vamos a crear una _computed property_ que genere el objeto que necesitamos, los datos de los tres artesanos y en los dos modos (normal y hardcore):

```javascript
computed: {
  artisansData () {
    return {
      blacksmith: this.profileData.blacksmith,
      blacksmithHardcore: this.profileData.blacksmithHardcore,
      jeweler: this.profileData.jeweler,
      jewelerHardcore: this.profileData.jewelerHardcore,
      mystic: this.profileData.mystic,
      mysticHardcore: this.profileData.mysticHardcore
    }
  }
},
```

El código completo del componente `/Profile/Index.vue` es este:

```javascript
<template>
  <div class="profile-view">
    <BaseLoading v-if="isLoading"/>
    <template v-if="profileData !== null">
      <MainBlock :profile-data="profileData"/>
      <ArtisansBlock :artisans-data="artisansData" />
    </template>
  </div>
</template>

<script>
import setError from '@/mixins/setError'
import { getApiAccount } from '@/api/search'

import BaseLoading from '@/components/BaseLoading'
import MainBlock from './MainBlock/Index'
import ArtisansBlock from './ArtisansBlock/Index'

export default {
  name: 'ProfileView',
  mixins: \[
    setError
  \],
  components: {
    BaseLoading,
    MainBlock,
    ArtisansBlock
  },
  data () {
    return {
      isLoading: false,
      profileData: null
    }
  },
  computed: {
    artisansData () {
      return {
        blacksmith: this.profileData.blacksmith,
        blacksmithHardcore: this.profileData.blacksmithHardcore,
        jeweler: this.profileData.jeweler,
        jewelerHardcore: this.profileData.jewelerHardcore,
        mystic: this.profileData.mystic,
        mysticHardcore: this.profileData.mysticHardcore
      }
    }
  },
  created () {
    this.isLoading = trueconst { region, battleTag: account } = this.$route.params
    this.fetchData(region, account)
  },
  methods: {
    /\*\*
       \* Obtener los datos de la API
       \* Guardarlos en 'profileData'
       \* @param region {String}
       \* @param account {String}
       \*/
    fetchData (region, account) {
      getApiAccount({
        region,
        account
      })
        .then(({ data }) => {
          this.profileData = data
        })
        .catch((err) => {
          this.profileData = nullconst errObj = {
            routeParams: this.$route.params,
            message: err.message
          }
          if (err.response) {
            errObj.data = err.response.data
            errObj.status = err.response.status
          }
          this.setApiErr(errObj)
          this.$router.push({ name: 'Error' })
        })
        .finally(() => {
          this.isLoading = false
        })
    }
  }
}
</script>
```

Ahora, para probar que funcione, podemos darle este contenido al componente de `ArtisansBlock/Index.vue`

```javascript
<template>
  <div>
    <h1>Artesanos</h1>
  </div>
</template>

<script>
export default {
  name: 'ArtisansBlock'
}
</script>
```

Se debería ver así:

![preview-2.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/19/preview-2.png)

Ahora vamos a entrar al detalle en el componente de artesanos (`/ArtisansBlock/Index.vue`). Lo primero es definir las _props_ que va a recibir:

```javascript
<script>

import ArtisanItem from './ArtisanItem'

export default {
  name: 'ArtisansBlock',
  components: { ArtisanItem },
  props: {
    artisansData: {
      type: Object,
      required: true
    }
  }
}
</script>
```

Además, necesitamos crear un array que agrupe los datos de los artesanos. ¿Adivinas cómo lo vamos a hacer? Una _computed property_, ¡correcto!

```javascript
computed: {
  artisansInfo () {
    return \[
      {
        name: 'blacksmith',
        icon: 'hammer',
        emoji: '⚒',
        color: '#ffb74d',
        normal: this.artisansData.blacksmith,
        hardcore: this.artisansData.blacksmithHardcore
      },
      {
        name: 'jeweler',
        icon: 'gem',
        emoji: '💎',
        color: '#4dd0e1',
        normal: this.artisansData.jeweler,
        hardcore: this.artisansData.jewelerHardcore
      },
      {
        name: 'mystic',
        icon: 'hat-wizard',
        emoji: '🔮',
        color: '#ba68c8',
        normal: this.artisansData.mystic,
        hardcore: this.artisansData.mysticHardcore
      }
    \]
  }
}
```

> 😎 Truqui: si estás en MacOS, puedes pulsar la combinación de teclas `Control` + `Cmd` + `Tecla Espacio` para sacar un selector de emojis. 👇

![emojis.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/19/emojis.png)

> ¿Eres usuario de Windows? Con la combinación `Win` + `.` puedes hacer lo mismo 😉

Hemos creado un array con tres items. Cada item corresponde a un artesano. Cada uno tiene los dos datos de su tipo que ha recibido de las _props_.

Además, le hemos dado un color, un emoji y un ícono (_icon_, que hace referencia a FontAwesome, la librería de íconos que ya conoces)

Ahora el HTML:

```html
<template>
  <div class="artisan-list">
    <hr class="bg-light my-5">
    <h3 class="font-diablo mb-4">Artisans</h3>
    <b-row>
      <b-col lg="4" v-for="artisan in artisansInfo" :key="artisan.name">
        <ArtisanItem :artisan="artisan"/>
      </b-col>
    </b-row>
  </div>
</template>
```

El código completo de `/ArtisansBlock/Index.vue` es el siguiente:

```javascript
<template>
  <div class="artisan-list">
    <hr class="bg-light my-5">
    <h3 class="font-diablo mb-4">Artisans</h3>
    <b-row>
      <b-col lg="4" v-for="artisan in artisansInfo" :key="artisan.name">
        <ArtisanItem :artisan="artisan"/>
      </b-col>
    </b-row>
  </div>
</template>

<script>

import ArtisanItem from './ArtisanItem'

export default {
  name: 'ArtisansBlock',
  components: { ArtisanItem },
  props: {
    artisansData: {
      type: Object,
      required: true
    }
  },
  computed: {
    artisansInfo () {
      return \[
        {
          name: 'blacksmith',
          icon: 'hammer',
          emoji: '⚒️',
          color: '#ffb74d',
          normal: this.artisansData.blacksmith,
          hardcore: this.artisansData.blacksmithHardcore
        },
        {
          name: 'jeweler',
          icon: 'gem',
          emoji: '💎',
          color: '#4dd0e1',
          normal: this.artisansData.jeweler,
          hardcore: this.artisansData.jewelerHardcore
        },
        {
          name: 'mystic',
          icon: 'hat-wizard',
          emoji: '🔮',
          color: '#ba68c8',
          normal: this.artisansData.mystic,
          hardcore: this.artisansData.mysticHardcore
        }
      \]
    }
  }
}
</script>
```

El objeto que hemos generado con la computed property, que es el que se va a usar para iterar y generar los tres componentes de artesanos dinámicamente, tiene este contenido:

```javascript
\[
  {
    "name":"blacksmith",
    "icon":"hammer",
    "emoji":"⚒️",
    "color":"#ffb74d",
    "normal":{
      "slug":"blacksmith",
      "level":12
    },
    "hardcore":{
      "slug":"blacksmith",
      "level":0
    }
  },
  {
    "name":"jeweler",
    "icon":"gem",
    "emoji":"💎",
    "color":"#4dd0e1",
    "normal":{
      "slug":"jeweler",
      "level":12
    },
    "hardcore":{
      "slug":"jeweler",
      "level":0
    }
  },
  {
    "name":"mystic",
    "icon":"hat-wizard",
    "emoji":"🔮",
    "color":"#ba68c8",
    "normal":{
      "slug":"mystic",
      "level":12
    },
    "hardcore":{
      "slug":"mystic",
      "level":0
    }
  }
\]
```

ArtisanItem
-----------

Ahora nos queda terminar el componente `/ArtisansBlock/ArtisanItem.vue`. Vamos a dejar definidos los bloques de JavaScript y de CSS:

```javascript
<script>
export default {
  name: 'ArtisanItem',
  props: {
    artisan: {
      required: true,
      type: Object
    }
  }
}
</script>

<style lang="stylus" scoped>.artisan-item.iconwidth 80pxheight 80pxbackground-color #404850

</style>
```

El HTML lo explicamos un poquito más, aunque es muy simple, ya verás. ¿Recuerdas que hablamos de los emojis anteriormente? En esta ocasión le estamos pasando, a través de las _props_, ¡emojis al componente! 😏

Usarlo es tan sencillo como esto:

*   Opción uno

```html
<template>
  <div class="artisan-item d-flex bg-dark p-3 mb-2 rounded">

    <!-- Bloque Ícono / Emoji -->
    <div class="icon d-flex justify-content-center align-items-center rounded-circle mr-2">

      <!-- ¡Usar Emoji! -->
      <span class="display-4">{{ artisan.emoji}}</span>
    </div>

    <!-- Bloque Contenido -->
    <div class="content">
      <h5 class="font-weight-bold text-capitalize"> {{ artisan.name }} </h5>

      <!-- Si hay artesano normal -->
      <p v-if="artisan.normal.level" class="m-0 font-weight-normal">
        Level {{artisan.normal.level}} (normal)
      </p>

      <!-- Si hay artesano hardcore -->
      <p v-if="artisan.hardcore.level" class="mb-0 font-weight-normal text-muted">
        Level {{ artisan.hardcore.level }}
        <span class="text-danger">(hardcore)</span>
      </p>
    </div>
  </div>
</template>
```

Esto es así porque puedes jugar la historia en modo normal y no tener los artesanos del modo hardcore.

Si abres el navegador, tu app se debería ver maravillosamente así:

![preview-3.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/19/preview-3.png)Nos queda ver la segunda opción, usando iconos de FontAwesome.

*   Opción dos

```html
<!-- Bloque Ícono / Emoji -->
<div class="icon d-flex justify-content-center align-items-center rounded-circle mr-2">
  <!-- <span class="display-4">{{ artisan.emoji}}</span> -->
  <!-- Usar Ícono -->
  <font-awesome-icon :icon="artisan.icon" class="fa-2x" :style="{color: artisan.color}"/>
</div>
```

Con esta opción se vería así:

![preview-4.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/19/preview-4.png)¿Cuál te gusta más? ¿Cuál crees que es mejor? Deja tus comentarios y explica tu respuesta.

La decisión es tuya, tú eliges con que opción te quedas. En mi caso voy a usar la opción uno, la de los emojis.

¡Maravilloso! 🎉 Hemos terminado con la vista de _Profile_. Ahora debemos continuar con la vista de detalle del héroe, donde cargaremos los items y los skills de nuestro personaje.

Lo vemos en el siguiente tema.


## 21. Hero View

Ahora que tenemos la página de _Profile_ completa, y podemos navegar a la _Hero_, vamos a crear las funciones y componentes necesarios para esta vista.

> 👆 Esta lectura se corresponde con este _commit_: `35f0bacbfe195461a8dbacac01412779d98323fa`.

> Si no has seguido el proceso desde el principio (o si no te funciona), puedes ir a la carpeta del proyecto y escribir `git checkout 35f0bacbfe195461a8dbacac01412779d98323fa` en la terminal.

Antes de continuar, vamos a repasar la ruta que tenemos que gestionar en esta vista. Esta es la definición que tenemos en nuestro fichero de rutas:

```javascript
{ path: '/region/:region/profile/:battleTag/hero/:heroId', name: 'Hero' }
```

Entra en juego un nuevo parámetro, el `id` del héroe. Este parámetro lo vamos a usar para hacer una llamada a la API de items del héroe. Con esto vamos a obtener un listado de todos los objetos del personaje especificado.

Para esta vista vamos a hacer dos llamadas simultáneas a las APIs de Diablo. Aquí tienes todas las definiciones de las APIs y su documentación: [https://develop.battle.net/documentation/diablo-3/community-apis](https://develop.battle.net/documentation/diablo-3/community-apis)

Vamos a hacer uso de `getApiHero` y de `getApiDetailedHeroItems`. Con esto vamos a obtener todos los datos del héroe (stats, habilidades, etc.) y los objetos que tiene equipados en ese momento.

  

Tenemos que definir las dos nuevas funciones que hagan las llamadas a las APIs. Para ello, vamos a la carpeta `/api` y abrimos el fichero `search.js`. Agregamos estas 2 funciones:

```javascript
/\*\*
 \* Returns a single hero
 \* GET – /d3/profile/{account}/hero/{heroId}
 \* @param region {String}
 \* @param account {String}
 \* @param heroId {String}
 \* @returns {Promise}
 \*/
function getApiHero ({ region, account, heroId }) {
  const resource = \`d3/profile/${account}/hero/${heroId}\`const API_URL = \`${protocol}${region}${host}${resource}\`const locale = locales\[region\]

  const params = {
    'access_token': store.state.oauth.accessToken,
    locale
  }

  return get(API_URL, { params })
}

/\*\*
 \* Returns a list of items for the specified hero.
 \* GET – /d3/profile/{account}/hero/{heroId}/items
 \* @param region {String}
 \* @param account {String}
 \* @param heroId {String}
 \* @returns {Promise}
 \*/
function getApiDetailedHeroItems ({ region, account, heroId }) {
  const resource = \`d3/profile/${account}/hero/${heroId}/items\`const API_URL = \`${protocol}${region}${host}${resource}\`const locale = locales\[region\]

  const params = {
    access_token: store.state.oauth.accessToken,
    locale
  }

  return get(API_URL, { params })
}
```

No requieren mucha explicación, son similares a las que teníamos antes. Nos falta que puedan ser usadas desde fuera:

```javascript
export {
  getApiAccount,
  getApiHero,
  getApiDetailedHeroItems
}
```

Ya tenemos las dos funciones que llaman a las APIs preparadas, ahora solo queda llamarlas para gestionar la respuesta (promesa) desde la vista de _Hero_.

Volvamos a nuestra vista de _Hero_, al fichero `/views/Hero/Index.vue`. En el bloque de JavaScript, escribimos lo siguiente:

```javascript
<script>
import setError from '@/mixins/setError'
import BaseLoading from '@/components/BaseLoading'
import { getApiHero, getApiDetailedHeroItems } from '@/api/search'

export default {
  name: 'HeroView',
  mixins: \[setError\],
  components: { BaseLoading },
  data () {
    return {
      isLoadingHero: false,
      isLoadingItems: false,
      hero: null,
      items: null
    }
  },
  computed: {},
  created () {
    this.isLoadingHero = truethis.isLoadingItems = true
    const { region, battleTag: account, heroId } = this.$route.params

    getApiHero({ region, account, heroId })
      .then(({ data }) => {
        this.hero = data
      })
      .catch((err) => {
        this.hero = null
        const errObj = {
          routeParams: this.$route.params,
          message: err.message
        }
        if (err.response) {
          errObj.data = err.response.data
          errObj.status = err.response.status
        }
        this.setApiErr(errObj)
        this.$router.push({ name: 'Error' })
      })
      .finally(() => {
        this.isLoadingHero = false
      })

    getApiDetailedHeroItems({ region, account, heroId })
      .then(({ data }) => {
        this.items = data
      })
      .catch((err) => {
        this.items = nullconsole.log(err)
      })
      .finally(() => {
        this.isLoadingItems = false
      })
  }
}
</script>
```

Vayamos por partes. Lo primero, importar el mixin de error y el componente _Loading_. En caso de error, usaremos el mixin. Mientras hagamos las llamadas a las APIs, usaremos el componente _Loading_ hasta que se carguen los datos. Como tenemos dos llamadas de APIs (_hero_ & _items_) distintas vamos a tener dos componentes Loading, uno para cada llamada.

En la sección de variables, hemos definido la variable `hero` y la variable `items`. Las dos llamadas que vamos a hacer son independientes la una de la otra, por lo tanto se van a hacer en paralelo. Por eso hemos incluido otras dos variables de control para saber si están _loading_ o no:

```javascript
data () {
  return {
    isLoadingHero: false,
    isLoadingItems: false,
    hero: null,
    items: null
  }
}
```

Lo siguiente es hacer las llamadas a las dos APIs. Ponemos el _loading_ a `true`, llamamos a las APIs.

En caso de error hacemos uso del mixin y si todo va bien, guardamos el resultado en la variable correspondiente.

Por último, ponemos los _loading_ a `false`. Con esto vamos a poder controlar la visibilidad del componente de _Loading_.

Vemos que, efectivamente, se están haciendo las dos llamadas a las APIs:

![req-1.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/req-1.png)

![req-2.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/req-2.png)Ahora que ya tenemos los datos necesarios, vamos a empezar con los componentes de la vista. La estructura de componentes que vamos a seguir es esta:

> ![wireframe.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/wireframe.png)📗 Si nunca has jugado a Diablo III, te recomiendo que leas esta guía de controles de combate: [https://eu.diablo3.com/es/game/guide/gameplay/combat-skills](https://eu.diablo3.com/es/game/guide/gameplay/combat-skills)

Personalmente, creo que esta es la página más divertida de toda la app 🤙🤩🎉.

Vamos a pintar en pantalla:

*   Los atributos (fuerza, vida, inteligencia, etc.) del personaje, incluyendo sus recursos:
*   Recursos:
*   ![resources-preview.jpg](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/resources-preview.jpg)
*   Sus habilidades, tanto las activas como las pasivas (si las tiene, depende del nivel del personaje) y las runas (en caso de que tenga alguna, también dependen del nivel).
*   En esta parte veremos como crear componentes asíncronos (parecido a lo que hacíamos con las rutas y el _lazy load_, solo serán cargados cuando se requieran)
*   Los [objetos](https://eu.diablo3.com/es/item/), junto con las [joyas o gemas](https://us.diablo3.com/es/item/gem/) que puedan tener engarzadas.
*   Para los objetos, pintaremos una barra de color según la calidad de los objetos: [https://eu.diablo3.com/es/game/guide/items/equipment#item-quality](https://eu.diablo3.com/es/game/guide/items/equipment#item-quality)Color blanco: Normal
*   Color azul: Mágico
*   Color amarillo: Raro
*   Color verde: Conjunto (otorgan bonificación extra cuando llevas el _set_ completo)
*   Color naranja: Legendarios
*   Vamos a construir algo parecido a esto, que es como se ven los objetos del personaje (en PC, para consola cambia):
*   ![items.jpg](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/items.jpg)
*   Aquí hay objetos azules (mágicos) y amarillos (raros). Además vemos algunas gemas, por ejemplo, en el arma. Algo parecido a esto es lo que vamos a construir con los datos que nos devuelva la API de _items_.

Lo primero es crear la estructura de carpetas. ¡Empecemos!

Vamos a `/views/Hero` y creamos tres carpetas: `HeroAttributes`, `HeroItems` y `HeroSkills`. Creamos también el componente `HeroDetailHeader.vue`, que no va a estar agrupado en carpetas. Deberías tener una estructura como esta:

```markdown
📂 /Hero
├──📂 /HeroAttributes
├──📂 /HeroItems
├──📂 /HeroSkills
├── HeroDetailHeader.vue
└── Index.vue
```

Ahora, en nuestro componente `/Hero/Index.vue`, traemos el componente _HeroDetailHeader_:

```javascript
import HeroDetailHeader from './HeroDetailHeader'
```

Y lo damos de alta para poder usarlo:

```javascript
components: {
  BaseLoading,
  HeroDetailHeader
}
```

Usamos los componentes:

```javascript
<template>
  <div class="hero-view">
    <BaseLoading v-if="isLoadingHero"/>
    <HeroDetailHeader v-if="hero" :detail="detailHeader"/>
  </div>
</template>
```

> Por ahora, ignora los errores

Los datos que necesita el componente `HeroDetailHeader` son los siguientes: `name`, `class`, `gender`, `level`, `hardcore`, `seasonal`, `paragonLevel`, `alive` y `seasonCreated`. Todos estos datos los sacamos de la variable `this.hero`, que es donde guardamos los datos que hemos recuperado de la API.

Creamos una _computed_ llamada _detailHeader_ que nos retorne estos valores:

```javascript
computed: {
  detailHeader () {
    // Asignamos valores a través de const {
      name,
      // valor: aliasclass: classSlug,
      gender,
      level,
      hardcore,
      seasonal,
      paragonLevel,
      alive,
      seasonCreated
    } = this.hero

    return {
      name,
      classSlug,
      gender,
      level,
      hardcore,
      seasonal,
      paragonLevel,
      alive,
      seasonCreated
    }
  }
}
```

> 📗 Asignación por desestructuración: [https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Operadores/Destructuring_assignment](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Operadores/Destructuring_assignment)

Esto es lo que recibe el componente `HeroDetailHeader` en la _prop_ `detail`.

Ahora, abrimos el recién creado componente de `HeroDetailHeader` y le damos este contenido:

*   JavaScript

```javascript
<script>
import heroName from '@/mixins/heroName'

export default {
  name: 'HeroDetailHeader',
  mixins: \[heroName\],
  props: {
    detail: {
      type: Object,
      required: true
    }
  },
  computed: {
    heroClass () {
      const gender = this.detail.gender === 0 ? 'male' : 'female'return \`hero-${this.detail.classSlug} ${gender}\`
    }
  }
}
</script>
```

Con la _computed_ `heroClass` vamos a crear la clase de CSS necesaria para mostrar la cara correspondiente a nuestro personaje. Ya lo hemos usado con anterioridad; estamos usando las mismas clases para generar el avatar de nuestro héroe.

*   CSS:

```stylus
<style lang="stylus" scoped>
  .hero-detail-avatar
    width 138px
    height 105px
    background-size 280px

  .text-bone
    color #e8dcc2
</style>
```

*   HTML

```html
<template>
  <b-row class="hero-detail-header my-5">
    <b-col cols="12">

      <!-- Avatar -->
      <div class="d-flex justify-content-center mb-3">
        <div class="hero-detail-avatar" :class="heroClass"></div>
      </div>

      <div class="text-center">

        <!-- Nombre -->
        <h1 class="font-diablo text-truncate text-bone">{{ detail.name }}</h1>

        <div class="text-monospace">
          <small>
            <!-- Nivel -->
            <span>{{ detail.level }}</span>
              <!-- Nivel de Leyenda -->
              <span class="text-info" v-if="detail.paragonLevel">
                <span class="text-white"> · </span>
                ({{ detail.paragonLevel }})
              </span>
              <!-- Clase (A través del Mixin) -->
              <span> · {{classToName(detail.classSlug)}}</span>
              <!-- ¿Es de temporada? -->
              <span v-if="detail.seasonal" class="text-success"> · Seasonal </span>
              <!-- ¿Es hardcore? -->
            <span v-if="detail.hardcore" class="text-danger"> · Hardcore </span>
          </small>

          <div>
            <!-- En qué temporada ha sido creado el héroe -->
            <small class="text-muted">
              Season created:
            </small>
            <b-badge>{{ detail.seasonCreated }}</b-badge>
          </div>
        </div>

        <hr>

      </div>
    </b-col>
  </b-row>
</template>
```

En el HTML lo único que estamos haciendo es pintar, en el centro, los datos que recibimos del componente padre.

Si todo va bien, deberías ver algo como esto:

![preview-1.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/preview-1.png)Con esto hemos terminado el componente de _detailHeader_. A continuación vamos a trabajar con el componente de _Atributos_.

  

Volvemos al componente `/Hero/Index.vue` y ponemos lo siguiente en el HTML:

```html
<template>
  <div class="hero-view">
    <BaseLoading v-if="isLoadingHero"/>
    <HeroDetailHeader v-if="hero" :detail="detailHeader"/>

    <b-row>
      <!-- 12 columnas de 'xs' -> 'md', 8 columnas desde 'lg' hacia arriba  -->
      <!-- En 'lg' orden 2 -->
      <b-col md="12" lg="8" order-lg="2">
        <BaseLoading v-if="isLoadingItems"/>
      </b-col>

      <!-- 12 columnas de 'xs' -> 'md', 4 columnas desde 'lg' hacia arriba -->
      <!-- En 'lg' orden 1 -->
      <b-col md="12" lg="4" order-lg="1">
        <template v-if="hero">
          <HeroAttributes :attributes="detailStats"/>
          <HeroSkills :skills="hero.skills"/>
        </template>
      </b-col>

    </b-row>
  </div>
</template>
```

El componente de _DetailHeader_ está a 12 columnas (es decir el 100%). Para los demás componentes vamos a crear 2 columnas, como vimos en una imagen anteriormente. A la izquierda (atributos y habilidades) una columna de 4 unidades (sobre 12) y a la derecha (objetos) otra columna de 8 (sobre 12).

En tamaño de pantalla pequeño, lo primero que veremos es el bloque de 8 columnas, es decir, los objetos del personaje. Pero para pantallas grandes estamos alterando el orden de aparición a con la propiedad `order` de flexbox: [https://bootstrap-vue.js.org/docs/components/layout/#reordering](https://bootstrap-vue.js.org/docs/components/layout/#reordering).

Seguimos en `/Hero/Index.vue`. Importamos los componentes de atributos y habilidades y los registramos:

```javascript
import HeroAttributes from './HeroAttributes/Index'
import HeroItems from './HeroItems/Index'
components: {
  BaseLoading,
  HeroDetailHeader,
  HeroAttributes,
  HeroSkills
}
```

El componente de _Skills_ recibe el dato intacto de `hero.skills`. Para el componente de _Attributes_ necesitamos crear una _computed_ que haga alguna transformación. En este caso la transformación es muy simple. Cogemos los datos de `hero.stats` y le agregamos la clase (tipo) de personaje, que la necesitaremos en un componente hijo más adelante:

```javascript
computed: {
  detailStats () {
    // Devuelve el contenido de stats y agrega classSlugreturn { ...this.hero.stats, classSlug: this.hero.class }
  }
}
```

Para evitar errores en consola, vamos a crear también el fichero de _HeroSkills_. Dentro de la carpeta creamos su `Index.vue` correspondiente y le damos este contenido:

*   `/Hero/HeroSkills/Index.vue`

```javascript
<template>
  <h1>Skills</h1>
</template>

<script>
export default {
  name: 'HeroSkills'
}
</script>
```

Con esto ya podemos ir a pintar los componentes de atributos (y también de habilidades).

Dentro de `HeroAttributes` tendremos tres componentes: atributos primarios, atributos secundarios y recursos.

Vamos a crear el componente `Index.vue` en la carpeta `/HeroAttributes`, que está vacía. Además, dentro la misma, creamos otros dos componentes: `HeroAttributeList.vue` y `HeroResources.vue`

Abrimos `/HeroAttributes/Index.vue` y agregamos lo siguiente:

```javascript
<script>
// Importamos los componentes
import HeroAttributeList from './HeroAttributeList'
import HeroResources from './HeroResources'

// Definimos:
// Los atributos principales
const coreAttributes = \['strength', 'dexterity', 'vitality', 'intelligence'\]
// Los atributos secundarios
const secondaryAttributes = \['damage', 'toughness', 'healing'\]
// Los recursos
const resources = \['life', 'primaryResource', 'secondaryResource'\]

export default {
  name: 'HeroAttributes',
  components: { HeroResources, HeroAttributeList },
  // Definimos la propiedad
  props: {
    attributes: {
      type: Object,
      required: true
    }
  },
  computed: {
    // Creamos el objeto de atributos principales
    coreAttributes () {
      return coreAttributes.map(item => ({ name: item, val: this.attributes\[item\] }))
    },
    // Creamos el objeto de atributos principales
    secondaryAttributes () {
      return secondaryAttributes.map(item => ({ name: item, val: this.attributes\[item\] }))
    },
    resources () {
      // Creamos el objeto de recursos // Agregamos el tipo de personaje \`classSlug\` (necesario para los Sprites CSS)const data = {
        classSlug: this.attributes.classSlug,
        resources: {}
      }
      resources.forEach(item => {
        data.resources\[item\] = { name: item, val: this.attributes\[item\] }
      })
      return data
    }
  }
}
</script>
```

Los _arrays_ que acabamos de definir nos sirven para agrupar las claves que necesitamos en cada bloque.

Hemos agrupado en atributos principales (core), secundarios y recursos.

Todos los héroes tienen vida y recurso primario, pero solamente algunos tienen recurso secundario.

El HTML, que también es bastante sencillo, es el siguiente:

```html
<template>
<div class="h-attriubutes">
<!--Título-->
<h2 class="font-diablo">Attributes</h2>

    <hr class="bg-white">

    <div class="attributes">

      <!-- Atributos Principales-->
      <div class="core">
        <HeroAttributeList :attributes="coreAttributes"/>
      </div>

      <hr>

      <!-- Atributos Secundarios-->
      <div class="secondary">
        <HeroAttributeList :attributes="secondaryAttributes"/>
      </div>

    </div>

    <hr>

    <!-- Recursos -->
    <div class="resources">
      <HeroResources :resources="resources"/>
    </div>

  </div>
</template>
```

Para que te hagas la idea, un ejemplo de atributos primarios serían estos:

```javascript
\[
  {
    "name":"strength",
    "val":77
  },
  {
    "name":"dexterity",
    "val":77
  },
  {
    "name":"vitality",
    "val":4813
  },
  {
    "name":"intelligence",
    "val":9660
  }
\]
```

Hemos definido fuerza, destreza, vitalidad e inteligencia como atributos primarios. Solo nos quedaría mostrarlos por pantalla.

Un ejemplo de atributos secundarios serían estos:

```javascript
\[
  {
    "name":"damage",
    "val":986514
  },
  {
    "name":"toughness",
    "val":15263800
  },
  {
    "name":"healing",
    "val":1305200
  }
\]
```

Daño, dureza y curación serían nuestros atributos secundarios. Como ves, son idénticos a los primarios (a nivel de estructura de datos) y por lo tanto podemos utilizar el mismo componente para pintar los dos tipos de atributos. Simplemente les pasamos distinta información, pero mismo formato.

  

El componente `/Hero/HeroAttributes/HeroAttributeList.vue` es muy sencillo. Lo único que hace es mostrar el nombre del atributo (en color naranja) y su valor (en color blanco), pasado por el filtro de _numeral_ (que ya hemos usado anteriormente):

```javascript
<template>
  <ul class="list-unstyled">
    <!-- Itera -->
    <li v-for="attr in attributes" :key="attr.name" class="mb-1">
      <div class="d-flex justify-content-between">
        <!-- Nombre atributo -->
        <div class="pl-2 text-capitalize name-text">{{ attr.name }}</div>
        <!-- Valor formateado -->
        <div class="px-2 text-monospace">{{ attr.val | formatNumber }}</div>
      </div>
    </li>
  </ul>
</template>

<script>
import { formatNumber } from '@/filters/numeral'

export default {
  name: 'AttributeList',
  filters: { formatNumber },
  props: {
    attributes: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="stylus">ulli.name-textcolor #efb45dfont-weight 600
</style>
```

La app, actualmente, se ve así aunque tengamos errores:

![preview-2.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/preview-2.png)

Recursos
--------

Todas las clases tienen, además de los puntos de vida (_HP_), un recurso propio. Los recursos son: furia (bárbaro), cólera (cruzado), odio y disciplina (cazador de demonios), esencia (nigromante), espíritu (monje), maná (médico brujo) y poder arcano (mago).

En este bloque, vamos a pintar los puntos de vida que tiene el personaje y su recurso correspondiente. Tenemos cargados todos los recursos (incluyendo la vida) en una imagen, a modo de _sprite_. Esta es la imagen que usaremos:

![resources](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/resources.png)

Vamos a crear las clases CSS correspondientes para cada tipo de héroe.

¿Recuerdas en dónde tenemos los estilos globales de CSS? Si pensaste que era `/src/assets/css/main.styl`, has acertado. Abrimos el archivo y le agregamos lo siguiente:

```stylus
// ---------------------
// Resources
// ---------------------
.resource.resource-iconbackground-image url('../img/resources.png')
    width 50pxheight 50px

    &.resource-manabackground-position 0 -50px

    &.resource-furybackground-position: -50px 0

    &.resource-hatred-disciplinebackground-position: -100px 0px

    &.resource-spiritbackground-position: -50px -50px

    &.resource-arcane-powerbackground-position: -100px -50px

    &.resource-wrathbackground-position: 0px -100px

    &.resource-essencebackground-position: -50px -100px
```

Como has podido ver, es muy sencillo este bloque de CSS. Cargamos la imagen y nos vamos moviendo de 50 en 50 por la imagen 😃 según el recurso que seleccionemos.

Al igual que hemos hecho antes con los nombres de los héroes, vamos a crear un mixin para mostrar el nombre normalizado de los recursos. Para ello vamos a la carpeta donde están los mixins y creamos un nuevo fichero. De nombre le ponemos `resources.js` y el contenido va a ser el siguiente:

```javascript
const names = {
  BARBARIAN: 'barbarian',
  CRUSADER: 'crusader',
  MONK: 'monk',
  WIZARD: 'wizard',
  WITCHDOCTOR: 'witch-doctor',
  NECROMANCER: 'necromancer',
  DEMONHUNTER: 'demon-hunter'
}

const resourceClassName = {
  \[names.BARBARIAN\]: 'fury',
  \[names.CRUSADER\]: 'wrath',
  \[names.MONK\]: 'spirit',
  \[names.WIZARD\]: 'arcane-power',
  \[names.WITCHDOCTOR\]: 'mana',
  \[names.NECROMANCER\]: 'essence',
  \[names.DEMONHUNTER\]: 'hatred-discipline'
}

const resourceDisplayName = {
  \[names.BARBARIAN\]: 'Fury',
  \[names.CRUSADER\]: 'Wrath',
  \[names.MONK\]: 'Spirit',
  \[names.WIZARD\]: 'Arcane Power',
  \[names.WITCHDOCTOR\]: 'Mana',
  \[names.NECROMANCER\]: 'Essence',
  \[names.DEMONHUNTER\]: 'Hatred / Discipline'
}

export default {
  methods: {
    /\*\*
     \* Get the name of the primary resource by class
     \* @param classSlug {String}
     \* @returns {String}
     \*/
    resourceClassName (classSlug) {
      return resourceClassName\[classSlug\]
    },
    /\*\*
     \* Resource Normalized name
     \* @param classSlug {String}
     \* @returns {String}
     \*/
    resourceDisplayName (classSlug) {
      return resourceDisplayName\[classSlug\]
    }
  }
}
```

Regresamos al componente de recursos, abrimos el archivo `/HeroAttributes/HeroResources.vue` y ponemos lo siguiente:

```javascript
<template>
  <div class="resource-wrapper">
    <div class="resource">
      <div class="d-flex justify-content-start align-items-center">
        <!-- Imagen Vida -->
        <div class="resource-icon resource-life"/>
          <!-- Nombre -->
          <div class="ml-3 text-uppercase name-text">
            <span>{{ resources.resources.life.name }}</span>
          </div>
          <!-- Valor -->
          <div class="ml-3">
            <span class="text-monospace"> {{ resources.resources.life.val | formatNumber }} </span>
          </div>
        </div>

      </div>

      <hr>

      <div class="resource">
        <div class="d-flex justify-content-start align-items-center">
          <!-- Imagen Recurso -->
          <div class="resource-icon" :class="classResourceName"/>
            <!-- Nombre -->
            <div class="ml-3 text-uppercase name-text" :class="'resource-name-' + resources.classSlug">
              <span>{{ displayResourceName }}</span>
            </div>
            <div class="ml-3">
            <!-- Valor -->
            <span class="text-monospace">
              {{ resources.resources.primaryResource.val | formatNumber }}
              <template v-if="hasSecondaryResource">
                <!-- Valor recurso secundario -->
                <span class="mx-0 text-muted">/</span>
                <span> {{ resources.resources.secondaryResource.val | formatNumber }} </span>
              </template>
            </span>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
import resources from '@/mixins/resources'
import { formatNumber } from '@/filters/numeral'

export default {
  name: 'HeroResources',
  mixins: \[resources\],
  filters: {
    formatNumber
  },
  props: {
    resources: {
      required: true,
      type: Object
    }
  },
  computed: {
    classResourceName () {
      return \`resource-${this.resourceClassName(this.resources.classSlug)}\`
    },
    displayResourceName () {
      return this.resourceDisplayName(this.resources.classSlug)
    },
    // Solo demon-hunter tiene recurso secundario
    hasSecondaryResource () {
      return this.resources.classSlug === 'demon-hunter'
    }
  }
}
</script>

<style lang="stylus">.resource.name-textcolor #efb45d

    .resource-name-demon-hunterwidth auto

  @media (min-width: 992px)
    .resource
      .resource-name-demon-hunter
        width 100px
</style>
```

Recibimos datos a través de una _prop_ y los mostramos, eso es todo lo que hacemos aquí. Con esto funcionando, la app debería verse así:

![preview-3](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/preview-3.png)

Ahí vemos la _esencia_ , que es el recurso del nigromante. Si probamos a cambiar de clase, vemos que se carga el recurso correspondiente. En los ejemplos de abajo vemos la _ira_ del cruzado y el _odio / disciplina_ del cazador de demonios.

![cruzado](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/cruzado.png)

![demon-hunter](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/demon-hunter.png)

> ✏️ Ves al navegador y prueba a cambiar los estilos CSS de la imagen de los recursos.

> ¿Qué pasa si pones `background-position: -25px 75px;` al elemento un recurso cualquiera? Deja tus respuestas en el sistema de comentarios

Con esto ya hemos terminado el bloque de atributos y recursos del personaje. Vamos a seguir con la siguiente parte, que es la de habilidades.

Skills
------

Cada personaje puede tener hasta 6 habilidades activas, 2 de ratón (botón primario y secundario) y 4 de teclado. Las habilidades se van desbloqueando según el nivel, no tienes todas las habilidades disponibles desde el inicio.

A su vez, las habilidades activas pueden tener modificadores o _runas_ de habilidad que mejoren dicha habilidad. Al igual que con las habilidades, las runas se van desbloqueando cuando vas subiendo de nivel.

Todo esto corresponde a las habilidades activas. Existen otro grupo de habilidades, las habilidades pasivas. Como las demás, se van ganando al subir de nivel.

Aquí puedes ver, a modo ejemplo, el progreso de niveles y habilidades del nigromante: [https://eu.diablo3.com/es/class/necromancer/progression](https://eu.diablo3.com/es/class/necromancer/progression)

Una vez entendido esto, podemos ir a crear los componentes necesarios. Vamos a tener componentes agrupados en habilidades activas y habilidades pasivas.

¡Hagámoslo! Dentro de nuestra carpeta de `/Hero/HeroSkills` creamos los siguientes archivos: `ActiveSkills.vue`, `ActiveSkill.vue`, `PassiveSkills.vue` y `PassiveSkill.vue`.

El contenido de `/Hero/HeroSkills/Index.vue` va a ser el siguiente (de momento):

```javascript
<template>
  <div class="skills-wrapper mt-5">
    <h2 class="font-diablo">Skills</h2>
    <hr class="bg-white">

    <ActiveSkills :skills="skills.active"/>
      <hr>
      <PassiveSkills :skills="skills.passive"/>
  </div>
</template>

<script>
import ActiveSkills from './ActiveSkills'
import PassiveSkills from './PassiveSkills'

export default {
  name: 'HeroSkills',
  components: {
    ActiveSkills,
    PassiveSkills
  },
  props: {
    skills: {
      required: true,
      type: Object
    }
  }
}
</script>
```

Estamos cargando los _skills_ activos y los pasivos, sin más.

Vamos a editar los componentes de las habilidades, empezando por el habiliades activas.

Como tenemos un array de _skills_ lo que vamos a hacer es iterar, con `v-for`, para utilizar el componente de habilidad individual, `ActiveSkill`.

*   `ActiveSkills.vue`:

```javascript
<template>
  <div class="active-skills">
    <h4 class="my-5">Active</h4>

    <div class="skills">
      <b-row>
        <b-col v-for="(skill, idx) in skills" :key="idx" cols="6" lg="12">
          <ActiveSkill :skill="skill.skill" :rune="skill.rune" :slot-num="idx+1"/>
        </b-col>
      </b-row>
    </div>

  </div>
</template>

<script>
import ActiveSkill from './ActiveSkill'

export default {
  name: 'ActiveSkills',
  components: { ActiveSkill },
  props: {
    skills: {
      type: Array,
      required: true
    }
  }
}
</script>
```

Antes de cargar el listado de habilidades activas, necesitamos editar el fichero global de CSS, que es dónde estamos guardando los estilos para los Sprites de imágenes.

Para identificar qué habilidad estamos mostrando, vamos a agregar estas líneas de código en `/assets/css/main.styl`:

```stylus
// ---------------------
// Active Skills
// ---------------------
.active-skills.skills.slot
  display block
  width 22px
  height 22px
  background url("../img/skill-overlays.png") 0 0
  position absolute
  top -5px
  left 5px

  &.slot-1
    background-position: 0 -1px

  &.slot-2
    background-position: -21px -1px

  &.slot-3
    background-position: 0 -23px

  &.slot-4
    background-position: -23px -23px

  &.slot-5
    background-position: 0 -46px

  &.slot-6
    background-position: -23px -46px
```

Con `slot` nos estamos refiriendo a qué habilidad es, siendo `slot-1` el boton princila del ratón y `slot-2` el botón secundario. Aguanta un poco, que con un ejemplo lo verás mejor.

*   `ActiveSkill.vue`:

```javascript
<template>
  <div class="d-flex align-items-center mb-3">
    <div class="mr-2">
      <!-- Slot (identificador de skill) -->
      <span class="slot" :class="slotClass"/>
      <!-- La imagen · Skill URL -->
      <img :src="skillUrl" :alt="skill.name">
    </div>

    <div>
      <!-- Nombre de la habilidad -->
      <p class="skill-name m-0" :title="skill.description">
        {{ skill.name }}
      </p>
      <!-- Runa (si tiene) -->
      <small v-if="rune" class="rune-name text-muted" :title="rune.description">
        {{ rune.name }}
      </small>
    </div>

  </div>
</template>

<script>
export default {
  name: 'ActiveSkill',
  props: {
    skill: {
      required: true,
      type: Object
    },
    rune: {
      required: false,
      type: Object
    },
    slotNum: {
      required: true,
      type: Number || String
    }
  },
  computed: {
    skillUrl () {
      // Posibles tamaños (px)const sizes = \[21, 42, 64\]
      // API URL para imágenesconst host = \`http://media.blizzard.com/d3/icons/skills/${sizes\[1\]}/\`// Ejemplo:// http://media.blizzard.com/d3/icons/skills/42/p6_necro_bonespikes.pngreturn \`${host}${this.skill.icon}.png\`
    },
    // Clase CSS para los slots
    slotClass () {
      return \`slot-${this.slotNum}\`
    }
  }
}
</script>
```

### Skill Images

En las propiedades estamos recibiendo la _habilidad_, la _runa_ en caso de que la tenga (si no llega, no la mostramos) y el número de _slot_, que corresponde con las clases de CSS que hemos creado recientemente.

> 📗 Documentación para obtener las URLs de las habilidades y de los objetos de Diablo III: [https://develop.battle.net/documentation/diablo-3/community-apis](https://develop.battle.net/documentation/diablo-3/community-apis)

Hacemos la composición de la URL, tenemos la base de la URL, el tipo (skills), el tamaño (42) y el nombre del icon (que nos lo da la API).

Un ejemplo sería este: [http://media.blizzard.com/d3/icons/skills/42/p6_necro_bonespikes.png](http://media.blizzard.com/d3/icons/skills/42/p6_necro_bonespikes.png)

Que renderiza esta imagen:

![p6_necro_bonespikes.png](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/p6_necro_bonespikes.png)

Gracias al atributo `title`, si pasamos el ratón por encima del elemento, podemos ver una breve descripción.

Perfecto, ya tenemos las habilidaes activas de nuestro personaje cargadas, que se ven así en nuestra app:

![preview-4](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/preview-4.png)

Hora de cargar las habilidades pasivas, que son casi lo mismo que las activas, pero más sencillas. Solo imagen y nombre de la habilidad.

*   `PassiveSkills.vue`:

```javascript
<template>
  <div class="passive-skills">
    <h4 class="my-5">
      Passive
    </h4>
    <div class="skills">
      <b-row>
        <b-col v-for="(skill, idx) in skills" :key="idx" cols="6" lg="12">
          <PassiveSkill :skill="skill.skill"/>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
import PassiveSkill from './PassiveSkill'

export default {
  name: 'PassiveSkills',
  components: { PassiveSkill },
  props: {
    skills: {
      type: Array,
      required: true
    }
  }
}
</script>
```

*   `PassiveSkill.vue`:

```javascript
<template>
  <div class="d-flex align-items-center mb-3">
    <div class="mr-2">
      <!-- Imagen Habilidad Pasiva -->
      <img :src="skillUrl" :alt="skill.name">
    </div>

    <div>
      <!-- Nombre -->
      <p class="skill-name m-0" :title="skill.description">
        {{ skill.name }}
      </p>
    </div>

  </div>
</template>

<script>
export default {
  name: 'PassiveSkill',
  props: {
    skill: {
      required: true,
      type: Object
    }
  },
  computed: {
    skillUrl () {
      const sizes = {
        21: 21,
        42: 42,
        64: 64
      }
      const host = \`http://media.blizzard.com/d3/icons/skills/${sizes\[42\]}/\`return \`${host}${this.skill.icon}.png\`
    }
  }
}
</script>
```

Bien, ya tenemos las habilidades activas y las pasivas funcionando. Se deberían ver así:

![preview-5](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/20/preview-5.png)

Puede darse el caso en el que si estás usando el perfil de un personaje que no está al nivel máximo, no tengas todas las habilidades (activas, pasivas y runas) desbloqueadas y por lo tanto veas menos habilidades.

Con esto hemos terminado la parte de _skills_… en modo normal. En el siguiente bloque vamos a ver cómo refactorizar el bloque de habilidades y crear componentes asíncronos dinámicos 🤘.


## 22. Componentes asíncronos

A medida que nuestra aplicación va creciendo, vamos buscando formas de mejorar su rendimiento. Tiene mucho sentido hacer _Lazy Loading_ (o carga diferida) en las rutas, ya que solo abres una ruta por vez. Por lo tanto, no hace falta cargar todo el contenido de las rutas a la vez.

Por si acaso no tenías muy claro el concepto de _Lazy Loading_, podríamos decir es un patrón de diseño que consiste en retrasar la carga o inicialización de un objeto hasta el momento de su utilización.

Esta técnica ya la hemos utilizado con las rutas de nuestra app, en el `router.js`. Ahora vamos a ver cómo hacerlo con los componentes.

Actualmente, nuestros componentes de _skills_ activas y pasivas se cargan de forma normal (síncrona). Lo que vamos a hacer ahora es cargar ambos componentes (habilidades activas y habilidades pasivas) con _lazy loading_, pero solo mostraremos uno, y podremos cambiar entre las activas y las pasivas con unos botones.

Por defecto, estaremos mostrando las habilidades activas, por lo que dicho componente se cargará inmediatamente cuando cargue la vista de `/Hero`. Sin embargo, el componente de habilidades pasivas no será cargado hasta que pulsemos el botón de `Passive`, que aún no hemos creado.

> 📗 Enlace a la documentación de Vue.js y componentes asíncronos: [https://es.vuejs.org/v2/guide/components-dynamic-async.html#Componentes-asincronos](https://es.vuejs.org/v2/guide/components-dynamic-async.html#Componentes-asincronos)

Hacer esto en Vue es muy fácil, gracias a los _bundlers_ (como Webpack) que se encargan de separar el código y hacer que se utilice solo cuando es requerido.

Con un ejemplo en el código lo entenderás mejor.

El primer cambio que vamos a hacer es cargar los componentes de manera asíncrona. En vez de hacer el _import_ que hacemos siempre vamos a hacer lo siguiente:

// /Hero/HeroSkills/Index.vue

```javascript
// import ActiveSkills from './ActiveSkills'
// import PassiveSkills from './PassiveSkills'

export default {
  name: 'HeroSkills',
  components: {
    ActiveSkills: () => import('./ActiveSkills'),
    PassiveSkills: () => import('./PassiveSkills')
  },
  // ...
}
```

EL _import_ habitual lo comentamos o lo borramos, porque ya no lo vamos a usar. Con esto ya estamos cargando nuestros componentes con _lazy loading_. Míralo aquí:

![pv-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/21/pv-1.png)

Los archivos `18.js` y `19.js` son nuestros 2 componentes de habilidades. Esto lo sé porque los he abierto y he revisado su contenido, pero esta no es la forma adecuada. ¿Recuerdas como lo hicimos en las rutas 🤔?

En el `import` pusimos un comentario y esto al generar el _chunk_ de código iba a tener el nombre que nosotros le asignamos.

En código se vería así:

```javascript
export default {
  components: {
    ActiveSkills: () => import(/\* webpackChunkName: "ActiveSkills" \*/'./ActiveSkills'),
    PassiveSkills: () => import(/\* webpackChunkName: "PassiveSkills" \*/'./PassiveSkills')
  }
}
```

Si volvemos a la consola del navegador, ahora vemos esto:

![pv-2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/21/pv-2.png)

Mucho mejor así 👌.

Código completo del fichero `/Hero/HeroSkills/Index.vue`:

```javascript
<template>
  <div class="skills-wrapper mt-5">
    <h2 class="font-diablo">Skills</h2>
    <hr class="bg-white">

    <ActiveSkills :skills="skills.active"/>
    <hr>
    <PassiveSkills :skills="skills.passive"/>

  </div>
</template>

<script>
export default {
  name: 'HeroSkills',
  components: {
    ActiveSkills: () => import(/\* webpackChunkName: "ActiveSkills" \*/ './ActiveSkills'),
    PassiveSkills: () => import(/\* webpackChunkName: "PassiveSkills" \*/ './PassiveSkills')
  },
  props: {
    skills: {
      required: true,
      type: Object
    }
  }
}
</script>
```

Hasta ahora lo único que hemos hecho es _code splitting_, es decir, trocear el código (en realidad lo hizo Webpack por nosotros: [https://webpack.js.org/guides/code-splitting/](https://webpack.js.org/guides/code-splitting/)). Y esto es así porque estamos mostrando los 2 componentes a la vez, por lo tanto se cargan los 2 a la vez y no hay _lazy load_.

Lo que puede ser mas interesante es tener 2 botones, cada uno asociado a un componente, y por defecto solo cargar las habilidades activas. Al pulsar el botón de las habilidades pasivas, cargar el contenido de este otro componente, es decir, hacer _lazy loading_ (ahora sí). Vamos a ello:

Componentes dinámicos
=====================

Antes de poder hacer esto, necesitamos revisar los componentes dinámicos: [https://es.vuejs.org/v2/guide/components.html#Componentes-dinamicos](https://es.vuejs.org/v2/guide/components.html#Componentes-dinamicos)

En resumen, tenemos un nuevo _tag_ con la propiedad `is`, que recibe como valor el nombre del componente que queremos cargar.

Podemos cargar varios componentes, por ejemplo:

```javascript
import ComponentA from './ComponentA'
import ComponentB from './ComponentB'
```

Y luego usarlos así:

```html
<component is="ComponentA"></component>
<component is="ComponentB"></component>
```

O así:

```javascript
<component is="selectedComponent"></component>
computed: {
  selectedComponent () {
    return this.value === 'B' ? ComponentB : ComponentA
  }
}
```

Si `value` es igual a `B`, cargamos el componente B, en caso contrario, cargamos el componente A.

Esto es lo que vamos a hacer con los componentes de habilidades, usar el tag `<component>` y cargar el componente que necesitemos con `is`. ¡Vamos a ello!

Componentes dinámicos asíncronos 🤯
===================================

Empecemos cambiando el HTML de nuestro componente `/Hero/HeroSkills/Index.vue`:

```html
<template>
  <div class="skills-wrapper mt-5">
  <h2 class="font-diablo">Skills</h2>
  <hr class="bg-white">

  <b-nav pills small>
    <b-nav-item :active="!isPassiveSkillsActive" @click="changeComponent('ActiveSkills')">
      Active
    </b-nav-item>
    <b-nav-item :active="isPassiveSkillsActive" @click="changeComponent('PassiveSkills')">
      Passive
    </b-nav-item>
  </b-nav>

  <component :is="activeComponent" :skills="componentProps"/>

  <!--
  <ActiveSkills :skills="skills.active"/>
  <hr>
  <PassiveSkills :skills="skills.passive"/>
  -->

  </div>
</template>
```

Vamos a crear una nueva variable en el `data` para controlar que componente está activo y por ende, cuál mostrar:

```javascript
data () {
  return {
    activeComponent: 'ActiveSkills'
  }
}
```

Y unas _computed properties_:

```javascript
computed: {
  /\*\*
   \* Dinamyc props for async dynamic components
   \* @returns {String}
   \*/// Con esto estamos generando "props" dinámicas// Si el componente es ActiveSkills pasa como props las activas, si no, las pasivas
  componentProps () {
    return this.activeComponent === 'ActiveSkills' ? this.skills.active : this.skills.passive
  },
  // Nos dice si el componente "HabilidadesPasivas" está activo o no
  isPassiveSkillsActive () {
    return this.activeComponent === 'PassiveSkills'
  }
}
```

En esta parte hacemos un breve hincapié.

Cerramos los ojos y pensamos “_¡Qué maravillosas que son las_ **_computed properties_**_!_” Esta es la potencia de las propiedades computadas.

La regla que yo sigo para saber cuando las tienes que usar es: “**Siempre**”. Abusa de las computadas y todo estará bien.

Hemos generado, a través de `componentProps` una _prop_ (que pasamos de comp. padre a hijo) dinámica. Esto es necesario porque tenemos componentes dinámicos, por lo tanto las props no pueden ser estáticas como haciamos antes.

Ya por último, tenemos el método que hace que se cargue un componente u otro, cuando hacemos _click_:

```javascript
methods: {
  changeComponent (component) {
    this.activeComponent = component
  }
}
```

El código completo se vería así:

```javascript
<template>
  <div class="skills-wrapper mt-5">
    <h2 class="font-diablo">Skills</h2>
    <hr class="bg-white">

    <b-nav pills small>
      <b-nav-item :active="!isPassiveSkillsActive" @click="changeComponent('ActiveSkills')">
        Active
      </b-nav-item>
      <b-nav-item :active="isPassiveSkillsActive" @click="changeComponent('PassiveSkills')">
        Passive
      </b-nav-item>
    </b-nav>

    <component :is="activeComponent" :skills="componentProps"/>

  </div>
</template>

<script>

export default {
  name: 'HeroSkills',
  components: {
    // Dynamic Components
    ActiveSkills: () => import(/\* webpackChunkName: "ActiveSkills" \*/'./ActiveSkills'),
    PassiveSkills: () => import(/\* webpackChunkName: "PassiveSkills" \*/'./PassiveSkills')
  },
  props: {
    skills: {
      required: true,
      type: Object
    }
  },
  data () {
    return {
      activeComponent: 'ActiveSkills'
    }
  },
  computed: {
    /\*\*
       \* Dinamyc props for dynamic components
       \* @returns {String}
       \*/
    componentProps () {
      return this.activeComponent === 'ActiveSkills' ? this.skills.active : this.skills.passive
    },
    isPassiveSkillsActive () {
      return this.activeComponent === 'PassiveSkills'
    }
  },
  methods: {
    changeComponent (component) {
      this.activeComponent = component
    }
  }
}
</script>
```

Este es el aspecto que tiene ahora nuestra app:

![pv-3](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/21/pv-3.png)

Se ve en 2 columnas porque la app es responsive y así es como se ve en pantallas pequeñas. Ahora bien, si nos fijamos en la pestaña network de las herramientas para desarrolladores, vemos que solo ha cargado el componente de _ActiveSkills_. ¡Esto es genial!

Sin cerrar la pestaña de `Network` del navegador, hacemos click en el botón de _Passive_, veremos como se carga el otro componente.

![pv-4](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/21/pv-4.png)

Hemos hecho _lazy load_ de componentes con tan solo refactorizando un par de líneas. Ahora ya puedes aplicar este método a todos tus proyectos 👏.

Keep Alive
==========

Sin embargo, tengo una (no tan buena) noticia que darte. Al hacer este cambio de _pestañas_, es decir, el cambio del componente _ActiveSkills_ a _PassiveSkills_ (o viceversa) múltiples veces, estamos haciendo otra vez peticiones de carga de imágenes. Mira lo que ha pasado al hacer el flujo Activas > Pasivas > Activas:

![pv-5](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/21/pv-5.png)

Hemos cargado cada imagen varias veces, en este caso 3 veces. Cada vez que cambiamos de “pestaña”, el componente se destruye, por lo tanto las imágenes de las habilidades se tiene que volver a cargar para ser renderizadas.

Esto no es una buena práctica, pues estaríamos haciendo peticiones innecesarias para cargar contenido que antes teníamos cargado. ¡Esto no pasaba cuando teníamos componentes síncronos!

Para ver cómo se crea y se destruye el componente con esta técnica de _lazy loading_, podemos poner el código que tienes a continuación en el componente de `/HeroSkills/PassiveSkills.vue`:

```javascript
created () {
  console.log('CREADO!')
},
destroyed () {
  console.log('DESTRUIDO!')
}
```

Ahora, prueba de nuevo a alternar entre componentes de habilidades activas y pasivas. Puedes ver como salen los _logs_ en la consola del navegador.

![pv-6](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/21/pv-6.png)

_No problem_. Vue tiene una solución para esto y se llama **Keep Alive**. Es una de las _features_ que más me gusta, para lo complejo que podría llegar ser.

> 📗 Documentación oficial de Keep Alive: [https://es.vuejs.org/v2/guide/components-dynamic-async.html#keep-alive-con-Componentes-Dinamicos](https://es.vuejs.org/v2/guide/components-dynamic-async.html#keep-alive-con-Componentes-Dinamicos) & [https://es.vuejs.org/v2/api/#keep-alive](https://es.vuejs.org/v2/api/#keep-alive)

Esta definición, sacada de la documentación oficial, me parece que es perfecta:

> _Keep Alive_ se utiliza principalmente para preservar el estado de los componentes o evitar la re-renderización.

Justo lo que nosotros queremos, que no se carguen de nuevo, en este caso, las imágenes.

Usarlo es tan fácil como envolver el componente que queremos mantener _vivo_ con la etiqueta `<keep-alive>`:

```html
<keep-alive>
  <component :is="activeComponent" :skills="componentProps"/>
</keep-alive>
```

Por lo tanto, usamos `keep-alive` en nuestro componente y probamos. El HTML del `/Hero/HeroSkills/Index.vue` debería estar así:

```html
<template>
  <div class="skills-wrapper mt-5">
  <h2 class="font-diablo">Skills</h2>
  <hr class="bg-white">

    <b-nav pills small>
      <b-nav-item :active="!isPassiveSkillsActive" @click="changeComponent('ActiveSkills')">
        Active
      </b-nav-item>
      <b-nav-item :active="isPassiveSkillsActive" @click="changeComponent('PassiveSkills')">
        Passive
      </b-nav-item>
    </b-nav>

    <keep-alive>
      <component :is="activeComponent" :skills="componentProps"/>
    </keep-alive>

  </div>
</template>
```

En este tema hemos visto, Componentes Asíncronos, Componentes Dinámicos, Componentes Asíncronos Dinámicos con _Props_ Dinámicas y _Keep Alive_. 😍

En el siguiente, vamos a terminar con esta vista, donde cargaremos los items (⚔️) de nuestro personaje.


## 23. Objetos del Héroe

Actualmente nuestra vista de `Hero` tiene un bloque de cabecera, otro de atributos (stats) del personaje y el último, con las habilidades.

Lo siguiente que vamos a hacer es mostrar los _items_ del personaje. La API de _items_ nos devuelve un objeto que tiene este formato:

```javascript
{
  "mainHand": {
    "id":"P6_Unique_Scythe1H_04",
    "name":"Jesseth Skullscythe",
    "icon":"p6_unique_scythe1h_04_demonhunter_male",
    "displayColor":"green",
    "tooltipParams":"/item/jesseth-skullscythe-P6_Unique_Scythe1H_04",
    "requiredLevel":70,
    "itemLevel":1,
    "stackSizeMax":0,
    "accountBound":true,
    "flavorText":"This assembly of sharpened bones will make you a true artist in combat.",
    "typeName":"Ancient Set Scythe",
    "type": {
      "twoHanded":false,
      "id":"scythe1h"
    },
    "armor":0,
    "damage":"1682-2259 Damage\\n1.38 Attacks per Second",
    "dps":"2,715.3",
    "attacksPerSecond":1.3779999,
    "minDamage":1682,
    "maxDamage":2259,
    "slots":"mainHand",
    "attributes": {
      "primary": \[
        "+1433-1798 Damage",
        "+998 Intelligence",
        "+899 Vitality",
        "Increases Attack Speed by 6%"
      \],
      "secondary": \[
        "+19 Maximum Essence",
        "Monster kills grant +254 experience."
      \]
    },
    "openSockets":0,
    "gems": \[
      {
        "item": {
          "id":"x1_Emerald_10",
          "slug":"flawless-royal-emerald",
          "name":"Flawless Royal Emerald",
          "icon":"x1_emerald_10_demonhunter_male",
          "path":"item/flawless-royal-emerald-x1_Emerald_10"
        },
        "attributes": \[
          "Critical Hit Damage Increased by 130.0%"
        \],
        "isGem":true,
        "isJewel":false
      }
    \],
    "seasonRequiredToDrop":-1,
    "isSeasonRequiredToDrop":false
  }
}
```

Este modelo de datos corresponde al _slot_ del arma (mano principal o _main hand_). Tenemos 13 tipos de objetos (_items_) distintos, que son los siguientes: cabeza (_head_), cuello (_neck_), pecho (_torso_), hombros (_shoulders_), piernas (_legs_), cintura (_waist_), manos (_hands_), brazales (_bracers_), pies (_feet_), dedo izquierdo (_leftFinger_), dedo derecho (_rightFinger_), mano dominante (_mainHand_) y mano secundaria (_offHand_).

> 📗 Aquí tienes más información acerca de los objetos del juego: [https://eu.diablo3.com/es/item/](https://eu.diablo3.com/es/item/)

Según la documentación, para obtener la imagen de un objeto, tenemos que usar esta url `http://media.blizzard.com/d3/icons/items/large/` + la propiedad `icon` + `.png`.

Si quisiéramos obtener la imagen del arma principal (_mainHand_) tendríamos que poner lo siguiente:

`http://media.blizzard.com/d3/icons/items/large/p6_unique_scythe1h_04_demonhunter_male.png`

Que se corresponde con esta imagen:

![mainHand](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/22/main-hand.png)

Como has podido ver, cada _item_ tiene una gran cantidad de propiedades que podríamos usar para crear nuestra app, pero para evitar complejidad y no alargar mucho el tema, no vamos a usar todas.

Aparte de la propiedad `icon`, vamos a usar `name`, `displayColor` (para saber la calidad del objeto) y `gems` (para saber si tiene gemas o joyas).

La estructura HTML que vamos a seguir para mostrar los objetos de nuestro personaje en pantalla es la misma que se ve en este boceto, en el bloque de _items_:

![wireframe](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/22/wireframe.png)

Un pequeño problema que podríamos tener es que nuestro personaje no tenga objetos equipados en todos los huecos posibles. Por ejemplo, puede darse el caso de que el personaje no tenga equipado el objeto de `legs`. Si esto pasara, se nos descuadraría la cuadrícula o se mostraría vacía. Es nuestro deber, como developers, controlar estos posibles casos.

  

La lista de objetos de nuestro personaje descansa en la variable `items` del componente `/views/Hero/Index.vue`. Tenemos que crear el componente de `HeroItems` para poder usarlo.

Dentro del directorio `/HeroItems` creamos nuestro componente principal `Index.vue` y le damos este contenido:

```javascript
<template>
  <div>
    <h1>HeroItems</h1>
  </div>
</template>

<script>
export default {
  name: 'HeroItems'
}
</script>
```

Ahora, desde el componente principal de la vista `Hero`, es decir, en `/views/Hero/Index.vue` hacemos el ritual de siempre: traer, declarar y utilizar el componente:

```javascript
// Traer
import HeroItems from './HeroItems/Index'
// Declarar
components: {
  BaseLoading,
  HeroDetailHeader,
  HeroAttributes,
  HeroSkills,
  HeroItems
}
```

Por último, lo usamos:

```html
<template>
  <div class="hero-view">
  <BaseLoading v-if="isLoadingHero"/>
  <HeroDetailHeader v-if="hero" :detail="detailHeader"/>

    <b-row>
      <b-col md="12" lg="8" order-lg="2">
        <BaseLoading v-if="isLoadingItems"/>
        <!-- Componente de Items del personaje -->
        <HeroItems v-if="items" :items="items"/>
      </b-col>

      <b-col md="12" lg="4" order-lg="1">
        <template v-if="hero">
          <HeroAttributes :attributes="detailStats"/>
          <HeroSkills :skills="hero.skills"/>
        </template>
      </b-col>

    </b-row>
  </div>
</template>
```

Debería verse así:

![pv-1](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/22/pv-1.png)

HeroItem
========

Vamos a crear el componente correspondiente a un objeto, que luego reutilizaremos para pintar todos los objetos. A nivel de API, todos los objetos del personaje son iguales, por lo que no tenemos que hacer distinciones.

Empezamos creando el fichero `/Hero/HeroItems/ItemDetail.vue`. Continuamos con la definición básica de nuestro componente:

```javascript
<template>
  <div>
    <h1>Item</h1>
  </div>
</template>

<script>

export default {
  name: 'ItemDetail',
  props: {
    item: {
      type: Object || undefined,
      required: true
    }
  }
}
</script>

<style lang="stylus">

</style>
```

Lo siguiente que vamos a definir son las clases CSS que necesitamos para este componente. Para ello, dentro de `style` agregamos lo siguiente:

```stylus
.d3-icon-item
  min-height 100px
  // El borde de la caja va determinar la rareza del objeto, segun el color que tenga
  border-top-style solid
  border-top-width 4px

  &.item-none
    border-color transparent

  &.item-green
    border-color #8bc34a

  &.item-orange
    border-color #ff9800

  &.item-yellow
    border-color #ffeb3b

  &.item-blue
    border-color #03a9f4

  &.item-white
    border-color #a0aab5
```

Estas clases las vamos a usar para determinar la calidad de nuestro objeto. [Recuerda](https://eu.diablo3.com/es/game/guide/items/equipment#item-quality) que el objeto puede ser blanco (_normal_), azul (_mágico_), amarillo (_raro_), verde (_de conjunto_) o naranja (_legendario_).

En el HTML vamos a poner lo siguiente:

```html
<template>
  <!-- Clase que determina el color -->
  <div class="text-center bg-dark h-100 pt-3 d3-icon-item" :class="itemClassColor">

    <div class="d-flex flex-column justify-content-between h-100">
      <!-- Si el item tiene ID, es que tenemos la información -->
      <!-- Es decir, que tiene un objeto equipado. -->
      <template v-if="item.id">
        <div>
          <div v-if="item" class="item-image">
            <!-- Nombre del objeto -->
            <p class="text-muted">{{ item.name }}</p>
            <!-- Imagen correspondiente al objeto -->
            <img :src="itemUrl" :alt="item.slotName + ' ' + item.name ">
          </div>
        </div>

        <div>
          <!-- No todos los objetos tienen gemas -->
          <!-- Por lo tanto, si el objeto tiene gemas engarzadas -->
          <template v-if="itemHasGems">
            <!-- Puede ser Gema o Joya -->
            <small>{{ gemOrJewel }}:</small>
            <ul class="list-inline">
              <!-- Un objeto puede tener varias gemas -->
              <li v-for="(gem, index) in item.gems" :key="'gem-'+index" class="list-inline-item">
                <!-- Componente gema -->
                <ItemDetailGem :gem="gem"/>
              </li>
            </ul>
          </template>
        </div>
      </template>
      <!-- En caso de que no tenga el objeto equipado -->
      <p v-else>
        <!-- Mostramos el nombre del slot y dejamos el contenido vacío -->
        <b-badge class="text-dark"> {{item.slotName}} </b-badge>
      </p>
    </div>

  </div>
</template>
```

Con los comentarios queda bastante claro que hace cada cosa.

Ahora necesitamos crear las _computed properties_ que estamos usando en el template. Agregamos, en nuestro bloque de JavaScript, las siguientes funciones (computadas):

```javascript
computed: {
  // Resuelve la URL de la imagen
  itemUrl () {
    const host = 'http://media.blizzard.com/d3/icons/items/large/'return \`${host}${this.item.icon}.png\`
  },
  // Comprueba si el item tiene gemas
  itemHasGems () {
    return Object.prototype.hasOwnProperty.call(this.item, 'gems')
  },
  // Si tiene gemas, comprueba si es Gema o Joya// Puede haber varias Gemas. Solo puede haber una Joya. No puede haber joyas y gemas mezcladas
  gemOrJewel () {
    return this.item.gems\[0\].isGem ? 'Gems' : 'Jewel'
  },
  // Clase CSS para saber la rareza
  itemClassColor () {
    if (Object.prototype.hasOwnProperty.call(this.item, 'displayColor')) {
      return \`item-${this.item.displayColor}\`
    }
    // Si no tiene color (es que no hay objeto equipado)return 'item-none'
  }
}
```

El código completo se ve así:

```javascript
<template>
  <!-- Clase CSS que determina el color -->
  <div class="text-center bg-dark h-100 pt-3 d3-icon-item" :class="itemClassColor">

    <div class="d-flex flex-column justify-content-between h-100">
      <!-- Si el item tiene id, es que tenemos la información -->
      <!-- Es decir, que tiene un objeto equipado. -->
      <template v-if="item.id">
        <div>
          <div v-if="item" class="item-image">
            <!-- Nombre del objeto -->
            <p class="text-muted">{{ item.name }}</p>
            <!-- Imagen correspondiente al objeto -->
            <img :src="itemUrl" :alt="item.slotName + ' ' + item.name ">
          </div>
        </div>

        <div>
          <!-- No todos los objetos tienen gemas -->
          <!-- Por lo tanto, si el objeto tiene gemas engarzadas -->
          <template v-if="itemHasGems">
            <!-- Puede ser Gema o Joya -->
            <small>{{ gemOrJewel }}:</small>
            <ul class="list-inline">
              <!-- Un objeto puede tener varias gemas -->
              <li v-for="(gem, index) in item.gems" :key="'gem-'+index" class="list-inline-item">
                <!-- Componente gema -->
                <ItemDetailGem :gem="gem"/>
              </li>
            </ul>
          </template>
        </div>
      </template>
      <!-- En caso de que no tenga el objeto equipado -->
      <p v-else>
        <!-- Mostramos el nombre del slot y dejamos el contenido vacío -->
        <b-badge class="text-dark"> {{item.slotName}}</b-badge>
      </p>
    </div>

  </div>
</template>

<script>

export default {
  name: 'ItemDetail',
  props: {
    item: {
      type: Object || undefined,
      required: true
    }
  },
  computed: {
    itemUrl () {
      const host = 'http://media.blizzard.com/d3/icons/items/large/'return \`${host}${this.item.icon}.png\`
    },
    itemHasGems () {
      return Object.prototype.hasOwnProperty.call(this.item, 'gems')
    },
    gemOrJewel () {
      return this.item.gems\[0\].isGem ? 'Gems' : 'Jewel'
    },
    itemClassColor () {
      if (Object.prototype.hasOwnProperty.call(this.item, 'displayColor')) {
        return \`item-${this.item.displayColor}\`
      }
      return 'item-none'
    }
  }
}
</script>

<style lang="stylus">
  .d3-icon-item
    min-height 100px
    border-top-style solid
    border-top-width 4px

    &.item-none
      border-color transparent

    &.item-green
      border-color #8bc34a

    &.item-orange
      border-color #ff9800

    &.item-yellow
      border-color #ffeb3b

    &.item-blue
      border-color #03a9f4

    &.item-white
      border-color #a0aab5
</style>
```

Para terminar, vamos a crear el componente de la gema (o joya). Creamos un nuevo archivo `ItemDetailGem.vue` al mismo nivel de `ItemDetail.vue`, es decir, dentro de `/HeroItems`.

El código de este componente es muy simple:

```javascript
<template>
  <img :src="gemUrl" :alt="gem.item.name" :title="gem.item.name">
</template>

<script>
export default {
  name: 'GemSlotItem',
  props: {
    gem: {
      required: true,
      type: Object
    }
  },
  computed: {
    gemUrl () {
      // Cambio de 'large' por 'small'const host = 'http://media.blizzard.com/d3/icons/items/small/'return \`${host}${this.gem.item.icon}.png\`
    }
  }
}
</script>
```

El único cambio que hay aquí es que en la URL de la imagen estamos usando el tamaño pequeño (`small`) en vez del grande (`large`) que usamos en los demás _items_.

Tenemos que importar este componente en el componente de detalle. Para ello, desde `/Hero/HeroItems/ItemDetail.vue` agregamos lo siguiente:

```javascript
import ItemDetailGem from './ItemDetailGem'
export default {
  name: 'ItemDetail',
  components: { ItemDetailGem }
  // ...
}
```

Con esto ya tenemos los componentes de items terminados. Queda llamarlos desde la vista principal y ¡💥! Deberían aparecer todos.

Desde `/Hero/HeroItems/Index.vue`, cargamos el componente de _ItemDetail_, lo declaramos y los utilizamos:

```javascript
<template>
  <section class="hero-items mb-5">
    <h2 class="font-diablo">Items</h2>

    <hr class="bg-white">

    <!-- Grid de 3 columnas. Mostramos solo una centrada -->
    <b-row>
      <b-col cols="4" offset="4">
        <ItemDetail :item="itemsData.head"/>
      </b-col>
    </b-row>

    <hr>

    <!-- Grid de 3 columnas -->
    <b-row>
      <b-col>
        <ItemDetail :item="itemsData.shoulders"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.torso"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.neck"/>
      </b-col>
    </b-row>

    <hr>

    <!-- Grid de 3 columnas -->
    <b-row>
      <b-col>
        <ItemDetail :item="itemsData.hands"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.waist"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.bracers"/>
      </b-col>
    </b-row>

    <hr>

    <!-- Grid de 3 columnas -->
    <b-row>
      <b-col>
        <ItemDetail :item="itemsData.leftFinger"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.legs"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.rightFinger"/>
      </b-col>
    </b-row>

    <hr>

    <!-- Grid de 3 columnas -->
    <b-row>
      <b-col>
        <ItemDetail :item="itemsData.mainHand"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.feet"/>
      </b-col>
      <b-col>
        <ItemDetail :item="itemsData.offHand"/>
      </b-col>
    </b-row>

  </section>

</template>

<script>
import ItemDetail from './ItemDetail'

// Objeto con las keys de los 'items' del personaje
const defaultItems = {
  head: {
    slotName: 'head'
  },
  shoulders: {
    slotName: 'Shoulders'
  },
  torso: {
    slotName: 'Torso'
  },
  neck: {
    slotName: 'Neck'
  },
  hands: {
    slotName: 'Hands'
  },
  waist: {
    slotName: 'Waist'
  },
  bracers: {
    slotName: 'Bracers'
  },
  leftFinger: {
    slotName: 'Left Finger'
  },
  legs: {
    slotName: 'Legs'
  },
  rightFinger: {
    slotName: 'Right Finger'
  },
  mainHand: {
    slotName: 'Main Hand'
  },
  feet: {
    slotName: 'Feet'
  },
  offHand: {
    slotName: 'Off Hand'
  }
}

export default {
  name: 'HeroItems',
  components: { ItemDetail },
  props: {
    items: {
      type: Object,
      required: true
    }
  },
  computed: {
    itemsData () {
      // Fusionar objetos:// Esto lo hacemos para mostrar el hueco vacío en caso de que ese objeto no esté equipado// Si NO hay item equipado, manda el valor de 'defaultItems' correspondiente// Si hay item equipado, manda la info del itemreturn {
        ...defaultItems,
        ...this.items
      }
    }
  }
}
</script>
```

Si tienes todo correcto y sin errores deberías ver algo como esto:

![full-pv](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/22/full-pv.png)

En mi caso, todos los personajes que tenía en el momento de crear este escrito estaban a niveles altos y con todos los huecos de equipación completos.

Sin embargo, rebuscando por internet, he encontrado un perfil a nivel 1, con varios huecos de _items_ vacíos, y solo una habilidad activa. Así es como se vería:

![low-level](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/22/low-level.png)

Si has llegado hasta aquí… 🎉 **¡Enhorabuena!** 🎉 Ya tienes una super aplicación con datos reales de personajes Diablo III.

![congrats](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/22/congrats.png)

Esta vista de la aplicación da mucho juego, pues la información que nos devuelve la API es muy extensa. En este curso no hemos trabajado con toda la información existente, ya que se haría demasiado complejo, pero te animo a que hagas extensiones y/o mejoras.

También te recuerdo que si quieres contribuir, ya sabes que el [repositorio](https://github.com/baumannzone/diablo3-vue-platzi) original siempre está abierto a mejoras y sugerencias.

En la siguiente lectura veremos cómo crear directivas personalizadas (_custom directives_).


## 24. Custom Directives

Además de las directivas de Vue que ya conoces (`v-if`, `v-for`, etc), este framework nos permite crear nuestras propias directivas personalizadas (_custom directives_). En esta entrada, vamos a ver qué son, cómo crearlas y cómo usarlas.

> 📗 [https://es.vuejs.org/v2/guide/syntax.html#Directivas](https://es.vuejs.org/v2/guide/syntax.html#Directivas)

Las directivas son pequeños atributos que podemos usar en elementos HTML. Todas tienen el prefijo `v-` para que Vue sepa que se trata de un _comando_ especial y para mantener la coherencia.

Por lo general, son útiles si necesitas controlar comportamientos de bajo nivel en elementos del DOM.

En esta ocasión vamos a crear 2 directivas muy sencillas que nos van a ayudar a entender los conceptos básicos.

Al inicio del curso, creamos una carpeta llamada `/directives`. Es ahí donde van a estar nuestras directivas personalizadas. Para empezar, creamos, dentro de esta carpeta, un archivo llamado `index.js`. Debería estar en esta ruta:

```markdown
📂 /src
└──📂 /directives
   └── index.js
```

De momento, el contenido que va a tener este archivo es el siguiente:

import Vue from 'vue'

Ahora, vamos a ir a la vista principal `Home` y abrimos el componente del formulario (`src/views/Home/HomeForm.vue`).

Dentro, tenemos que buscar el input en el que escribimos el _BattleTag_ del usuario. Este es el código del input que necesitas encontrar:

```html
<b-form-input id="input-text" v-model="form.battleTag" type="text" size="lg" required placeholder="BattleTag" />
```

La principal funcionalidad que tiene esta página de `Home` es el formulario. Por lo tanto, estaría bien que cuando un usuario llegue a esta vista el input reciba el foco (`.focus()`, [https://developer.mozilla.org/es/docs/Web/API/HTMLElement/focus](https://developer.mozilla.org/es/docs/Web/API/HTMLElement/focus)) y podamos escribir en la caja de texto directamente.

Vamos a agregar la directiva personalizada `v-focus` a nuestro _input_. Antes del `id` le agregamos la directiva y lo dejamos así:

```html
<b-form-input v-focus id="input-text" v-model="form.battleTag" type="text" size="lg" required placeholder="BattleTag" />
```

Ahora, con el servidor levantado, vamos al navegador y abrimos la consola.

![v-focus-err](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/23/v-focus-err.png)

Hay un error, nos dice que no entiende la directiva `focus`. Y es lógico, aún no hemos creado ninguna directiva.

Las directivas, al igual que el resto de elementos que hemos ido creando en la aplicación, pueden ser declaradas a nivel global o a nivel local, es decir, a nivel de componente. Para crear una directiva global, lo que vamos a hacer es usar `Vue.directive()`.

Volvemos al archivo de las directivas que acabamos de crear, `/directives/index.js` y agregamos lo siguiente:

Vue.directive('focus', {})

Ya tenemos la directiva creada, fíjate que no hemos puesto el prefijo `v-`, pues esto lo hace automáticamente Vue.

El primer parámetro, `focus` es el nombre de nuestra directiva y el segundo parámetro, `{}` es el objeto de opciones vacío. Es decir, esta directiva no hace nada.

Tenemos declarada una directiva pero la instancia principal de Vue no sabe de su existencia. Vamos a usarla desde el archivo `main.js`.

```javascript
import Vue from 'vue'

// BootstrapVue
import './plugins/bootstrapVue'

// Vue Font-Awesome
import './plugins/fontAwesome'

// Custom directives
import './directives'
```

Vamos a poner las directivas debajo de FontAwesome. Importamos el fichero de directivas que acabamos de crear. Dejamos el resto como estaba.

Ahora, si volvemos al navegador, recargamos la página y abrimos la consola, vemos que no hay ningún error. ¡Estupendo! Directiva funcionando 👌.

> 📗 Revisa esta documentación antes de continuar: [https://es.vuejs.org/v2/guide/custom-directive.html](https://es.vuejs.org/v2/guide/custom-directive.html)

Vamos a darle contenido a la directiva. Tenemos que conseguir que el input que tiene la directiva reciba el foco. El código que tiene la directiva es tan sencillo como esto:

```javascript
// Registra una directiva global llamada \`v-focus\`
Vue.directive('focus', {
  /\*\*
   \* inserted hook: Cuando el elemento es insertado en el DOM
   \* @param el {HTMLElement} El elemento al que está dirigida la directiva
   \*/
  inserted: function (el) {
    // Enfoca el elemento
    el.focus()
  }
})
```

Al poner esto en funcionamiento, si recargas la página, deberías tener el input con el _foco_, listo para escribir:

![focus](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/23/focus.png)

Este es el ejemplo que viene en la documentación de las directivas personalizadas con Vue, pero es perfecto para nuestro caso.

Ahora, cada vez que tengas un formulario al que le quieras aplicar esta funcionalidad, ya sabes como hacerlo.

Vamos a crear otra directiva, un poco más compleja. Agregamos lo siguiente al fichero de directivas:

```javascript
Vue.directive('diablo', {})
```

Es importante que revises estos 2 temas antes de pasar al siguiente punto:

*   Al igual que los componentes, las directivas también tienen _hooks_: [https://es.vuejs.org/v2/guide/custom-directive.html#Funciones-Hook](https://es.vuejs.org/v2/guide/custom-directive.html#Funciones-Hook)
*   Estos son los argumentos que soportan dichas funciones (_hooks_): [https://es.vuejs.org/v2/guide/custom-directive.html#Argumentos-en-Hooks](https://es.vuejs.org/v2/guide/custom-directive.html#Argumentos-en-Hooks)

Vamos a crear una directiva para usarla en los títulos (`<h1>`). Esta directiva, que la llamaremos `v-diablo` va a transformar el estilo del componente.

Como es una directiva más compleja, tiene múltiples formas de ser usada. Estas son las modificaciones que va a tener:

*   De manera obligatoria, va a poner la tipografía de `DiabloHeavy` sobre el elemento que recibe la directiva. Para esto no hay que hacer nada especial, solo usar la directiva.
*   Las directivas soportan argumentos a través de los dos puntos `:`. Es decir, que si le quiero pasar un argumento a la directiva `v-diablo` lo que tendria que hacer es esto: `v-diablo:platzi`. En este caso el argumento es `platzi`.
*   Aparte de los argumentos, tendremos modificadores, que se usan con el punto simple (`.`) Un ejemplo sería así: `v-diablo.top`

> Una cosa que hay que tener en cuenta es que las directivas no son reactivas, por lo que tendrás que recargar la web manualmente cada vez que hagas un cambio.

No necesitamos esperar a que el elemento esté cargado en el DOM, por lo cual, para esta directiva en vez de usar el _hook_ `inserted`, vamos a usar el _hook_ `bind`, en donde vamos a establecer la configuración inicial.

La función quedaría de la siguiente forma:

```javascript
Vue.directive('diablo', {
  /\*\*
   \* @param el {HTMLElement} Elemento al que aplica la directiva
   \* @param binding {DirectiveBinding} Datos que recibe la directiva a traves de argumentos, modificadores, etc
   \*/
  bind (el, binding) {
    // Definimos los coloresconst color = {
      bone: '#e8dcc2',
      white: '#ffffff'
    }

    // Tipografía Diablo
    el.style.fontFamily = 'DiabloHeavy, sans-serif'

    console.log('binding')
    console.log(binding)

    // Argumento (\`:\`)const arg = binding.arg === 'bone' ? 'bone' : 'white'// Si el argumento es 'bone'if (arg === 'bone') {
      // Le damos el color blanco hueso
      el.style.color = color.bone
    } else {
      // Si no, el color por defecto es el blanco
      el.style.color = color.white
    }

    // Modificadores (\`.\`)// Si hay modificadoresif (Object.keys(binding.modifiers).length > 0) {
      // Value: (\`=\`)// Valor por defecto de 'value' es 1 (Corresponde al ancho del borde en 'px')const value = binding.value || 1// Expresión con el borde, ejemplo: '1px solid white'const borderExp = \`${value}px solid ${color\[arg\]}\`

      // Si el modificador es 'bottom'if (binding.modifiers.bottom) {
        // Ponemos una linea debajo del elemento
        el.style.borderBottom = borderExp
        // Separada 10px
        el.style.paddingBottom = '10px'
      }
      // Si el modificador es 'top'if (binding.modifiers.top) {
        // Ponemos una linea encima del elemento
        el.style.borderTop = borderExp
        // Separada 10px
        el.style.paddingTop = '10px'
      }
    }
  }
})
```

*   Argumento: Accedes a su valor a través de `binding.arg`. Recuerda, solo puedes pasar 1 argumento. Lo usas con los dos puntos (`:`). Ejemplo “`v-diablo:argumento`”.
*   Modificadores: Se usan con el punto (`.`) y puedes acceder a ellos a través de `binding.modifiers`, que es un objeto.
*   Si usamos esto “`v-diablo.modificador1.modificador2`”, en el objeto de modificadores recibimos esto:

```javascript
{ modificador1: true, modificador2: true }
```

*   Valor: Lo usas con el símbolo igual (`=`) en la directiva y pasándole un valor, ejemplo: `v-diablo="42"`. Accedes a su valor a través de `binding.value`

Argumentos posibles
-------------------

**Color del texto**:

*   `bone`
*   `white` (color por defecto)

Modificadores posibles
----------------------

**Posición de la línea:**

*   `bottom`
*   `top`

Valor
-----

**Grosor de la línea en** `**px**`**:**

*   Si no le pasas valor, por defecto es 1 (px)
*   Valor numérico. Si le pasas valor, recibe el número que se le pasa (en px)

Con esto claro, tenemos varias opciones para usar nuestra directiva:

*   `v-diablo:bone`, color _blanco hueso_ en el texto.
*   `v-diablo:white` que es lo mismo que `v-diablo`. El blanco es el color que hemos puesto por defecto.
*   `v-diablo:bone.bottom`: Le pone un `border-bottom` de color `bone` de `1px`.
*   `v-diablo:bone.top`: Le pone un `border-top` de color `bone` de `1px`.
*   `v-diablo:bone.top="10"`: Le pone un `border-top` de color `bone` de `10px`
*   `v-diablo:white.top="10"`: Le pone un `border-top` de color blanco de `10px`

Para el título principal de la vista `Home` y para el nombre del héroe, en la vista `Hero`, me gusta usar `v-diablo:bone`, para que resalte un poco más del resto de títulos.

*   `/Home/HomeTitle.vue`:

```html
<h1 v-diablo:bone class="my-5">Diablo 3 Profile Finder</h1>
```

*   `/Hero/HeroDetailHeader.vue`:

```html
<h1 v-diablo:bone class="text-truncate">{{ detail.name }}</h1>
```

Estos cambios se ven así de espectaculares:

![home](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/23/home.png)

![hero](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/23/hero.png)

Haz pruebas y déjalo como más te guste.

  

**Como has podido ver, tenemos infinitas posibilidades. ¿Cómo lo has usado tú? ¿Qué pasaría si usamos** `**v-diablo:top.bottom**`**? ¿Qué combinación te gusta más? Deja tus respuestas en el sistema de comentarios ✍️.**

Aunque este ejemplo no sea el más recomendado para usar las directivas, se puede comprobar que son muy potentes en este aspecto. Tal vez para este caso hubiera sido mas recomendable hacer un componente título o simplemente agregarle las clases CSS específicas.

Si quieres ampliar conocimientos, te recomiendo que visites este enlace con muchas directivas para que puedas experimentar y probar ya mismo: [https://codesandbox.io/s/directivas-personalizadas-en-vue-puyyq](https://codesandbox.io/s/directivas-personalizadas-en-vue-puyyq)

¡Awesome! Ya tenemos la app a tope de _power_, lista para subirla y desplegarla en algún servidor.

![awesome](https://media1.giphy.com/media/em4i0bDs9Hm2Q/giphy.gif?cid=790b7611eed8c1cc55eba33dbbb41d102f10e7a66ac0f615&rid=giphy.gif)

En la siguiente clase veremos cómo subir y desplegar automáticamente nuestra aplicación.


## 25. Netlify

Seguramente hayas oído hablar de [Netlify](https://www.netlify.com/), pues últimamente está en boca de todos. A mi, personalmente, es la plataforma que más me gusta de todas las que hay.

Hace tiempo que he sustituido _Github Pages_ por este servicio. Me gustaba describirlo como “_Github Pages_ con super-poderes”.

![net](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/net.png)

Como te habrás dado cuenta, la [web original](https://diablo3.netlify.com/) del proyecto está alojada en **Netlify**.

Vamos a configurar este servicio para tener nuestra web online, con despligue automático, para que cada vez que hagamos un commit a la rama `master` en el repositorio de GitHub, se ejecuten las tareas correspondientes y la web se despliegue con el nuevo contenido.

Variables de Entorno
====================

Lo primero que deberíamos hacer antes de subir nuestra app a Netlify es buscar una forma para **no** subir las claves del cliente de Diablo III, el `clientSecret` y el `clientId`.

Esto lo vamos a hacer usando variables de entorno. Las variables de entorno nos van a permitir 2 cosas:

*   La primera, securizar nuestra app, pues no vamos a compartir nuestras claves del cliente de Diablo III ([https://develop.battle.net/access/clients](https://develop.battle.net/access/clients))
*   La segunda es que la app sea más flexible y modular, pues vamos a poder configurarla a través de un fichero.

> 📗 Lee la documentación de las variables de entorno aquí: [https://cli.vuejs.org/guide/mode-and-env.html#environment-variables](https://cli.vuejs.org/guide/mode-and-env.html#environment-variables)

Vamos a crear nuestra primera variable de entorno. Imagina que quieres que el título de la aplicación se pueda configurar con una variable de entorno.

El CLI de Vue nos ofrece una forma muy sencilla para poder usar las variables de entorno. Lo primero es crear un archivo llamado `.env`, lo segundo es meter nuestras variables. Un archivo `.env` simplemente contiene pares _clave=valor_.

Para que Vue lo entienda, todas las variables de entorno que crees deben empezar, obligatoriamente, por `VUE_APP_`.

Crea tu archivo `.env` en el directorio raíz del proyecto, y crea la variable `VUE_APP_TITLE=D3PF`:

![env](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/env.png)

Webpack se va a encargar de que nuestra variable esté accesible desde cualquier parte de la aplicación. Podemos acceder a ella a través de `process.env.VUE_APP_TITLE`.

Para probar que funciona, podemos ir al componente `src/components/HeaderBar/Index.vue` donde tenemos el icono y el título de la app. Cambiamos el título por nuestra variable de entorno de la siguiente forma:

```javascript
<template>
  <div class="header-bar">
    <div class="navigation-bar">
      <b-navbar toggleable="lg" type="dark" variant="dark">
        <b-navbar-brand :to="{ name: 'Home' }">
          <img src="@/assets/img/diablo-iii.svg" alt="D3" width="30">
          <!-- Variable de Entorno -->
          <span class="font-diablo ml-2">
            {{ title }}
          </span>
        </b-navbar-brand>
      </b-navbar>
    </div>

  </div>
</template>

<script>

export default {
  name: 'HeaderBar',
  data () {
    return {
      // 🔥 Note that only variables that start with VUE_APP_ will be statically embedded// into the client bundle with webpack.DefinePlugin.// Recuperamos la variable de entorno y la guardamos en 'title'
      title: process.env.VUE_APP_TITLE
    }
  }
}
</script>
```

Todas las variables de entorno las puedes encontrar bajo `process.env`.

Continuando con el proceso anterior, si abres la web, deberías ver algo como esto:

![env2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/env2.png)

😳 ¡El título ha desaparecido! No pasa nada, está todo controlado. Solo necesitamos **reiniciar** el servidor (`npm run serve`) para que se reflejen los cambios. Y ahora sí, deberías ver esto:

*   Levantamos server:
*   ![server](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/server.png)
*   Abrir la web:
*   ![env3](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/env3.png)

Ya sabes cómo crear variables de entorno y cómo usarlas. Estas variables de entorno son “públicas”, para crear variables de entorno de tipo “privado” Vue CLI nos da otro método. Simplemente hay que crear el fichero de variables de entorno con otro nombre: `.env.local`.

#### En resumen:

```
.env                # Cargada en todos los casos
.env.local          # Cargada en todos los casos, ignorado por Git
```

Este modo de crear variables de entorno nos interesa más, ya que queremos que Git lo ignore y no lo suba. Es justo lo que necesitamos para trabajar con nuestros datos del cliente de Diablo III (clientId y clientSecret).

Creamos el fichero `.env.local`, al mismo nivel que el otro que hemos creado antes y le damos el contenido de nuestras variables:

```
VUE_APP_CLIENT_ID =db5d7d6e7db543e0a3e13cf5812ce76
VUE_APP_CLIENT_SECRET=wuf4Ym9jX5kOurOUnmnB8wdBO6VKSm6
```

> Recuerda usar tus claves, estas no te van a funcionar ☝️.

A continuación deberíamos cambiar las variables de `clientId` y `clientSecret` que creamos al principio por las variables de entorno. Para ello, vamos al fichero de `/api/oauth.js` y cambiamos:

```diff
// Variables de Entorno
- const clientId = 'db5d7d6e7db543e0a3e13cf5812ce76d'
- const clientSecret = 'wuf4Ym9jX5kOurOUnmnB8wdBO6VKSm60'
+ const clientId = process.env.VUE_APP_CLIENT_ID
+ const clientSecret = process.env.VUE_APP_CLIENT_SECRET
```

Ahora nuestras claves están a salvo (en un fichero local), pues git las va a ignorar, pero cuando levantemos el servidor, Vue las va a saber interpretar. Recuerda que tienes que reiniciar después de hacer estos cambios.

Desplegando la aplicación
=========================

Ahora sí, ya tenemos todo preparado para poder desplegar nuestra app en la nube ☁️. Antes de nada, necesitas tener una cuenta en [Netlify](https://www.netlify.com/), si es que no la tienes ya.

Mi recomendación es que lo hagas con la cuenta de GitHub, pero puedes usar el método que quieras.

![login](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/login.png)

Una vez tengas la cuenta creada y estés en el panel de control de Netlify (ver imagen abajo), vamos a crear un nuevo sito a partir de git con el botón `New site from Git`:

![arrow](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/arrow.png)

En el siguiente paso tenemos que elegir el servicio en el cual tenemos alojado nuestro código. En mi caso se corresponde con “GitHub”, los pasos deberían ser similares en los 3 casos.

![options](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/options.png)

Te pedirá que inicies sesión con el GitHub, o con el servicio que hayas seleccionado. Una vez estés logeado, lo siguiente que tienes que hacer es buscar el repositorio que quieres desplegar en el listado que aparece:

![repo](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/repo.png)

Una vez que hayas elegido el repositorio que quieres desplegar, deberías estar en el paso de “**Configuración del despliegue**” (_Deploy settings_):

![build-opts](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/build-opts.png)

![build-opts-2](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/build-opts-2.png)

Vamos a revisar las opciones que tenemos para configurar:

*   Owner: Lo dejamos tal cual está.
*   Branch to deploy: Elige la rama dónde está el código para subir, en este caso, en `master`.

Ahora viene lo más importante (y lo que más me gusta 😍)

*   **Build command**: El comando con el que hacemos el `build` de nuestra aplicación. Escribimos `npm run build`.
*   **Publish directory**: El directorio que se genera al hacer el _build_. Escribimos `dist`.

Cuando lo tengas listo, le das a `Deploy site` y _voilà_! Tu sitio web está a punto de desplegarse. Por defecto, tendrás una URL autogenerada, pero le puedes poner un nombre. En mi caso le he puesto `diablo3`, por lo que la url completa es la siguiente: `https://diablo3.netlify.com`.

Si te interesa cambiar el nombre debes hacer click en `Site settings` y luego en `Change site name`

![change-name](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/change-name.png)

Si aún no te has enamorado de Netlify, te cuento más:

*   Cada vez que subas un cambio a la rama `master` (o la rama que hayas configurado), tus cambios se desplegarán automágicamente 😱.
*   Tienes acceso al historial de todos los despliegues (_deploys_) de tu app, vas a poder ver cómo estaba tu app hace 1 semana (por ejemplo) 🤯.
*   En caso de que hagan un _Pull Request_ en Github, te genera un deploy (automático) del PR para que puedas ver cómo queda 🤯🤯
*   ¡Todo esto de manera gratuita! 👏

En la siguiente imagen se puede ver la vista de detalle de un _deploy_, el 21 de Febrero. Si hacemos click en ese link, podemos ver cómo estaba la web ese día.

![preview-deploy.](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/preview-deploy.png)

En la imagen vemos un Pull Request en Github. Como lo tenemos configurado con Netlify, automáticamente nos va a generar una URL para que podamos ver el resultado, antes de aceptar el _PR_.

![PR.](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/PR.png)

En caso de que todo en la app esté OK, aparece un check ✅ indicándonos que la app se ha podido desplegar sin problemas (Ver la siguiente imagen).

Si hubiera algún error, aparecería una `X` de color rojo ❌.

![PR-OK](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/PR-OK.png)

Desde que conocí Netlify, es mi hosting personal en el cual subo todos mis proyectos.

Me hace la vida más fácil, y si lo necesitas, puedes comprar el dominio y hostear la web sin utilizar un subdominio de _Netlify_.

Con tu app funcionando, puedes compartir el enlace de tu app en el sistema de comentarios.

¿Cómo que no te funciona? ¿¿Un error?? 🤔

¿Qué crees que ha pasado? 😜 Si pensaste en variables de entorno, acertaste.

La app no puede funcionar correctamente, ya que no las hemos configurado en Netlify. Desde el panel de control de Netlify vamos a ser capaces de configurar las variables de entorno de nuestra app muy fácilmente.

Para configurar las variables de entorno vamos a `Site settings` > `Build & Deploy` (del menú de la derecha) > `Environment`. Le das a `Edit variables` y metes las variables de entorno que hemos configurado antes:

*   VUE_APP_CLIENT_ID
*   VUE_APP_CLIENT_SECRET
*   VUE_APP_TITLE

![env-var](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/24/env-var.png)

Una vez hayas hecho eso, ya debería funcionarte la app sin problemas. Hay que desplegarla de nuevo, para que tenga la configuración nueva. Para ello, vamos a la pestaña _deploys_ y hacemos click en `Trigger deploy` (un botón, a la derecha). Esto va a lanzar manualmente un despliegue. En cuanto terminé el despliegue, tu sitio web estará listo. ✌️

Ahora que ya tienes tu app corriendo en Netlify, es el momento de que compartas tu enlace a través del sistema de comentarios. ¿Has hecho algún cambio? 🎨 ¡Muéstrale al mundo tu creación!


## 26. About y Error

Si has llegado hasta aquí… ¡Enhorabuena! Ya tienes una super aplicación Vue creada desde 0 que utiliza conceptos avanzados. Además has podido subirlo a la plataforma de Netlify y administrar las variables de entorno.

👏 👏 👏 🦄 👏 👏 👏

Lo que nos queda para terminar definitivamente es darle contenido a las páginas de _About_ y de _Error_, que las hemos dejado un poco de lado durante el curso, ya que no tienen ninguna funcionalidad especial que explicar.

En la página de `About`, que corresponde con el fichero `/views/About/Index.vue` vamos a poner esto, que es HTML plano:

```javascript
<template>
  <div class="about-view mb-5">
    <div class="text-center">
      <!-- Directiva v-diablo, en blanco 😎 -->
      <h1 v-diablo:white class="my-5">Diablo 3 Profile Finder</h1>

      <hr class="bg-dark mb-5">

      <p class="lead">
        Diablo III is a genre-defining action-RPG set in Sanctuary, a world ravaged by the eternal conflict between angels and demons.
      </p>
      <p class="lead">
        <span class="font-weight-bold">D3PF</span> allows you to enter your battle-tag to see your profile, your last played heroes, your items, skills and more.
      </p>
    </div>

    <hr class="bg-dark my-5">

    <div class="mt-5">
      <h2 class="mb-4">API Rate Limit</h2>
      <b-alert show variant="dark">
        Clients exceeding these limits may experience slower service or a response error. See the
        <a href="https://develop.battle.net/documentation/guides/getting-started">Getting Started Guide</a> for more details.
      </b-alert>

      <dl class="row mt-5 text-center text-sm-left">
        <div class="col-sm-6 mb-3">
          <dt>36,000 requests per hour</dt>
          <dd>Long-term Quota</dd>
        </div>

        <div class="col-sm-6">
          <dt>100 requests per second</dt>
          <dd>Short-term Throttle</dd>
        </div>
      </dl>

    </div>

    <div class="my-5">
      <h2>Getting Started</h2>

      <p>Before you can get started using the Blizzard APIs, you must:</p>

      <ol>
        <li>Login or create a new Battle.net account.</li>
        <li>Create a client through the API Access menu option.</li>
        <li>Generate a secret for the client.</li>
        <li>Understand how Blizzard APIs work with OAuth.</li>
      </ol>

      <p class="text-break">Read more here:
        <a href="https://develop.battle.net/documentation/guides/getting-started">https://develop.battle.net/documentation/guides/getting-started</a>
      </p>
    </div>

    <hr>

  </div>
</template>

<script>
export default {
  name: 'AboutView'
}
</script>
```

Abre la página de _About_ en el navegador, deberías verlo así:

![about](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/25/about.png)

La página de error es bastante sencilla también. Como recordarás, cada vez que teníamos un error, guardabamos toda la información del error en el _Store_ de nuestra aplicación (Lo puedes ver en: `/store/modeules/error.js`)

Pues bien developer, lo único que hay que hacer es recuperar los datos del _Store_ y mostrarlos en la vista de Error, `/src/views/Error/Index.vue`:

```html
<template>
  <div class="error-page m-5">
    <hr class="my-5">
    <!-- Si hay error -->
    <div v-if="err">

      <!-- Si hay codigo de error -->
      <h1 class="my-5">
        Error <span v-if="err.status">{{ err.status }}</span>
      </h1>

      <!-- Si hay parámetros de ruta -->
      <div v-if="err.routeParams">
        <h2>Query Params:</h2>
        <ul class="list-unstyled">
          <li v-for="(val, key) in err.routeParams" :key="key">
            👉 {{ key.toUpperCase() }}: <span class="lead text-muted">{{ val }}</span>
          </li>
        </ul>

        <hr class="my-5">
      </div>

      <!-- Si hay mensaje de error -->
      <div v-if="err.message">
        <p class="lead">
          {{ err.message }}
        </p>
      </div>

      <!-- Si hay información de error adicional -->
      <div v-if="err.data">
        <ul class="list-unstyled">
          <li v-for="(val, key) in err.data" :key="key">
            {{ key.toUpperCase() }}:
            <span class="lead text-muted">
              {{ val }}
            </span>
          </li>
        </ul>
      </div>

    </div>

    <!-- Si NO hay error -->
    <div v-else>
      <h1 class="my-5">Error Page</h1>
      <p class="lead">What are you doing here? 🤔</p>
    </div>

  </div>
</template>

<script>
import { mapState } from 'vuex'
import setError from '@/mixins/setError'

export default {
  name: 'ErrorView',
  mixins: \[setError\],
  computed: {
    ...mapState('error', {
      err: 'error'
    })
  },
  // Este "guardia de ruta" es invocado justo antes de cambiar de página// Es perfecto para limpiar el mensaje de error a través del mixin y liberar memoria
  beforeRouteLeave (to, from, next) {
    this.setApiErr(null)
    next()
  }
}
</script>
```

Con los comentarios hemos explicado bastante bien lo que hace cada parte, pero hay una que no hemos visto durante el curso. Es el guardian de ruta `beforeRouteLeave`.

> 📗 Puedes leer más acerca de los guardianes de ruta aquí: [https://router.vuejs.org/guide/advanced/navigation-guards.html#in-component-guards](https://router.vuejs.org/guide/advanced/navigation-guards.html#in-component-guards)

Los _route guards_ pueden ser utilizados a nivel local de componente, como en este caso, y a nivel global, en el archivo donde tienes las rutas, `router.js`.

El guardián de ruta (_route guard_) `beforeRouteLeave` se ejecuta justo antes de que la ruta que renderiza el componente vaya a cambiar. En ese momento seguimos teniendo acceso al `this`, por lo tanto es el momento perfecto para limpiar o liberar recursos.

En este caso, lo que nos interesa el limpiar el mensaje de error de Vuex (haciendo la llamada al mixin con el valor `null`), ya que si no lo limpiamos al salir, va a estar ocupando sitio en nuestro _Store_ inútilmente.

Para forzar el error y poder ver la página de error puedes borrar o renombrar las variables de entorno y volver a lanzar el proyecto. Cuando intentes obtener el perfil de un jugador te saldrá este error:

![error](https://raw.githubusercontent.com/baumannzone/d3pf-images/master/25/error.png)

Error 401, no autorizado (ya que no hemos conseguido el token de acceso), junto con los parámetros de búsqueda:

*   BattleTag: `SuperRambo-2613`
*   Región: `EU`

Prueba a obtener otros errores y comparte tu resultado en el sistema de mensajes. Un error puede ser pedir los datos de un usuario (_BattleTag_) existente con una región incorrecta. ¿Que error te da? ¿Qué te aparece en pantalla? ¿Crees que ese mensaje de error es correcto? Explica tu respuesta en el sistema de comentarios.

  

Despedida
=========

Ahora sí, el curso ha llegado a su **fin**. Espero que lo hayas disfrutado tanto como yo y que hayas aprendido mucho. Si has ido haciendo paso a paso todo lo que se ha explicado durante el curso, me gustaría ver tu versión de la aplicación. Comparte tu enlace de Netlify para que podamos verlo todos 🤩.

Para cualquier consulta o sugerencia (**¡Todo el feedback es bienvenido!**) ya sabes que puedes usar el sistema de comentarios de la aplicación o buscarme en las [redes](https://twitter.com/baumannzone). Te recomiendo que utilices el sistema de preguntas y respuestas, para así (además de conseguir puntos) ayudar los demás compañeros que puedan tener las mismas dudas que has tenido tú. Anímate, y pregunta siempre que lo consideres oportuno.

Por último, me gustaría decirte que el [repositorio oficial de la aplicación](https://github.com/baumannzone/diablo3-vue-platzi) siempre estará abierto a mejoras o nuevas ideas de hacer las cosas, por lo que si te ves con ganas, siempre puedes hacer un **Pull Request**, y con ello, ganarte el aparecer en la lista de contributors de la aplicación 😍. Suena bien, ¿verdad? ¡Espero tu participación!

👋 ¡Hasta la próxima!