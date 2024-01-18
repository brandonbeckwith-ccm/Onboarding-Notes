#JS 
[Async / Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) are a way to run asynchronous code while retaining some synchronicity. 

### `async function () {}`
This way of declaring a function creates a binding in memory and allows [[Promises]] based behavior to be written in a nicer, easier to read way.

```js
async function() {
	// We're missing something
}
```

### `await`
Is a *keyword* used inside an `async function` that allows for sequential, `Promise` based execution. Say for example you wanted to `alert` a user after **n** seconds. You could do this with a `Promise` like so:

```js
const promise = new Promise((resolve) => {
	setTimeout(() => {
		resolve(`Fancy user message`)
	}, n)
}).then(console.log(resolved))

```

The way `.then` is used is unintuitive in terms of execution order and just helps to make more of a mess of things. Let's rewrite with `async await`

```js
const promise = new Promise((resolve) => {
	setTimeout(() => {
		resolve(`Fancy user message`)
	}, n)
})

const message = await promise

console.log(promise)
```

Same functionality, but is presented in a more familiar flow. But what about errors? Simply use a `try catch` block.

```js
	const promise = new Promise(...)
	
	try {
		const resolved = await promise
		doSomething(resolved)
	} catch (rejected) {
		console.log(`Error: ${rejected}`)
	}
	
```

This avoids having to chain `.catch` onto `Promises` or even worse, chains of `Promises`!

The behavior of `async await` is the same as how `Promises` function, the only difference is the syntax. This makes `async await` #SyntaticSugar!
