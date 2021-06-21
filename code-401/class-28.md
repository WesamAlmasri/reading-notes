# Component Composition

![Component Composition](https://res.cloudinary.com/practicaldev/image/fetch/s--uhp38MJ0--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://thepracticaldev.s3.amazonaws.com/i/1cjigsdjmgz5j8lohlch.png)

## Review, Research, and Discussion

1. Can a parent component access the state of a child component?

Yes they can by using Refs. Assign Refs for the child component in the parent component, then using Refs can access the child's state. Refs are created using `React.createRef()` and attached to React elements via the ref attribute
2. What can be passed along in a prop variable?

Any data, object, function, JavaScript that needs to be passed down.
3. How can a child component “know” the state of another component?

To obtain the state of another component, you can pass the component's state to it's child components as props. You can also have components share a common ancestor, and have them access the same state in a similar manner.

## Terms

**Component Props**: Keyword in React for properties, can be any information, function, JavaScript that needs to be passed to another component. Can only be passed in one direction, from the root to its children, no way for data to be passed up.

**Component State**: React components have built in state object, which is where you store property values that belong to the component. When the state object changes, the component re-renders.

**Application State**: In an application, state is interface between data (from backend or local change) and the representation of this data with UI elements on the front-end. State is able to keep the data of different components in sync because each state update will re-render all relevant components. State can be a medium to communicate between different components as well.

## props.children

`this.props.children` is used to display whatever you include between the opening and closing tags when invoking a component.

Here’s an example of a stateless function that is used to create a component. Again, since this is a stateless function, there is no 'this' keyword so just use props.children

```js 
const Picture = (props) => {
  return (
    <div>
      <img src={props.src}/>
      {props.children}
    </div>
  )
}
```

This component contains an `<img>` that is receiving some `props` and then it is displaying `{props.children}`.

Whenever this component is invoked `{props.children}` will also be displayed and this is just a reference to what is between the opening and closing tags of the component.

```js
//App.js
render () {
  return (
    <div className='container'>
      <Picture key={picture.id} src={picture.src}>
          //what is placed here is passed as props.children  
      </Picture>
    </div>
  )
}
```

Instead of invoking the component with a self-closing tag `<Picture />` if you invoke it will full opening and closing tags `<Picture> </Picture> `you can then place more code between it.

This de-couples the `<Picture>` component from its content and makes it more reusable.

## Composition vs Inheritance

React has a powerful composition model, and we recommend using composition instead of inheritance to reuse code between components.

Props and composition give you all the flexibility you need to customize a component’s look and behavior in an explicit and safe way. Remember that components may accept arbitrary props, including primitive values, React elements, or functions.

If you want to reuse non-UI functionality between components, we suggest extracting it into a separate JavaScript module. The components may import it and use that function, object, or a class, without extending it.
