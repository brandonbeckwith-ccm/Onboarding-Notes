#JS 
![[Pasted image 20240117120244.png]]
[Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) are a key part of asynchronous code execution. They allow you to differ code that may not immediately return / take a long time or is dependent on something else for execution.
```
The **`Promise`** object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.
```

### Constructing
Promises are constructed like every other object. They take a an `executor` function that is responsible for handling success / failure and returning a `value`.

```js
const iPromise = new Promise((resolve, reject) =>{
	// Do something async here
	if (bad) {
		reject(someValue)
	} else {
		resolve(someValue)
	}
})
```

The values passed to the `resolve` function are returned as a result that can be acted on using `.then(returnVal)`.

```js
iPromise.then((returnVal / result) => {
	// Do something
})
```

Values passed to `reject` on the other hand are used with `.catch` (similar to a try catch)

```js
iPromise.catch((error / returnVal / result) => {
	// Do something with the error
})
```

And you can chain these! This is because the return value of calling `.then` or `.catch` is another `Promise`. This means you can basically indefinitely chain logic together. However, this will quickly become unwieldy. A better solution would be to use [[Async Await]].

### Methods
1. [`Promise.all()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all): Returns a promise that completes when all `Promises`  passed `resolve`
2. [`Promise.allSettled()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/allSettled): Returns a promise that completes when all `Promises` passed are `resolved` or `rejected` 
3. [`Promise.any()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/any): Returns a promise that completes when any of the `Promises` passed `resolve`
4. [`Promise.prototype.catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch): Catches thrown errors. See above
5. [`Promise.prototype.finally()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/finally): Calls a passed function after all `Promises` are settled (`resolved` / `rejected`)
6. [`Promise.race()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/race): Returns a `Promise` that settles with the state of the first `Promise` passed that settles.
7. [`Promise.reject()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/reject): Generates a `Promise` that is `reject` with a given reasons
8. [`Promise.resolve()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/resolve): `Resolves` a given value to a `Promise`
9. [`Promise.prototype.then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then): See above :)
10. [`Promise.withResolvers()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/withResolvers): Returns a Promise, and two functions that `resolve` or `reject` it.