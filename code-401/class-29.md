# Routing

## Review, Research, and Discussion

1. Do child components have direct access to props/state from the parent?

Child components have access to state from the parent (`this.state`) when in a class, and have access to props as a functional component.

2. When a component “wraps” another component, how does the child component’s output get rendered?

Gets rendered when there is an update to state.

3. Can a component, such as `<Content />`, which is a child also be used as a standalone component elsewhere in the application?

Yes if we made it as separate component and export it.

4. What trick can a parent use to share all props with it’s children

Can pass all the props with the spread operator: `<ChildComponent {...props}>`

## Terms

**props.children**: can be used on components that represent generic boxes and don't know their children ahead of time (per React docs). It can be used to display whatever you include between the opening and closing tags when invoking a component (source: Codeburst)

**Composition**: the act of combining parts or elements to form a whole, components are the UI building blocks in React applications like pure functions are the building blocks of function composition. (source: Medium)

## React Router v4

React Router v4 is a pure React rewrite of the popular React package. Previous versions of React Router used configuration disguised as pseudo-components and could be difficult to understand. With v4, everything is “just components”.

When starting a new project, you need to determine which type of router to use. For browser based projects, there are `<BrowserRouter>` and `<HashRouter>` components. The `<BrowserRouter>` should be used when you have a server that will handle dynamic requests (knows how to respond to any possible URI), while the `<HashRouter>` should be used for static websites (where the server can only respond to requests for files that it knows about).

Usually it is preferable to use a `<BrowserRouter>`, but if your website will be hosted on a server that only serves static files, then the `<HashRouter>` is a good solution.

For our project, we will assume that the website will be backed by a dynamic server, so our router component of choice is the `<BrowserRouter>`.
