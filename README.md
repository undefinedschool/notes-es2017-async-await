# [WIP] ✨ ES2017: Async/Await

Una de las principales desventajas de manejar asincrinismo en JavaScript, es que muchas veces resulta algo complejo razonar o seguir el flujo de las diferentes operaciones, principalmente porque estamos más acostumbrados a pensar de forma _sincrónica_.

Es por esto que en la versión [ES2017](https://medium.com/@tmvvr/ecmascript-async-await-to-the-rescue-fc379ff89146) de JavaScript se incorporó una nueva forma de trabajar con código asincrónico, `async/await`.

`async/await` nos permite _pausar_ la ejecución de funciones asincrónicas, para poder escribir código _asincrónico_ que se lea como código _sincrónico_ y resulte de esta forma, más legible y simple de razonar.

> 👉 `async/await` no deja de ser _sugar syntax_ (es decir, una forma más simple de escribir) sobre [_Promises_](https://github.com/undefinedschool/notes-es6-promises/)

## Async

Al agregar `async` delante de cualquier función, esta pasa automáticamente a retornar una promesa al valor original que retornaba antes. Por ejemplo, si tenemos

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
