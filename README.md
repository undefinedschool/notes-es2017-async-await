> El siguiente contenido fue elaborado por [@_nhsz](https://twitter.com/_nhsz) como guía para las clases de [undefined school](https://twitter.com/undefinedSchool)
> Son bienvenidos los _issues_ y _PRs_ para mejorar el contenido, corregir errores, etc. 

> 👉 Si te resultó útil, **se agradece que lo compartas para que le llegue a más gente!**

# [WIP] ✨ ES2017: Async/Await

Una de las principales desventajas de manejar asincrinismo en JavaScript, es que muchas veces resulta algo complejo razonar o seguir el flujo de las diferentes operaciones, principalmente porque estamos más acostumbrados a pensar de forma _sincrónica_.

Es por esto que en la versión [ES2017](https://medium.com/@tmvvr/ecmascript-async-await-to-the-rescue-fc379ff89146) de JavaScript se incorporó una nueva forma de trabajar con código asincrónico, `async/await`.

`async/await` nos permite _pausar_ la ejecución de funciones asincrónicas, para poder _escribir código asincrónico que se lea como código sincrónico_, resultando de esta forma, más legible y simple de razonar.

> 👉 `async/await` no deja de ser _sugar syntax_ (es decir, una forma más simple de escribir) sobre [_Promises_](https://github.com/undefinedschool/notes-es6-promises/)

## Async

> 👉 El operador `async` transforma una función cualquiera en una que retorna una [Promise](https://github.com/undefinedschool/notes-es6-promises). Entonces, al agregar `async` delante de cualquier función, esta pasa automáticamente a retornar una promesa al valor original que retornaba antes. 

Por ejemplo, si tenemos

```js
function sum(a, b) {
  return a + b;
}
```

La función `sum` retorna un número. Al agregar `async` delante

```js
async function sum(a, b) {
  return a + b;
}
```

la función pasa a retornar una `Promise` a este número.

## Await

> 👉 El operador `await` le indica a un valor o expresión cualquiera que tenga a continuación, que espere a que la [Promise](https://github.com/undefinedschool/notes-es6-promises) se resuelva antes de continuar (lo que haríamos con el `.then()`). Cuando se usa junto con la declaración de una variable o constante (`var`, `let` o `const`), asigna la respuesta de la promesa a la variable, en lugar de la promesa en si misma.

👉 **`await` sólo puede utilizarse dentro de una función `async`**

Ejemplo usando `fetch`

```js
async function getPost() {
  const response = await fetch('https://jsonplaceholder.typicode.com/posts/5');
	const post = await response.json();
  
  console.log(post);
  return post;
};

getPost();
```

## Error Handling

[![Complete Guide to JS Async & Await ES2017/ES8](https://img.youtube.com/vi/krAYA4rvbdA/0.jpg)](https://www.youtube.com/watch?v=krAYA4rvbdA)
> Ver [Complete Guide to JS Async & Await ES2017/ES8](https://www.youtube.com/watch?v=krAYA4rvbdA)
