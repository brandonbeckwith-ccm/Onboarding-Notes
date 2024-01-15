![JavaScript Debugging](https://www.youtube.com/watch?v=TtsvMRxmfGA)

* Reproduce bugs in a test.
	* Helps ensure you squish and prevents it returning
## Console Log
* Adding {} around variables can help expose more information when logging
* There's a [`console.*`](https://developer.mozilla.org/en-US/docs/Web/API/console) library to make things things easier
	* `console.group`: Groups variables together
	* `console.table`: Outputs a table
	* `console.trace`: Shows the stack
	* `console.dir`: Inspect a dom element as an object
* Also don't forget about `*$*`, it exposes values in console when inspecting with developer tools
## Debugging
* The `debugger;` keyword essentially inserts a breakpoint into the JS code for use in the browser.
	* Good to know, you should probably just link the browser to your ID
	* Also good for #API calls
* You can use **Break On** to change when the debugger stops