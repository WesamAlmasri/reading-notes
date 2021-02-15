# HTML Lists, CSS Boxes, JS Control Flow

![html css js image](https://d2h0cx97tjks2p.cloudfront.net/blogs/wp-content/uploads/sites/2/2020/07/html-lists-df.jpg)

## Lists

HTML provides us with three different types:

1. Ordered lists
2. Unordered lists
3. Definition lists

### Ordered Lists

Lists where each item in the list is numbered.

- `<ol>` The ordered list is created with the `<ol>` element.
- `<li>` Each item in the list is placed between an opening `<li>` tag and a closing `</li>` tag. (The `li`stands for list item.)

```html
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>  
```

1. Coffee
2. Tea
3. Milk

### Unordered Lists

Lists that begin with a bullet point.

- `<ul>` The unordered list is created with the `<ul>` element.
- `<li>` Each item in the list is placed between an opening `<li>` tag and a closing `</li>` tag. (The `li` stands for list item.)

```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

- Coffee
- Tea
- Milk

### Definition Lists

Made up of a set of terms along with the definitions for each of those terms.

The `<dl>` tag defines the description list, the `<dt>` tag defines the term (name), and the `<dd>` tag describes each term:

```html
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>
```

![definition list](https://camo.githubusercontent.com/8e5f686fa1d8e143bd842d2e70d305d85454ae378934f78defbe878d42ff0933/68747470733a2f2f7777772e64756d6d6965732e636f6d2f77702d636f6e74656e742f75706c6f6164732f3339383536392e696d616765302e6a7067)

### Nested Lists

You can put a second list inside an `<li>` element to create a sub-list or nested list.

```html
<ul>
    <li>Mousses</li>
    <li>Pastries
        <ul>
            <li>Croissant</li>
            <li>Mille-feuille</li>
            <li>Palmier</li>
            <li>Profiterole</li>
        </ul>
    </li>
    <li>Tarts</li>
</ul>
```

- Mousses
- Pastries
  - Croissant
  - Mille-feuille
  - Palmier
  - Profiterole
- Tarts

## Boxes

![css boxes image](https://disenowebakus.net/en/images/articles/learn-css.jpg)

CSS treats each HTML element as if it lives in its own box.

### Box Dimensions

**width, height**:

By default a box is sized just big enough to hold its contents. To set your own dimensions for a box you can use the height and width properties. The most popular ways to specify the size of a box are to use pixels, percentages, or ems. Traditionally, pixels have been the most popular method because they allow designers to accurately control their size.

```html
<!-- HTML -->
<div>
    <p>
        The Moog company pioneered the commercial manufacture of modular voltage-controlled analog synthesizer systems in the early 1950s.
    </p>
</div>
```

```css
// CSS
div.box {
    height: 300px;
    width: 300px; 
    background-color: #bbbbaa;
}
p {
    height: 75%;
    width: 75%; 
    background-color: #0088dd;
}

```

### Limiting Width

**min-width, max-width**:

Some page designs expand and shrink to fit the size of the user's screen. In such designs, the min-width property specifies the smallest size a box can be displayed at when the browser window is narrow, and the max-width property indicates the maximum width a box can stretch to when the browser window is wide.

```html
<!-- HTML -->
<tr>
    <td>
        <img src="images/rhodes.jpg" width="200" height="100" alt="Fender Rhodes" />
    </td>
    <td class="description">
        The Rhodes piano is an electro-mechanical piano, invented by Harold Rhodes during the fifties and later manufactured in a number of models ...
    </td>
    <td>
        $1400
    </td>
</tr>
```

```css
// CSS
td.description { 
    min-width: 450px; 
    max-width: 650px; 
    text-align: left; 
    padding: 5px; 
    margin: 0px;
}
```

And there are also Limited Height (**min-height, max-height**).

### Overflowing Content

**overflow**:
The overflow property tells the browser what to do if the content contained within a box is larger than the box itself. It can have one of two values:

- **hidden**: This property simply hides any extra content that does not fit in the box
- **scroll**: This property adds a scrollbar to the box so that users can scroll to see the missing conten


### Border and Margin and Padding

**Border**:

Every box has a border (even if it is not visible or is specified to be 0 pixels wide). The border separates the edge of one box from another.

**Margin**:

Margins sit outside the edge of the border. You can set the width of a margin to create a gap between the borders of two adjacent boxes.

**Padding**:

Padding is the space between the border of a box and any content contained within it. Adding padding can increase the readability of its contents.

![border margin and paddign image](https://i.pinimg.com/originals/f6/f6/c9/f6f6c946356774ddb886956cd94df4c9.png)

### White space & Vertical Margin

The padding and margin properties are very helpful in adding space between various items on the page.

![margine and padding image](https://camo.githubusercontent.com/24b49da33379b1fc096a77ffad267da33d614d048baa7a126957b73cd4ada9f8/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f2d32634b724134495a4e587a43593742413270714a4e78367352306e426b6a7565575568617a6d4c4f734b2d544c51483369356e5a754b524972476c3552744f5f426a6775686a5936314b415265515159766f63357a6f66373164446c557a533653744633396f57474e757543506478695a6b4c484e5179422d5075464252756435565678715747)

### Border Width

**border-width**:

The border-width property is used to control the width of a border. The value of this property can either be given in pixels or using one of the following values:

- thin
- medium
- thick

You can control the individual size of borders using four separate properties:

```css
border-top-width
border-right-width 
border-bottom-width 
border-left-width
```

```html
<!-- HTML -->
<p class="one">Hohner's "Clavinet" is essentially an electric clavichord.</p>
<p class="two">Hohner's "Clavinet" is essentially an electric clavichord.</p>
<p class="three">Hohner's "Clavinet" is essentially an electric clavichord.</p>
```

```css
// CSS
p.one { 
    border-width: 2px;
}
p.two {
    border-width: thick;
}
p.three {
    border-width: 1px 4px 12px 4px;
}
```

### Border Style

**border-style**:

```html
<p class="one">Wurlitzer Electric Piano</p>
<p class="two">Wurlitzer Electric Piano</p>
<p class="three">Wurlitzer Electric Piano</p>
<p class="four">Wurlitzer Electric Piano</p>
<p class="five">Wurlitzer Electric Piano</p>
<p class="six">Wurlitzer Electric Piano</p>
<p class="seven">Wurlitzer Electric Piano</p>
<p class="eight">Wurlitzer Electric Piano</p>
```

```css
p.one {border-style: solid;} 
p.two {border-style: dotted;} 
p.three {border-style: dashed;} 
p.four {border-style: double;} 
p.five {border-style: groove;} 
p.six {border-style: ridge;} 
p.seven {border-style: inset;} 
p.eight {border-style: outset;}
```

![border styles image](https://camo.githubusercontent.com/3a1f9a61e5fce469372efbfa5be19b8ff8bc0c16b85bbc0452e3065f636b07d4/68747470733a2f2f646f63732e6d6963726f736f66742e636f6d2f656e2d75732f70726576696f75732d76657273696f6e732f77696e646f77732f696e7465726e65742d6578706c6f7265722f69652d646576656c6f7065722f706c6174666f726d2d617069732f696d616765732f66663937353631362e626f726465722d7374796c65253238656e2d757325324376732e38352532392e706e67)

### Border 

**border-color**:

You can specify the color of a border using either RGB values, hex codes or CSS color names It is possible to individually control the colors of the borders on different sides of a box using:

```css
border-top-color
border-right-color 
border-bottom-color 
border-left-color
```

**border-width**:

The border-width property is used to control the width of a border. The value of this  property can either be given in pixels or using one of the following values:

- thin
- medium
- thick

You can control the individual size of borders using four separate properties:

```css
border-top-width
border-right-width
border-bottom-width
border-left-width
```

**border-style**:

You can control the style of a border using the border-style property. This property can take the following values:

- **solid** a single solid line
- **dotted** a series of square dots (if your border is 2px wide, then the dots are 2px squared with a 2px gap between each dot)
- **dashed** a series of short lines
- **double** two solid lines (the
value of the border-width property creates the sum of the two lines) 
- **groove** appears to be carved into the page
- **ridge** appears to stick out from the page
- **inset** appears embedded into the page
- **outset** looks like it is coming out of the screen
- **hidden / none** no border is shown

You can individually change the styles of different borders using:

```css
border-top-style
border-left-style
border-right-style
border-bottom-style
```

Or you can use a shorthand (where the values are in clockwise order: top, right, bottom, left):

`border: size style color;`
`order: 3px dotted #0088dd;`

### Padding

**padding**:

The padding property allows you to specify how much space should appear between the content of an element and its border. You can specify different values for each side of a box using:

```css
padding-top 
padding-right 
padding-bottom 
padding-left
```

Or you can use a shorthand (where the values are in clockwise order: top, right, bottom, left):

`padding: 10px 5px 3px 1px;`

### Margin

**margin**:
 The margin property controls the gap between boxes. Its value is commonly given in pixels, although you may also use percentages or ems. You can specify values for each side of a box using:

 ```css
 margin-top 
margin-right 
margin-bottom 
margin-left
```

You can also use the shorthand (where the values are in clockwise order: top, right, bottom, left):

` margin: 1px 2px 3px 4px;`

Sometimes you might see the following, which means that the left and right margins should be 10 pixels and the top and bottom margins should be 20 pixels:

`margin: 10px 20px;`

### Changing Inline/Block

**display**:

The display property allows you to turn an inline element into a block-level element or vice versa, and can also be used to hide an element from the page.

The values this property can take are:

**inline**: This causes a block-level element to act like an inline element.

**block**: This causes an inline element to act like a block-level element.

**inline-block**: This causes a block-level element to flow like an inline element, while retaining other features of a block-level element.

**none**: This hides an element from the page. In this case, the element acts as though it is not on the page at all (although a user could still see the content of the box if they used the view source option in their browser).

### Hidding Box

**visability**:

The visibility property allows you to hide boxes from users but It leaves a space where the element would have been.

This property can take two values:

**hidden**: This hides the element.

**visible**: This shows the element.

## Decisions and Loops (JavaScript)

![javascript image](https://cdn.searchenginejournal.com/wp-content/uploads/2020/02/seo-javascript-the-good-the-bad-the-uncertainty-5e4a09b3cd5db-760x400.webp)


### Switch statements

A **switch** statement starts with a variable called the *switch value*. Each case indicate a possible value for this variable and the code that should run if the variable matches that value.

```javascript
switch(level){
    case 'One':
        title = 'Level 1';
        break;
    case 'Two':
        title = 'Level 2';
        break;
    case 'Three':
        title = 'Level 3';
        break;
    default:
        title = 'Test';
        break;
}
```

A `switch` statement first evaluates its expression. It then looks for the first `case` clause whose expression evaluates to the same value as the result of the input expression (using the strict comparison, `===`) and transfers control to that clause, executing the associated statements. (If multiple `case`s match the provided value, the first `case` that matches is selected, even if the `case`s are not equal to each other.)

If no matching `case` clause is found, the program looks for the optional `default` clause, and if found, transfers control to that clause, executing the associated statements. If no `default` clause is found, the program continues execution at the statement following the end of `switch`. By convention, the `default` clause is the last clause, but it does not need to be so.

The optional `break` statement associated with each `case` label ensures that the program breaks out of `switch` once the matched statement is executed and continues execution at the statement following `switch`. If `break` is omitted, the program continues execution at the next statement in the `switch` statement. The `break` statement is not required if a `return` statement precedes it.

### TYPE COERCION & WEAK TYPING

If you use a data type JavaScript did not expect, it tries to make sense of the operation rather than report an error.

JavaScript can convert data types behind the scenes to complete an operation. This is known as **type coercion**. For example, a string '1' could be converted to a number 1 in the following expression:('1' > 0). As a result, the above expression would evaluate to true.

JavaScript is said to use **weak typing** because the data type for a value can change. Some other languages require that you specify what data type each variable will be. They are said to use **strong typing**.

| Data type | purpose                                                 |
| --------- | ------------------------------------------------------- |
| string    | Text                                                    |
| number    | Number                                                  |
| Boolean   | true or false                                           |
| null      | Empty value                                             |
| undefined | Variable has been declared but not yet assigned a value |

`NaN` is a value that is counted as a number. You may see it when a number is expected, but is not returned, e.g .. ('ten' /2) results in NaN.

### TRUTHY & FALSY VALUES

Due to type coercion, every value in JavaScript can be treated as if it were true or false; and this has some interesting side effects.

**Falsy** values are treated as if they are fa1se.Falsy values can also be treated as the number 0.

**Truthy** values are treated as if they are true. Truthy values can also be treated as the number 1.

![truthy and falsy values image](https://miro.medium.com/max/1600/1*s-FasudN5aSYnX2rDz75AA.jpeg)

### CHECKING EQUALITY & EXISTENCE

Because the presence of an object or array can be considered truthy, it is often used to check for the existence of an element within a page.

```javascript
if (document.getElementByid('header'))
// Found: do something
else {
// Not found: do somethi ng else
```

Those new to JavaScript often think the fol lowing would do the same: `if (document . getElementByld('header') == true)` but `document.getElementByld ('header ')` would return an object which is a truthy value but it is not equal to a Boolean value of true.

### SHORT CIRCUIT VALUES

Logical operators are processed left to right. They short-circuit (stop) as soon as they have a result - but they return the value that stopped the processing (not necessarily `true` or `false`).

Logical operators will not always return true or false, because:

- They return the value that stopped processing.
- That value might have been treated as truthy or falsy although it was not a Boolean.

### Loops

Loops check a condition. If it returns `true`, a code block will run. Then the condition will be checked again and if it still returns `true`, the code will run again. It repeats untill the condition returns `false`.

There are three common types of loops.

**For**:

```javascript
    for(var i = 0; i < 10; i++){
        document,write(i);
    }
```

`var i = 0;` Initialization which creates a variable and set it to zero and it acts as the counter. The variable is only created the first time the loop is run.

`i < 10` The condition that will be checked in every cycle.

`i++` The Update to the variable. It will bw run in every cycle after runing the body of the for statement.

**While**:

```javascript
initVariable;
while(condition){
    statements;
    updatingTheVariable;
}
```

In while loop you have to initialize the variable before the while statement and we have to update the variable at the end of while body.
