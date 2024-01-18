#JS 
[Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures) are a design pattern that's relatively common in JavaScript. They consist of a function with variable(s) declared inside of them that are then referenced in another function that's returned. This allows them to access a variable shared between calls because it's in *scope*. 

```js
function example() {
	const name = "cat"; // Decalred here
	function display() {
		console.log(name); // Able to be referenced here
	}
	display(); // Actually prints cat
} 

example() // Calls example
```

Knowing this we can do some pretty interesting things like create [[Debounce and Throttle]] functions. These types of functions generate a function that when called can update a variable kept in memory due to it still being in scope. To make this clearer let's use an example.

```js
function createCounter() {
	let currentCount = 0 // This will be kept 'alive' inside the function we return
	function getCount() {
		currentCount++; // Update the value then return
		return currentCount;
	}
	return getCount
}

const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2

const anotherCounter = createCounter();
console.log(counter()); // 3
console.log(anotherCounter()); // 1
```