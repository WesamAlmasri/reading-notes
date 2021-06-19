# Component Based UI

![Component Based UI](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR97GJJVfhO-RJFF6Cc4CrXw76fBCKFsk-E6w&usqp=CAU)

## Review, Research, and Discussion

1. Name 5 Javascript UI Frameworks (other than React)
    - Angular
    - Vue
    - Ember
    - Svelte 3
    - Ext JS

2. What’s the difference between a framework and a library?

The technical difference lies in a term called inversion of control. When you use a library you are in charge of the flow of the application ( you are choosing when and where to call the library), but when you use a framework it is in charge of the flow (provides some places for you to plug in your code but it calls the code you plugged in as needed).

## Terms

**Rendering**: Javascript uses the document object model (DOM) to manipulate the DOM elements. Rendering refers to showing the output in the browser.

**Templates**: Templating refers to the client side data binding method implemented with the JavaScript language. Popular JavaScript templating languages are: AngularJS, Backbone.js, Ember.js, Handlebars.js, and Mustache.js. The templating engine is responsible for connecting to the data model, processing the code specified in the source templates, and directing the output to a specific pipeline, text file, or stream.

**State**: Describes the status of the entire program or an individual object, could be text, a number, a boolean, or another data type. It is a common tool for coordinating code, for example, once you update state a bunch of different functions can instantly react to the change.

## React

![react](https://cdn.hackernoon.com/hn-images/1*HSisLuifMO6KbLfPOKtLow.jpeg)

React is a JavaScript library for building user interfaces, it is used to build single page applications and allows us to create reusable UI components.

## JSX

JSX stands for JavaScript XML. JSX allows us to write HTML in React and makes it easier to write and add HTML in React.

Below some definitions and additional information about JSX:

- JSX is a syntax extension to JavaScript, it produces React "elements"
- React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display
- React separates concerns with loosely coupled units called "components" that contain both markup and logic
- Can put any valid JavaScript expression inside the curly braces in JSX (2+2, user.firstName, or formatName(user) for example)
- JSX is an expression too, after compilation JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects
- Can use JSX inside of if statements and for loops, assign it to variables, accept it as arguments and return it from functions
- Use quotes to specify string literals as attributes
- Can also use curly braces to embed a JavaScript expression in an attribute
- If a tag is empty, you can close it immediately with />
- By default, React DOM escapes any values embedded in JSX before rendering them, thus it ensures that you can never inject anything that's not explicitly written in your application
- Babel compiles JSX down to React.createElement() calls
- Can think of React elements as descriptions of what you want to see on the screen, React reads these objects and uses them to construct the DOM and keep it up to date

## Rendering Elements

Below some information about react elements, components and rendering elements:

- Elements are the smallest building blocks of React apps, an element describes what you can see on the screen
- Unlike browser DOM elements, React elements are plain objects, and are cheap to create
- React DOM takes care of updating the DOM to match the React elements
- Elements are what components are made of
- Example: A `<div>` on the page is referred to as a root DOM node because everything inside it will be managed by React DOM
- Applications built with just React usually have a single root DOM node
- If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you'd like
- React elements are immutable, once you create an element you can't change its children or its attributes
- An element is like a single frame in a movie, it represents the UI at a certain point in time
- React only updates what is necessary, React DOM compares the element and its children to the previous one and only applies the DOM updates necessary to bring the DOM to the desired state
