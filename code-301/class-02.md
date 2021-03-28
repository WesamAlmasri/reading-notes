# jQuery, Events, and The DOM

![jqeuy image](https://www.webdesignerdepot.com/cdn-origin/uploads/2019/07/featured_jquery.jpg)

jQuery is Javascript file that you include in your web pages. It lets you find elements using CSS selectors and then do something with the element using jQuery methods.

## The .class Selector

The jQuery `.class` selector finds elements with a specific class.

To find elements with a specific class, write a period character, followed by the name of the class:

`$(".test")`

For Example:

```javascript
$(document).ready(function(){
  $("button").click(function(){
    $(".test").hide();
  });
});
```

Do something to elements using JQuery method like `addClass`

![jQuery methid using image](https://camo.githubusercontent.com/fbb6d95df94aeddc003b35fef40f1d530957621a3cd1d4e0ad7ccab76d5336b0/68747470733a2f2f7777772e6564756361746976652e696f2f6170692f656470726573736f2f73686f742f363130333738373838303035343738342f696d6167652f36303931373336333032343835353034)

Example:

```html
<h2>This is a heading</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<button>Click me to hide paragraphs</button>
```

```javascript
$(document).ready(function(){
  $("button").click(function(){
    $("p").hide();
  });
});
```

## Why JQuery

There are lots of other JavaScript libraries out there, but jQuery is probably the most popular, and also the most extendable.

Many of the biggest companies on the Web use jQuery, such as:

- Google
- Microsoft
- IBM
- Netflix

## Finding elements

| Selector        | Example             | Selects                                       |
| --------------- | ------------------- | --------------------------------------------- |
| `*`             | `$("*")`            | All elements                                  |
| `#id`           | `$("#lastname")`    | The element with id="lastname"                |
| `.class`        | `$(".intro")`       | All elements with class="intro"               |
| `.class,.class` | `$(".intro,.demo")` | All elements with the class "intro" or "demo" |
| `element`       | `$("p")`            | All `<p>` elements                            |
| `element.class` | `p.intro`           | Selects all      elements with class="intro"  |

![jquery selector](https://camo.githubusercontent.com/0a2bd064ccf393fe5a4d05330d162e1f983fd627b290c85392688cc96a6cc718/68747470733a2f2f63646e2e6564756362612e636f6d2f61636164656d792f77702d636f6e74656e742f75706c6f6164732f323031392f31312f6a71756572792d71756572792d73656c6563746f722e706e67)

## JQuery selector

### Single Element

`$('ul')`

### Multiple Element

`$('li')`

### Getting information

`var content = $('li').html();`

### Setting information

`$('li').html('Updatd');`

![jquery looping](https://camo.githubusercontent.com/8bf959dcc749f643d57028197f0923ec104e00908df5c92e3beecdb339ed5210/68747470733a2f2f7777772e706f736974726f6e782e696f2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f706f736974726f6e782d6a71756572792d3030312e6a7067)

### jQuery Looping

![looping](https://camo.githubusercontent.com/bad42c27878318fee721bdc6e1c18fcad01f484209ba7ed4679e2202e365d3d3/68747470733a2f2f7777772e706f736974726f6e782e696f2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f706f736974726f6e782d6a71756572792d3030322e6a7067)

### Checking a page is ready to work with

jQuery `.ready()` method checks that the page is ready to your code to work with

```javascript
$(document).ready(function() {
  // Your script goes here
});
```

### Getting element content

1. `html()`
2. `text()`

`.html()` used to read the html content from page

The jQuery `text()` method is used to set or return the text content of the selected elements.

### Updating element

1. `html()`
2. `text()`
3. `replaceWith()`
4. `remove()`

### Changing CSS rules

The `css()` method sets or returns one or more style properties for the selected elements.

```javascript
$("p").css({"background-color": "yellow", "font-size": "200%"});
```

### Delegating event

Event delegation allows us to attach a single event listener, to a parent element, that will fire for all descendants matching a selector, whether those descendants exist now or are added in the future.

```html
<html>
<body>
<div id="container">
    <ul id="list">
        <li><a href="http://domain1.com">Item #1</a></li>
        <li><a href="/local/path/1">Item #2</a></li>
        <li><a href="/local/path/2">Item #3</a></li>
        <li><a href="http://domain4.com">Item #4</a></li>
    </ul>
</div>
</body>
</html>
```

When an anchor in our `#list` group is clicked, we want to log its text to the console. Normally we could directly bind to the click event of each anchor using the `.on()` method:

```javascript
$( "#list a" ).on( "click", function( event ) {
    event.preventDefault();
    console.log( $( this ).text() );
});
```

**Other methods**:

1. `.show()`
2. `.hide()`
3. `.slideUp()`
4. `.slideDown()`
5. `.fadeOut()`
6. `.fadeIn()`
7. `.toggle()`
8. `.slideToggle()`
9. `.fadeToggle()`
10. `.addClass()`

```javascript
// Instantaneously hide all paragraphs
$( "p" ).hide();
 
// Instantaneously show all divs that have the hidden style class
$( "div.hidden" ).show();

// Slowly hide all paragraphs
$( "p" ).hide( "slow" );
 
// Quickly show all divs that have the hidden style class
$( "div.hidden" ).show( "fast" );

// Hide all paragraphs over half a second
$( "p" ).hide( 500 );
 
// Show all divs that have the hidden style class over 1.25 seconds
$( "div.hidden" ).show( 1250 );

// Hide all paragraphs using a slide up animation over 0.8 seconds
$( "p" ).slideUp( 800 );
 
// Show all hidden divs using a slide down animation over 0.6 seconds
$( "div.hidden" ).slideDown( 600 );

// Hide all paragraphs using a fade out animation over 1.5 seconds
$( "p" ).fadeOut( 1500 );
 
// Show all hidden divs using a fade in animation over 0.75 seconds
$( "div.hidden" ).fadeIn( 750 );

// Instantaneously toggle the display of all paragraphs
$( "p" ).toggle();
 
// Slowly toggle the display of all images
$( "img" ).toggle( "slow" );
 
// Toggle the display of all divs over 1.8 seconds
$( "div" ).toggle( 1800 );

// Toggle the display of all ordered lists over 1 second using slide up/down animations
$( "ol" ).slideToggle( 1000 );
 
// Toggle the display of all blockquotes over 0.4 seconds using fade in/out animations
$( "blockquote" ).fadeToggle( 400 );

// Fade in all hidden paragraphs; then add a style class to them (not quite right)
$( "p.hidden" ).fadeIn( 750 ).addClass( "lookAtMe" );

// Fade in all hidden paragraphs; then add a style class to them (correct with animation callback)
$( "p.hidden" ).fadeIn( 750, function() {
    // this = DOM element which has just finished being animated
    $( this ).addClass( "lookAtMe" );
});
```

![jquery methods and events](https://camo.githubusercontent.com/90ba0d5cb34edbe13b07accf386de70fe4b3cdaae8bf6fa0d03ca9454db9f45f/68747470733a2f2f69322e77702e636f6d2f636f64656d7975692e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031362f30382f6275696c642d696e2d6c6f6164696e672d7375626d69742d627574746f6e2e6769663f6669743d3838302532433434302673736c3d31)

### Animting CSS

The jQuery `animate()` method is used to create custom animations.

The following example demonstrates a simple use of the `animate()` method; it moves a `<div>` element to the right, until it has reached a left property of 250px:

```javascript
$("button").click(function(){
  $("div").animate({left: '250px'});
}); 
```

### jQuery animate() - Manipulate Multiple Properties

```javascript
$("button").click(function(){
  $("div").animate({
    left: '250px',
    opacity: '0.5',
    height: '150px',
    width: '150px'
  });
}); 
```

### jQuery animate() - Using Pre-defined Values You can even specify a property's animation value as "show", "hide", or "toggle"

```javascript
$("button").click(function(){
  $("div").animate({
    height: 'toggle'
  });
}); 
```
