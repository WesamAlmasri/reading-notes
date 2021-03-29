# MUSTACHE and FLEXBOX

## Templating with Mustache

![JavaScript Mustach image](https://image.slidesharecdn.com/mustachefronteers11-111006032603-phpapp01/95/templating-with-your-mustachejs-1-728.jpg?cb=1318327508)

Mustache can be used for HTML, config files, source code - anything. It works by expanding tags in a template using values provided in a hash or object.

We call it "`logic-less`" because there are no if statements, else clauses, or for loops.

### TAG TYPES

Tags are indicated by the double mustaches. `{{person}}` is a tag, as is `{{#person}}`. In both examples, we'd refer to person as the key or tag key. Let's talk about the different types of tags.

### Variables

The most basic tag type is the variable. A `{{name}}` tag in a basic template will try to find the name key in the current context. If there is no name key, the parent contexts will be checked recursively. If the top context is reached and the name key is still not found, nothing will be rendered.

All variables are HTML escaped by default. If you want to return unescaped HTML, use the triple mustache: `{{{name}}}`.

Template:

```html
* {{name}}
* {{age}}
* {{company}}
* {{{company}}}
```

Hash:

```javascript
{
  "name": "Chris",
  "company": "<b>GitHub</b>"
}
```

Output:

```renderdhtml
* Chris
*
* &lt;b&gt;GitHub&lt;/b&gt;
* <b>GitHub</b>
```

### Install Mustache

**Mustache-Express**: If you intend you use mustache with Node and Express, you can use *mustache-express*. Mustache Express lets you use Mustache and Express together easily. To install:

`$ npm install mustache --save`

Configure `mustache-express` in your server.js/app.js/index.js file:

![mustache-express Configure](https://camo.githubusercontent.com/4f8b43498b9cfd5c2df163c33b6a7da76d28a21976133e0b1a273ae09a171136/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313430302f312a455331306c7872377464524656454b635241674c45772e706e67)

Create a views folder and add some html view templates (e.g. hello.html):

![steps](https://camo.githubusercontent.com/89ce12d49cc509840c6a22dda77c9fc22982030cacfb8cf05f7f24528f429548/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3938382f312a7a775945386135727641565a63426c3976316f7166412e706e67)

To use variable passed to HTML like the image bellow

![use variable](https://camo.githubusercontent.com/ee8e3d419fc478f4bec82dc54adca426ad0809a02eb49b34d0c21a2dc1f7bfa0/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313430302f312a4652634c394e5148493743766932454c4c6d7a4a47512e706e67)

Then in the router configuration, use `res.render(TEMPLATE_NAME, JSON_DATA)`. Example:

`res.render('hello', {"name": "Sherlynn"})`

**Output**:

![output image](https://camo.githubusercontent.com/7cc2d997433c32444b165c5abf587f0ef579f3682eecd66c2b80f5fe9af93d08/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313430302f312a59614a317674737577524d686669387061726c484f412e706e67)

## CSS Flexbox

![css flexbox image](https://oracle-patches.com/images/2019/11/09/flexbox-css_large.jpg)

The Flexible Box Layout Module, makes it easier to design flexible responsive layout structure without using float or positioning.

### Parent Element (Container)

The flex container becomes flexible by setting the display property to flex:

```css
.flex-container {
  display: flex;
}
```

The flex container properties are:

1. flex-direction
2. flex-wrap
3. flex-flow
4. justify-content
5. align-items
6. align-content

### The flex-direction Property

![The flex direction](https://camo.githubusercontent.com/9ece155a18899ad915ccef5da80f618006b82c49277beea200e22c1f70d966da/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f666c65782d646972656374696f6e2e737667)

The `flex-direction` property defines in which direction the container wants to stack the flex items.

```css
.flex-container {
  display: flex;
  flex-direction: column;
}
```

The `column-reverse` value stacks the flex items vertically (but from bottom to top):

```css
.flex-container {
  display: flex;
  flex-direction: column-reverse;
}
```

The `row` value stacks the flex items horizontally (from left to right):

```css
.flex-container {
  display: flex;
  flex-direction: row;
}
```

The `row-reverse` value stacks the flex items horizontally (but from right to left):

```css
.flex-container {
  display: flex;
  flex-direction: row-reverse;
}
```

### The flex-wrap Property

![flex wrap image](https://camo.githubusercontent.com/fd3727f675a455a68ce92ed75cf57ff202447fd18f730f7978b80a3bb0e79638/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f666c65782d777261702e737667)

The `flex-wrap` property specifies whether the flex items should wrap or not.

The wrap value specifies that the flex items will wrap if necessary:

```css
.flex-container {
  display: flex;
  flex-wrap: wrap;
}
```

The `nowrap` value specifies that the flex items will not wrap (this is default):

```css
.flex-container {
  display: flex;
  flex-wrap: nowrap;
}
```

The `wrap-reverse` value specifies that the flexible items will wrap if necessary, in reverse order:

```css
.flex-container {
  display: flex;
  flex-wrap: wrap-reverse;
}
```

### The flex-flow Property

![flex flow image](https://camo.githubusercontent.com/cc5ffa61af4df1ed084ac9cc7339792a821d17b7618c4d44b52033202248227d/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313638382f312a31786e7a5976545072304c542d54514d6950733741512e706e67)

In the following example we will solve a very common style problem: **perfect centering**.

**SOLUTION**: Set both the justify-content and align-items properties to center, and the flex item will be perfectly centered:

```css
.flex-container {
  display: flex;
  height: 300px;
  justify-content: center;
  align-items: center;
}
```

### Other values of justifiy-content

![centering with flexbox](https://camo.githubusercontent.com/43424f1be2ae6a7a38c7a39dd9aa0f702a0a9cb1e913a9d13f8997a6256c3cd3/68747470733a2f2f692e70696e696d672e636f6d2f6f726967696e616c732f61622f64332f65652f61626433656533326365333338616438663336326336613666643839336638372e706e67)
