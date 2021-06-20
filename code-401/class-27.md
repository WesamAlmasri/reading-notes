# Props and State

![Props and State](https://res.cloudinary.com/practicaldev/image/fetch/s--IeH7-Hx3--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/http://live-linguine-code.pantheonsite.io/wp-content/uploads/2019/03/react-state-vs-props.jpg)

## Review, Research, and Discussion

1. Does a deployed React application require a server?

Don't necessarily need a static server in order to run a React app project in production, it works well when integrated into an existing server side app.

2. Why do we prefer to test a React application at the behavior rather than the unit level?

Want to write tests for the applications behavior, not the implementation of the behavior. Implementation can change but behavior doesn't change that fast. By testing behavior, you won't have to adjust after each minor code change.

3. What does npm run build do?

When you're ready to deploy to production, running npm run build will create an optimized build of your app in the build folder

4. Describe the actual composition / architecture of a React application

React application is split into components, it is important that you can add functionality to a component without causing rippling changes through the codebase

## Terms

**BDD**: Behavior driven development, a branch of Test Driven Development (TDD), which uses human-readable descriptions of software user requirements as the basis for software tests.

**Acceptance**: Tests: testing technique performed to determine whether or not the software system has met the requirement specifications, the main purpose is to evaluate the system's compliance with the business requirements and verify if it is has met the required criteria for delivery to end users. Forms of acceptance testing: user acceptance testing, business acceptance testing, alpha testing, beta testing.

**Mounting**: Process by which the operating system makes files and directories on a storage device available for users to access via the computer's file system.

**Build**: Process of converting source code files into standalone software artifacts that can be run on a computer.

## setState

- Article from CSS-tricks
- Update to a component state should be done using setState()
- You can pass an object or a function to setState()
- Pass a function when you can to update state multiple times
- Do not depend on this.state immediately after calling setState() and make use of the updater function instead.

## Handling Events

- Handling events with React elements is very similar to handling events on DOM elements
- There are some syntax differences: React events are named using camelCase rather than just lowercase, and with JSX you pass a function as the event handler rather than a string
- You cannot return false to prevent default behavior in React, you must call preventDefault explicitly

## Forms

- HTML form elements work a little bit differently from other DOM elements in React, because form elements naturally keep some internal state
- In HTML, form elements such as input, textarea, and select typically maintain their own state and update it based on user input
- In React, mutable state is typically kept in the state property of components, and only updated with setState()
- Can combine the two by making the React state be the “single source of truth”. Then the React component that renders a form also controls what happens in that form on subsequent user input. - An input form element whose value is controlled by React in this way is called a “controlled component”.

## State and Lifecycle

- Can declare special methods on the component class to run some code when a component mounts and unmounts, these methods are called "lifecycle methods"
- Three things to keep in mind about setState():
  - Do not modify state directly, instead use setState(), the only place you can assign this.state is the constructor
  - State updates may be asynchronous
    - React may batch multiple setState() calls into a single update for performance
    - Because this.props and this.state may be updated asynchronously, you should not rely on their values for calculating the next state
  - State updates are merged, when you call setState() React merges the object you provide into the current state
- The data flows down, neither parent nor child components can know if a certain component is stateful or stateless, and they shouldn’t care whether it is defined as a function or a class
- This is why state is often called local or encapsulated. It is not accessible to any component other than the one that owns and sets it
- A component may choose to pass its state down as props to its child components

## Components and Props

- Components let you split the UI into independent, reusable pieces, and think about each piece in isolation
- Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.
- Components can refer to other components in their output
- Whether you declare a component as a function or a class, it must never modify its own props
- All React components must act like pure functions (do not attempt to change their inputs and always return the same result for the same inputs) with respect to their props
