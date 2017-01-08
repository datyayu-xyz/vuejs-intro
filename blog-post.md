Desde hace ya varios meses, el mundo del frontend se ha visto dominado por React y Angular 2 como las alternativas principales para crear aplicaciones pero ultimamente ha aparecido una tercera opción que es cada vez más importante y que para muchos es superior incluso a las ya existentes: [Vue.js](https://vuejs.org/).

Si quieres ver el código del ejemplo en este post o tienes alguna duda, puedes checar [el repo en github](https://github.com/datyayu-xyz/vuejs-intro).


## ¿Qué es?
[Vue.js](https://vuejs.org/) (pronunciado 'viu', como en 'view') es un framework de javascript para construir interfaces. Es similar a react en el sentido de que su enfoque principal es la parte visual de la aplicación pero a diferencia de react, Vue propone formas "oficiales" de resolver problemas como routing, ajax o manejo de estado.

Dicho de una manera más sencilla, Vue es un framework diseñado para construir aplicaciones web pero sin la fatiga de tener que buscar que libreria usar para cada problema, pues Vue ya te da las respuestas desde un inicio. 

![](/content/images/2017/01/logo-1.png)

Si tuviera que comparar Vue con las otras librerías populares de javascript para SPAs, considero que es un punto medio entre React (por su simplicidad, manejo de estado y virtual DOM) y angular (por su two-way data binding y templates).

Lo interesante, sin embargo, es el hecho de que Vue.js es un framework desarrollado por la comunidad y no por una empresa grande como Google o Facebook. El hecho de que aún sin una empresa grande detrás del framework haya sido capaz de generar tal impacto en la comunidad al punto de que productos como [Gitlab](https://about.gitlab.com/) o [Laravel](https://laravel.com/) lo están utilizando en producción es para mí un buen indicador de que su simplicidad y calidad como librería de javascript.


## Uso
Ahora que sabemos que es Vue, crearemos un ejemplo sencillo para darnos una idea de como usar el framework. 

Primero que nada, creamos una pagina simple de HTML y agregamos el script de Vue. Lo mas recomendado es instalar Vue usando npm pero para este post usaremos el link al CDN que Vue nos ofrece.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Intro a Vue.js</title>
</head>
<body>
    <div id="app"></div>

    <script src="https://unpkg.com/vue/dist/vue.js"></script>
    <script>
        // Nuestro codigo va aquí.
    </script>
</body>
</html>
```

Nada fuera de lo común aquí, es una pagina normal con un `div` que será donde montaremos nuestros elementos que interactuarán con Vue.js. También agregamos un etiqueta de `script` adicional que es donde escribiremos nuestro código.


Para asociar el `div` con Vue todo lo que tenemos que hacer es agregar el siguiente código:

```js
new Vue({
    el: '#app',
})
```

`new Vue({ ... })` es la manera en que creamos una instancia de Vue. Cada instancia es un objeto especial de Vue que puede contener métodos y datos para hacer funcionar nuestra aplicación.

El objeto con el creamos nuestra instancia de Vue tiene que tener un atributo `el`, el cual indica en que elemento montar la instancia usando un selector de css, como jQuery. En nuestro caso, queremos correr la explicación en el elemento con `id` `'app'` así que le pasamos `'#app'`.


## Agregando datos

Ya creamos una instancia de Vue.js, ahora lo que sigue es mostrar datos dinámicamente para comprobar que este funcionando.

En nuestro HTML agregamos un párrafo donde mostraremos algo:

```html
<div id="app">
    <p> {{ titulo }} </p>
</div>
```

Si has usado algún sistema de templates antes, lo más seguro es que reconozcas esta sintaxis. Lo que se encuentra dentro de los `{{ }}` es una código de javascript que se evaluara al momento de correr nuestra aplicación. En este caso, tenemos una variable `titulo` que declararemos en nuestra instancia de Vue y cuyo valor se mostrará al correr la aplicación. 

Para declarar datos en Vue, al crear nuestra instancia lo declaramos en la propiedad `data`.

```js
new Vue({
    el: '#app',
    data: {
        titulo: 'Hola Mundo',
    },
})
```

Así como `el` se usa para especificar donde montar la instancia, `data` es usada para declarar que datos va a tener la misma. La manera en que hacemos esto es en un objeto donde cada propiedad especifica su valor por defecto. En nuestro caso, declaramos la propiedad `titulo` con valor de `'Hola Mundo'`.

Si corres esto en tu navegador, podrás ver como ya se muestra el `'Hola mundo'`. Así de sencillo es mostrar datos con Vue.

![](/content/images/2017/01/Screen-Shot-2017-01-07-at-4.43.35-PM.png)


## Modificando datos

Ya vimos como mostrar datos pero, para poder apreciar la parte "dinámica" mejor, haremos que el usuario pueda modificar esos datos directamente.

Para esto, agreguemos un `input` simple.

```html
<div id="app">
    <input type="text"></input>
    <p>{{titulo}}</p>
</div>
```

La manera en que podemos conectar ese `input` con la propiedad que ya tenemos es usando `v-model`.

```html
<div id="app">
    <input type="text" v-model="titulo"></input>
    <p>{{titulo}}</p>
</div>
```

Lo que `v-model` hace es que le dice a Vue que haga que el valor de ese `input` sea igual al de la propiedad `titulo`, y si ese `input` cambia, actualice también el valor de `titulo`.

Si probamos esto, al modificar el input, automaticamente Vue.js se encarga de actualizar los datos sin que tengamos que  hacer esfuerzo extra.

![](/content/images/2017/01/2AGu7IHRTP.gif)


## Conclusión
Como puedes ver Vue.js es super simple de utilizar y facil de aprender. Aun así, esta es sólo una pequeña introducción a todo lo que Vue.js nos ofrece. Si quieres saber más, continua leyendo los siguientes posts en la serie para aprender a fondo las diferentes funcionalidades que Vue.js nos ofrece.

Todo el codigo [El repo con el ejemplo en este post está disponible en github](https://github.com/datyayu-xyz/vuejs-intro) para cualquier duda que tengas o mejora que quieras agregar, así que no dudes en hacerlo!

---

*Este post es parte de [una serie acerca de VueJS](LINK_A_LOS_POSTS). Si tienes dudas o hay alguna funcionalidad que aun no haya cubierto, no dudes en avisarme.*