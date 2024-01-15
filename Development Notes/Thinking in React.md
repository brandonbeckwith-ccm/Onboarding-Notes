# [Thinking in React](https://react.dev/learn/thinking-in-react)
- Handling DOM, routing, states, etc...
- Contract between DB and UI
	- Know the mapping between the two to be able to build without having the backend ready.
1. Break UI into hierarchy
	- Logical, reasonable ordering
	- CSS can be done directly in line or with a styles file
	![[Pasted image 20240115131519.png]]
2. Create a static version, nothing dynamic just a layout
3. Find the minimal, but complete representation of UI state
	1. Keep it #DRY (Don't Repeat Yourself)
	2. Avoid using stateful variables when unneeded
		1. Reactive objects are held in the state. 
		2. Computed variables, passed values, unchanged, etc...
4. Where should State *live*?
	1. A lot of #Vue state will be baked into local state, IE #ref
	2. Having state at the top level is the least troublesome
		1. Data flows down into components
		2. Children request parents to update state, not directly update
			1. This can be done by passing a callback function from the parent to the child
		3. Parents are the single source of truth
	3.  Structure components so each component can be reused.