# ejercicio-vue

## Se aborda en el ejercicio .- 
Añadir un listado de miembros que pertencen a Lemoncode:

Leer de la api de Github para obtener miembros de una organización.
Añadir un input y un botón para filtrar por organización, es decir:

Se muestra un input que por defecto tiene como valor: lemoncode.
Se muestra por defecto el listado de miembros de lemoncode (o tabla).
El usuario puede teclear otro nombre de organizacíon, por ejemplo: microsoft y al pulsar el botón de busqueda te muestra los miembros de dicha organizacíon.
Muestra el detalle de un miembro de esa organización en otra página.
Que al volver de la página de detalle se muestre la organización que se había tecleado en el filtro (por ejemplo si el usuario tecleó microsoft se debe de ver Microsoft).

## Queda fuera del ejercio.-
La implementación de tabla con paginación, ya que a la hora de realizar el ejercicio se implemento en VUE 3 y las soluciones de Vuetify 3 alpha no tiene ni tablas ni paginados.
Se intento implementar con otras soluciones ( bootstrap, jquery, datatables ... )  que no funcionanron del todo bien o no tiene soporte a VUE3 y se deja fuera de la entrega.

https://athemes.com/collections/vue-ui-component-libraries/

## Enunciado .-
Master Continuo - Laboratorio - Módulo 4 - Frameworks - Vue
Intro
Laboratorio del módulo de Vue, lo hemos divido en dos secciones

Básico: si queréis simplemente práctica el mínimo de esta parte y aprobarla (tenéis opciones para subir nota) y centraros en otro framework / librería.
Opcional para trabajar con la tecnología y empezar a hincar diente.
IMPORTANTE: estas prácticas las tenéis que subir a vuestro repositorio de Github (o si lo prefirís Gitlab o Bitbucket público).

Básico
Filtrado organización miembros Github
Mostrar una listado de miembros que pertenecen a una organizacíon en Github (Microsoft, Facebook, Lemoncode...), y permitir al usuario que pueda introducir el nombre de organización que quiera le de al botón de cargar y que se carguen los datos.

Enunciado
Añadir un listado de miembros que pertencen a Lemoncode:

Leer de la api de Github para obtener miembros de una organización.
Añadir un input y un botón para filtrar por organización, es decir:

Se muestra un input que por defecto tiene como valor: lemoncode.
Se muestra por defecto el listado de miembros de lemoncode (o tabla).
El usuario puede teclear otro nombre de organizacíon, por ejemplo: microsoft y al pulsar el botón de busqueda te muestra los miembros de dicha organizacíon.
Muestra el detalle de un miembro de esa organización en otra página.
Que al volver de la página de detalle se muestre la organización que se había tecleado en el filtro (por ejemplo si el usuario tecleó microsoft se debe de ver Microsoft).
Ideas opcionales
Intenta crearlo usando Nuxt (server side rendering + static).
Implementa paginación para la tabla.
Utiliza una tabla de Vuetify.
Nuxt
Para usar Nuxt, la manera oficial es create-nuxt-app: https://nuxtjs.org/docs/2.x/get-started/installation#using-create-nuxt-app

Vuetify
Para usar Vuetify, una limitación que tenemos es que no dan soporte de momento a Vue 3. Tendréis que empezar vuestra pp eligiendo en los presets (si usáis Vue CLI), la versión 2 de Vue. Github issue.

> vue create nombre_de_la_app # elegir el preset de Vue 2...
> vue add vuetify
No debería daros problemas, aun usando la última versión de Vue CLI (4.5.9, al momento de escribir esto).

Fijaros que en el main.ts (o main.js) esté vuetify referenciado. Quizás tenéis que añadir .use(vuetify) como dice este usuario/a: https://github.com/vuetifyjs/vue-cli-plugins/issues/140#issuecomment-671288792

Yo el ejercicio lo he hecho con Nuxt + Vuetify. Y Nuxt de momento solo trabaja con Vue 2 ;)

Si os da problemas Vuetify, por tema de versiones; recordad que lo importante es conocer Vue, las funcionalidades del framework. Podéis darle un poco de estilos para que no sea tan tosca la interfaz, o utilizar otro framework/librería de CSS.
## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### url interesantes .-

https://vuetifyjs.com/en/getting-started/installation/

https://next.vuetifyjs.com/en/

https://davidwalsh.name/javascript-debounce-function

https://vuex.vuejs.org/guide/forms.html

https://flaviocopes.com/vuex/
