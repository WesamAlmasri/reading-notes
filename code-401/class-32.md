# Custom Hooks

![Custom Hooks](https://diarybydhanushka.dev/wp-content/uploads/2020/02/custom-hooks.png)

## Review, Research, and Discussion

- What does a component’s lifecycle refer to?

Lifecycle of a component is series of methods that are invoked in different stages of the component's existence. Lifecycle methods give ways to interact with component logic before/during/after being used in the DOM. 

- Why do you sometimes need to “wrap” functions in useCallback when called from within `useEffect`

`useCallback()` is often used in conjunction with `useEffect()` because it allows you to prevent the re-creation of a function.

- Why are functional components preferred over class components?

Functional components are much easier to read and test, they have less code, easier to separate container and presentational components. 

- What is wrong with the following code?

The `renderedItems` array should be in state so that it can preserve its value between renders

The `useEffect` placed inside a for loop which contradicts hooks rules.

```js
import React, {useState, useEffect} from 'react';

function MyComponent(props) {
  const [count, setCount] = useState(0);

  function changeCount(e) {
    setCount(e.target.value);
  }

  let renderedItems = []

  for (let i = 0; i < count; i++) {
    useEffect( () => {
      console.log('component mount/update');
    }, [count]);

    renderedItems.push(<div key={i}>Item</div>);
  }

  return (<div>
     <input type='number' value={count} onChange={changeCount}/>
      {renderedItems}
    </div>);
}
```

## Terms

**State hook**: `useState()`, similar to `this.setState()` in a class except it doesn't merge the old and new state together. The only argument to `useState()` is the initial state. Allows us to add a state powered variable to our application.

**Effect hook**: `useEffect()`, adds the ability to perform side effects (data fetching, subscriptions, or manually changing the DOM from React components) from a function component. Serves the same purpose as `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` in React classes but unified into a single API. Allows us to define properties that will trigger or not trigger React API features.

**Reducer hook**: alternative to `useState()`, accepts a reducer of type `(state, action) =>` newState, and returns the current state paired with a dispatch method.

## Authoring

- `useEffect` tells react to do something after the render is complete and after every update
- `useEffect(()=>{document.title = 'You clicked ${count} times'});`
- Custom hooks are prefixed with the word `use`, normal function but follows the rules of creating a Hook
- Async hooks offers an example of how to code a fetch request to google books
- Async hooks cannot use async keyword with useEffect will create race condition
- Reducer takes in `(state, action)` and returns current state and a dispatch method
- Preferable when complex state logic or multiple sub-values or when state depends on previous
- When you want to share logic between two hooks, extract to a third hook
- Name must start with use
- State inside custom hooks is isolated
