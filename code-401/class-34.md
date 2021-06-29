# `<Login />` and `<Auth />`

![ auth ](https://www.ilantus.com/wp-content/uploads/2019/07/authentication-vs-authorization1-thegem-blog-default.png)

## Review, Research, and Discussion

- Why is the Context API useful?

Context API is useful because it can help to make information globally available in the app rather than having to pass it in props to each individual child element.

- Can a component outside of a provider get its context?

No, the component should be inside the app can.

- What are some common use cases for using the Context API?

Needing to pass functions that need to be available in multiple places.

- Describe “Context Hell” 

It some thing related to have too many nested contexts.

## Terms

- **Global state:** state that is accessible at the top level of the app and passed via props
- **Global context**: context that is passed from the app.js component and is available to all child components
- **Provider**: React uses provider pattern in Context API to share data across tree descendants
- **Consumer**: consumer takes a child as a function and that function returns a node

## what is role based access control?

- It restricts network access based on a person's role within an organization
- You can designate management or employee roles that allow certain privileges.
- Having roles reduces administrative work, as a new employee can be assigned automatically by job title/function, and can decrease unnecessary access to sensitive information/documents.

## react-cookies component

React component library that help to save cookies;
