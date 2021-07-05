# Redux - Asynchronous Actions

## Review, Research, and Discussion

1. How granular should your reducers be?

It is difficult to manage states that are deeply nested, so more reducers is better than only a few. Redux gives us combineReducers to let us define more precisely what our initial state will look like.

2. Pro or Con – multiple reducers can “fire” when a commonly named action is dispatched

Pro: you can make multiple state logic to listen to some common action

Con: You have import the action in the reducers files, so the separation of concern approach is minimum

3. Name a strategy for preventing the above

Using Redux middleware thunk, allows for evaluating the actions.

## Terms

- **Store**: Holds the whole state tree of the application, only way to change the state inside is to dispatch an action on it.
- **Combined Reducers**: Helper function turns an object whose values are different reducing functions into a single reducing function you can pass to createStore.

## async actions

- Redux middleware enables writing logic with side effects
- Redux `Thunk` middleware allows us to write functions that get dispatch and getState as arguments
- `$npm install redux-thunk`
- `import thunkMiddleware from 'redux-thunk'`
- `const composedEnhancer = composeWithDevTools(applyMiddleware(thunkMiddleware))`

## thunk middleware

- Allows you to write action creators that return a function instead of an action
- Can be used to delay dispatch or conditionally dispatch
- "The term originated as a humorous past-tense version of 'think'."
- `import { createStore, applyMiddleware } from 'redux';`
