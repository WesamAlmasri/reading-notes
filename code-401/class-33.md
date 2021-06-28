# Context API

![Context API](https://miro.medium.com/max/2560/1*Yo1nkzOAMihE8Ia5O411PQ.jpeg)

## Review, Research, and Discussion

- Describe use cases for `useMemo()` and `useReducer()`

`useReducer` can be used for complex data objects that you need to update different properties within. `useMemo` memoizes a value, saving it to the cache and not running it again during re-renders unless the value changes.

- Why do custom hooks need the use prefix?

It's a convention, and without it react wouldn't be able to automatically check for violations of rules of hooks.

- What do custom hooks usually do?

Extract component logic into reusable functions

- Using any list of custom hooks, research and name one that you think will be useful in your applications

`useWebSocket` would be useful when building a real time web app that needs to communicate with a websocket api.

- Describe how a hook that fetches API data might work.

We could abstract the logic for fetching the data into a custom hook then call that in useEffect for example on multiple pages if they all need access to data from that api cal

## Terms

**reducer**: Is a function that determines changes to an application's state. It uses the action it receives to determine this change.

## Context API

Context provides a way to pass data through the component tree without having to pass props down manually at every level.

When to Use Context Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language. 
Using context, we can avoid passing props through intermediate elements:

Before You Use Context Context is primarily used when some data needs to be accessible by many components at different nesting levels. Apply it sparingly because it makes component reuse more difficult.

If you only want to avoid passing some props through many levels, component composition is often a simpler solution than context.
