# Redux, Reducers and Middleware
Redux provides us with a Store which holds our state, and a Dispatch for triggering actions, and Reducers for updating our state tree.

## Container

The container is the glue that connects react to redux. It connects it in a lot of ways. This is where the react-redux module is used and I usually call that connect as that is what I use it for. It takes three arguments, an object that maps state to props — mapStateToProps, an object that maps actions to dispatch (these are used to wire events to actions) — mapActionsToDispatch, and mergeProperties merges all the properties together and passes them to react for rendering.

## Action & Action Creator

- Action: This is an object that contains the type of action and the state that was changed because of the action.

-Action Creator: This is the code that is called to create an action and send it along to the reducer.

## Reducers

- JavaScript functions that take in a state and an action, and return a new state. 
- Reducers are pure functions: they don't rely on or modify any global state, so they're easy to test, reason about, and refactor.
- Must be synchronous. They return the new state.

## Store

- Subscribe to state changes in the store and dispatch actions

## Middleware

- Middleware function is a function that returns a function that returns a function.  i.e: a curried function
- The middleware sits in between the dispatch and reducers, which means we can alter our dispatched actions before they get to the reducers or execute some code during the dispatch.
- Receives a store, then returns a function that receives a next function and returns another function that receives an action.
- Middleware should be responsible for any interactions that affect global state (like setInterval()) or any asynchronous operations (like HTTP requests).
- redux middleware is redux-thunk which allows you to write action creators that return a function instead of an action.

<img src="https://cdn-images-1.medium.com/max/1600/1*HdW9EAF92r__hgFINFGYSw.png">

### Any asynchronous behavior or global state modifications should go through middleware, so your reducers can be pure functions. 

```
const customMiddleware = store => next => action => {
  ...
}
```

#### The Store: That’s our redux store.

#### The Next: We call this function when our middleware is done with the task assigned to do. This sends our actions to our reducer or another middleware.

#### The Action: Thats our action currently being dispatched.

Greate resource + read : <a href="https://medium.com/netscape/creating-custom-middleware-in-react-redux-961570459ecb">https://medium.com/netscape/creating-custom-middleware-in-react-redux-961570459ecb</a>
