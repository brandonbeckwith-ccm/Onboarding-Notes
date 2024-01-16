#JS 
![](https://www.youtube.com/watch?v=SrNQS8J67zc)

[Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator) are a very interesting concept. Explore in addition to `async` / `await`
- They are essentially a way to keep generating *something* by yielding.
- Just a fancy syntax for a proto-object that initializes and basically supplies `next()`
[Async / Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) are a way to run asynchronous code while retaining some synchronicity. 
* Async is applied to functions, await is applied to [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* This allows you to offload non-critical / bulky operations to when the event loop is finished with the main path of execution (normally setting everything up!)
	* As an aside, the event loop also handles input, but this won't be blocked by long running functions.