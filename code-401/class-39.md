# Redux - Additional Topics

![Redux](https://i.morioh.com/200529/aec01012.jpg)

## Review, Research, and Discussion

1. What’s the best practice for “pre-loading” data into the store (on application start) in a Redux application?

Can use a `useEffect()` hook to dispatch an async action which load data on application start.

2. When using a thunk/async action that dispatches the actual action, which do you export from your reducer?

We export the actual action from the reducer.

## Terms

- **Middleware**: Code you put in between the framework receiving a request and the framework generating the response.
- **Thunk**: Function that wraps an expression to delay its evaluation.

## Redux Toolkit (RTK)

- `configureStore()` provides simplified config options, combine slice reducers, adds Redux middleware, includes Redux-thunk
- `createReducer()` supply a lookup table of action types to case reducer functions, uses `immer` library to let you write simpler immutable updates
- `createAction()` generates an action creator function for the given action type string
- `createSlice()` accepts an object of reducer functions, a slice name, and an initial state value, creates a slice reducer with corresponding action creators and action types
- `createAsyncThunk` accepts an action type string and a function that returns a promise, generates a thunk that dispatches action based on promise
- `createEntityAdaptor` generates set of reusable reducers adn selectors to manage normalized data in the store
- `createSelector` utility from `Reselect` library re-exported for ease of use
- `npm install @reduxjs/toolkit`
