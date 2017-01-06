## Intro
- Vue momentum
---
- Disclaimer acerca de la serie de posts

## Que es
- Que es
- Por que usar Vue
- Comentario vs React/Angular2

## Uso
- CDN
- [CODIGO HTML]
- Explicacion CDN
```html
    <div id="app"></div>
```
- Comentario
```js
new Vue({
    el: '#app',
})
```
- Explicacion `new Vue`
- Explicacion `el` selector


## Agregando datos
- Comentario
```html
<div id="app">
    <p>{{titulo}}</p>
</div>
```
- Explicacion template
```js
new Vue({
    el: '#app',
    data: {
        titulo: 'Hola Mundo',
    },
})
```
- Explicacion de `data`.
- Explicacion del rendering.

## Input del usuario
- Comentario
```html
<div id="app">
    <input type="text"></input>
    <p>{{titulo}}</p>
</div>
```
- Explicacion v-model
<div id="app">
    <input type="text" v-model="titulo"></input>
    <p>{{titulo}}</p>
</div>
```
- Explicacion two-way data-binding

## Conclusion
- Comentario acerca de Vue
- Link al repo

---
- Disclaimer acerca de la serie de posts