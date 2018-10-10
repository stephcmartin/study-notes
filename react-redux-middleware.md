Redux, Reducers and Middleware
Redux provides us with a Store which holds our state, and a Dispatch for triggering actions, and Reducers for updating our state tree.

Reducers: 
- JavaScript functions that take in a state and an action, and return a new state. 
- Reducers are pure functions: they don't rely on or modify any global state, so they're easy to test, reason about, and refactor.
- Must be synchronous. They return the new state.

Store:
- Subscribe to state changes in the store and dispatch actions

Middleware:
- Middleware function is a function that returns a function that returns a function.  i.e: a curried function
- The middleware sits in between the dispatch and reducers, which means we can alter our dispatched actions before they get to the reducers or execute some code during the dispatch.
- Receives a store, then returns a function that receives a next function and returns another function that receives an action.
- Middleware should be responsible for any interactions that affect global state (like setInterval()) or any asynchronous operations (like HTTP requests).
- redux middleware is redux-thunk which allows you to write action creators that return a function instead of an action.

<img src="https://cdn-images-1.medium.com/max/800/1*BqYWetCfpVNYhDX9fez0Mg.png">

Any asynchronous behavior or global state modifications should go through middleware, so your reducers can be pure functions. 