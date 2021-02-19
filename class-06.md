# JS Object Literals: The DOM

![javascript image](https://res.cloudinary.com/practicaldev/image/fetch/s--f03DnZwI--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/y5xlip29lnylnfhmhwj8.png)

## Object Literals in JavaScript

**WHAT IS AN OBJECT**?

Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. In an object, variables and functions take on new names.

In an object: variables become known as properties and functions as methods

Literal notations is the easiest and most popular way to create objects. (There are several ways to create objects), an object literal is a comma-separated list of name-value pairs inside of curly braces.

Here’s a snippet of an object literal with one property and one function.

![objects literal image](https://camo.githubusercontent.com/86e440388a6c4f4e7617d50a55ffee261ebe90c5b699b1f90e56f791958109d7/68747470733a2f2f7170682e66732e71756f726163646e2e6e65742f6d61696e2d71696d672d62363737323933393664386463613031373532393663653834383333653138632e77656270)

```javascript
var greeting = {
    fullname: "Michael Jackson",
    greet: function(message, name) {
        console.log(message + " " + name + "!!");
    }
}
```

However, you can create a function (e.g. getFullName())that accesses the fullname value using the **this** keyword, which is just the current object context.

```javascript
var greeting = {
    fullname: "Michael Jackson",
    getFullName: function() {
     return this.fullname;
    },
    greet: function(message, name) {
        console.log(message + " " + this.getFullName() + "!!");
    }
```

All members of an object literal in JavaScript, both properties and functions, are public. The only place you can put private members is inside of a function.

**Accessing an object and dot notation**:

You access the properties or methods of an object using dot notation. You can also access properties using square brackets.

```javascript
var name = greeting.fullname;
var greetingText = greeting.greet("my message", "my name");
```

![Document Object Model image](https://i.ytimg.com/vi/l-0nPnSvbX8/maxresdefault.jpg)

## The HTML DOM (Document Object Model)

The Document Object Model (DOM) specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window.

As a browser loads a web page, it creates a model of that page. The model is called a DOM tree, and it is stored in the browsers' memory.

![dom tree image](https://camo.githubusercontent.com/acefb971831c19a570c8f2c55f5b4077bb11e26eebaa817c662fcb098407b3b2/68747470733a2f2f7777772e77337363686f6f6c732e636f6d2f6a732f7069635f68746d6c747265652e676966)

With the object model, JavaScript gets all the power it needs to create dynamic HTML:

- JavaScript can change all the HTML elements in the page
- JavaScript can change all the HTML attributes in the page
- JavaScript can change all the CSS styles in the page
- JavaScript can remove existing HTML elements and attributes
- JavaScript can add new HTML elements and attributes
- JavaScript can react to all existing HTML events in the page
- JavaScript can create new HTML events in the page

### WORKING WITH THE DOM TREE

#### STEP 1: ACCESS THE ELEMENTS

**SELECT AN INDIVIDUAL ELEMENT NODE**:

Here are three common ways to select an individual element:

`get El ement Byld ()`: Uses the value of an element's id attribute (which should be unique within the page).

`querySe 1 ector ()`: Uses a CSS selector, and returns the first matching element.

**SELECT MULTIPLE ELEMENTS (NODELISTS)**:

There are three common ways to select multiple elements.

`getElementsByClassName()`: Selects all elements that have a specific value for their class attribute.

`getElementsByTagName()`: Selects all elements that have the specified tag name.

`querySelectorAll()`: Uses a CSS selector to select all matching elements.

**TRAVERSING BETWEEN ELEMENT NODES**:

You can move from one element node to a related element node.

`parentNode`: Selects the parent of the current element node (which will return just one element).

`previousSibling / nextSibling`: Selects the previous or next sibling from the DOM tree.

`firstChild / lastChild`: Select the first or last child of the current element.

The terms **elements** and **element nodes** are used interchangeably but when people say the DOM is working with an element, it is actually working with a node that represents that element.

#### STEP 2: WORK W ITH THOSE ELEMENTS

**ACCESS/ UPDATE TEXT NODES**:

`nodeValue`: This property lets you access or update contents of a text node.

**WORK WITH HTML CONTENT**:

One property allows access to child elements and text content: `innerHTML`. Another just the text content: `textContent`

Several methods let you create new nodes, add nodes to a tree, and remove nodes from a tree: `createElement()`, `createTextNode()`, `appendChild()` / `removeChild()`. This is called **DOM manipulation**

**ACCESS OR UPDATE ATTRIBUTE VA LUES**:

Here are some of the properties and methods you can use to work with attributes: `className` /`id`. Lets you get or update t he value of the class and id attributes.

`hasAttribute()`, `getAttribute()`, `setAttri bute()`, `removeAttribute()`. The first checks if an attribute exists. The second get s its value. The third updates the value. The fourth removes an attribute.

Methods that find elements in the DOM tree called DOM queries. When you need to work with an element more than once, you should use a variable to store the results of this queries. It really srore the location of the element(s) within the DOM tree in a variable. The properties of that element node work on the variable.

```javascript
var itemOne = getElementById('one');
```

DOM queries may return one element, or they may return a Nodelist, which is a collection of nodes.

There are two ways to select an element from a **NodeList**:

1. The `item()` method:

    ```javascript
    var elements = document.getElementsByClassName('hot');
    if (elements.length>= 1) {
    var firstltem = elements.item(O);
    }
    ```

2. Array syntax: This is preferred over the item method because it is faster.

    ```javascript
    var elements = document.getElementsByClassName('hot');
    if (elements.length>= 1) {
    var firstltem = elements.[O];
    }
    ```

Both methos require the index of the element you want.

Here is some example to select elements.

```javascript
var elements = document .getElementsByClassName('hot'); // Find hot items
if (elements .length> 2) { // If 3 or more are found
var el = elements[2];    // Select the third one from the Nodelist
el.className = 'cool';  // Change the value of its class attribute
}
```

```javascript
var elements = document.getElementsByTagName('li '); // Find <li> elements
if (elements .length> 0) { // If 1 or more are found
var el = elements[0];    // Select the first one using array syntax
el.className = 'cool';  // Change the value of its class attribute
}
```

```javascript
// querySelector() only returns the first match
var el = document.querySelector('li.hot'};
el.className = 'cool';
// querySelectorAll returns a Nodelist
// The second matching element (the t hird list item) is selected and changed
var els = document .querySelectorAll('li.hot');
els[1].className = 'cool';
}
```

### LOOPING THROUGH A NODELIST

If you want to apply the same code to numerous elements, looping through a Nodelist is a powerful technique.

```javascript
var hotItems = document.querySelectorAll('li.hot'); // Store Nodelist in array
if (hotItems.length > O) { // If it contains items
for (var i=O; i<hotl tems.length; i++) { // Loop through each item
hotltems[i ] .className = 'cool'; // Change value of class attribute
```

### RAVERSING THE DOM

When you have an element node, you can select another element in relation to it using these five properties. This is known as traversing the DOM.

`parentNode`: This property finds the element node for the containing (or parent) element in the HTML.

`previousSibling`, `nextSibling`: These properties find the previous or next sibling of a node if there are siblings.

`firstChild`, `lastChild`: These properties find the first or last child of the current element.

```html
<ul><li id="one" class="hot"><em>fresh<em> figs </i><li id="two"
class="hot">pine nuts</li><li id="three" class ="hot">honey</li><li
id="four">balsamic vinegar</li></ul>
```

```javascript
// Select the starting point and find its siblings
var startItem = document.getElementByid('two');
var prevItem = startltem.previousSibling;
var nextItem = startitem.nextSibling;
// Change the values of the siblings' class attributes
prevltem.className = 'complete';
nextltem.className = 'cool';
```

```html
<ul>
    <li id="one" class="hot"><em>fresh </em>figs</li>
    <li id="two" class="hot">pine nuts</li>
    <li id="three" class="hot">honey</li>
    <li id="four"">balsamic vinegar</li>
</ul>
```

```javascript
// Select the starting point and find its children
var startltem = document.getElementsByTagName('ul')[O] ;
var firstltem = startltem.firstChild;
var lastltem = startitem.lastChild;
// Change the values of the children's class attributes
firstltem.setAttribute('class', 'complete');
lastitem.setAttribute('class', 'cool');
```

The document object's `write()` method is a simple way to add content that was not in the original source code to the page, but its use is rarely advised.

`Element.innerHTML`: The innerHTML property lets you get/update the entire content of any element (including markup) as a string.

If you add HTML to a page using `innerHTML` (or several jQuery methods), you need to be aware of Cross-Site Scripting Attacks or XSS; otherwise, an attacker could gain access to your users' accounts.
