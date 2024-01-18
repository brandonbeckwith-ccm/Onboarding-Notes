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
* **Blackbox Script** is a good way to exclude code from getting debugged.
* **Logpoint** essentially adds `console.log()`, but without needing to remove it after
*  [**Snippets and Live Expressions**](https://developer.chrome.com/docs/devtools/javascript/snippets) are another good tool to watch values and share code.
* **Sources -> Workspaces** used to save changes made in the browser.
	* You could use this as an IDE... but you probably shouldn't lol. 
* **Proxy Overrides** allow you to override remote code with local. 
	* [Resource Override](https://chromewebstore.google.com/detail/resource-override/pkoacgokdfckfpndoffpifphamojphii) is a Chrome extension that achieves this. 
	* Great way to skip setting up environments for quick fixes
* **Source-map** make debugging easier (especially if you're using typescript!) by mapping sources to what's in the browser.
	* You can deploy this to production, they only get downloaded when DevTools are opened.
* You can debug node in chrome. Just need to set a flag.
* [Vue Browser Debugger](https://devtools.vuejs.org/)
## Performance Debugging
* Flamecharts show execution times, a lot of calls come from frameworks
	* You can go all the way down to function level
* Use [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview) to do a performance audit.
## Accessibility Debugging
* Ensure that names are set so screen readers have context.
* You need to probably run accessibility tests.