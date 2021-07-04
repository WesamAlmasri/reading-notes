# Redux - Combined Reducers

![Redux - Combined Reducers](https://www.cronj.com/blog/wp-content/uploads/New-Project.png)

## Review, Research, and Discussion

- Why choose Redux instead of the Context API for global state?

In a large scale application, Redux is a better way to control state.

- What is the purpose of a reducer?

Buffer that sits and protects the application state, changes to state by the components have to be passed through the reducer and have to play by the reducers rules. Reducer is a function that runs every time state needs to be updated, and always returns the new state of the application.

- What does an action contain?

Object literals that tell the reducer what is being done to the app, and any data required for the update.

- Why do we need to copy the state in a reducer?

Reducers are not allowed to modify the existing state, instead they must make immutable updates by copying the existing state and making changes to the copied values.

## Terms

- **Immutable state**: State cannot be modified, reducers must make copies of existing state to make updates.
- **Time travel in Redux**: Redux DevTools records dispatched actions and the state of the Redux store at every point in time, which makes it possible to inspect the state and travel back in time to a previous application state without reloading the page or re-starting the app.
- **Action Creator**: Instead of creating action objects inline in the places where you dispatch actions, can create functions generating them. You might write an action creator into a separate file, and import it into your component.
- **Reducer**: Functions that take current state and an action as arguments, and return a new state result, `(state, action) => newState`.
- **Dispatch**: A store holds the whole state tree of the application, the only way to change the state inside it is to dispatch an action on it.

## Multiple Reducers Example

- `import {combineReducers, createStore } from 'redux';`
- Example reducer: `const userReducer = (state={}, action) => { return state };`
- Example combineReducer example: `const reducers = combineReducers({user: userReducer, tweets: tweetReducer})`

## Using Combined Reducers

- Takes an object of reducer functions and returns a new reducer function
- `createStore` function takes `preloadedState` as a second argument

## Combined Reducer Syntax

- Reducers passed to `combineReducers` must satisfy the following:
  - any action that is not recognized, must return state that was given as first argument
  - must never return undefined
  - if `state` given to it is undefined, must return initial state for the specific reducer
