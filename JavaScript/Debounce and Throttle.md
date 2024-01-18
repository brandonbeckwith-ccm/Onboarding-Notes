[Debounce](https://www.joshwcomeau.com/snippets/javascript/debounce/) and [Throttle](https://www.geeksforgeeks.org/javascript-throttling/) are techniques used to limit the number of requests / inputs sent / received. These are *asynchronous* in nature. These functions make extensive use of [[Closures]] in order to function correctly.
### Debounce
Delays an action / request for a period of time before sending it. If another call is made the previous request is canceled and the next call is scheduled.

```js
const debounce = (callback, wait) => {
  let timeoutId = null; // Holds a timer
  
  return (...args) => { // Passes all arguments to the callback function
    window.clearTimeout(timeoutId); // Clear the previous timeout
    timeoutId = window.setTimeout(() => {
      callback.apply(null, args); // Call the callback
    }, wait);
  }; // Returns a function that when called will execute the callback after a peroid of time
}
```

### Throttle
Limits the number of times a request can be made during a period of time.
// Add code later