# HTML Text, CSS Introduction, and Basic JavaScript Instructions

## Text

When creating a web page, you add tags (known as markup) to the contents of the page. These tags provide extra meaning and allow browsers to show users the appropriate structure for the page

There are two types of markups:

- **Structural markup**: the elements that you can use to describe both headings and paragraphs
- **Semantic markup**: which provides extra information; such as where emphasis is placed in a sentence, that something you have written is a quotation (and who said it), the meaning of acronyms, and so on

### Heading

HTML has six "levels" of headings:

```html
<h1>This is a Main Heading</h1>
<h2>This is a Level 2 Heading</h2>
<h3>This is a Level 3 Heading</h3>
<h4>This is a Level 4 Heading</h4>
<h5>This is a Level 5 Heading</h5>
<h6>This is a Level 6 Heading</h6>
```

![html heading image](https://www.freetutorialsplus.com/html-tutorial/images/html-headings.png)

### Paragraphs

To create a paragraph, surround the words that make up the paragraph with an opening `<p>` tag and closing `</p>` tag.

```html
<p>This is a paragraph.</p>
<p>This is a paragraph.</p>
<p>This is a paragraph.</p>
```

### Bold & Italic

By enclosing words in the tags `<b>` and `</b>` we can make characters appear bold.

By enclosing words in the tags `<i>` and `</i>` we can make characters appear italic.

```html
<p>This is how we make a word appear <b>bold.</b></p>
<p>Captain Cook sailed to Australia on the <i>Endeavour</i>.</p>
```

### Superscript & Subscript

`<sup>` element is used to contain characters that should be superscript such as the suffixes of dates or mathematical concepts like raising a number to a power such as 2^5.

`<sub>` element is used to contain characters that should be subscript. It is commonly used with foot notes or chemical formulas such as H20.

```html
<p>On the 4<sup>th</sup> of September you will learn
about E=MC<sup>2</sup>.</p>
<p>The amount of CO<sub>2</sub> in the atmosphere
grew by 2ppm in 2009<sub>1</sub>.</p>
```

### White Space

In order to make code easier to read, web page authors often add extra spaces or start some elements on new lines.

When the browser comes across two or more spaces next to each other, it only displays one space. Similarly if it comes across a line break, it treats that as a single space too. This is known as **white space collapsing**.

### Linebreak & Horizintal rule

`<br />` As you have already seen, the browser will automatically show each new paragraph or heading on a new line. But if you wanted to add a line break inside the middle of a paragraph you can use the line break tag `<br />`.

`<hr />` To create a break between themes — such as a change of topic in a book or a new scene in a play — you can add a horizontal rule between sections using the `<hr />` tag.

```html
<p>The Earth<br />gets one hundred tons heavier
every day<br />due to falling space dust.</p>
<p>Venus is the only planet that rotates
clockwise.</p>
<hr />
<p>Jupiter is bigger than all the other planets
combined.</p>
```

### Semantic Markup

There are some text elements that are not intended to affect the structure of your web pages, but they do add extra information to the pages — they are known as semantic markup.

**`<strong>`**: Indicates that its content has strong importance.

**`<em>`**: Indicates emphasis that subtly changes the meaning of a sentence.

**`<blockquote>`**: Used for longer quotes that take up an entire paragraph.

**`<q>`**: Used for shorter quotes that sit within a paragraph.

**`<abbr>`**: If you use an abbreviation or an acronym, then the `<abbr>` element can be used. A title attribute on the opening tag is used to specify the full term.

**`<cite>`**: Used to reference a piece of work such as a book,
film or research paper, the `<cite>` element can be used to indicate where the citation is from.

**`<dfn>`**: Used to explain some new terminology

**`<address>`**: Used to contain contact details for the author of the page.

**`<ins>`, `<del>`**: The `<ins>` element can be used to show content that has been inserted into a document, while the `<del>` element can show text that has been deleted from it.

**`<s>`**: The `<s>` element indicates something that is no longer accurate or relevant (but that should not be deleted).

![css image](https://cdn.mos.cms.futurecdn.net/Vp9WvV7YKdH4k8sKRePcE8-970-80.jpg.webp)

## CSS

**What is CSS**:

**CSS** allows you to create rules that specify how the content of an element should appear. For example, you can specify that the background of the page is cream, all paragraphs should appear in gray using the Arial typeface, or that all level one headings should be in a blue, italic, Times typeface.

CSS works by associating rules with HTML elements. These rules govern how the content of specified elements should be displayed. A CSS rule contains two parts: a selector and a declaration.

```css
p {
    font-family: Arial;
}
```

![css rule image](https://camo.githubusercontent.com/3a5945f4634cc8c20483ff691fdf68831bb16b36edd94c973bba1df27acd810e/68747470733a2f2f6d646e2e6d6f7a696c6c6164656d6f732e6f72672f66696c65732f393436312f6373732d6465636c61726174696f6e2d736d616c6c2e706e67)

This rule indicates that all "p" elements should be shown in the Arial typeface.

Selectors indicate which element the rule applies to. The same rule can apply to more than one element if you separate the element names with commas.

Declarations indicate how the elements referred to in the selector should be styled. Declarations are split into two parts (a property and a value), and are separated by a colon.

### Applying css to your page

There are three way to implement your CSS with

1. Inline CSS
2. Add style tag into head and put your css on it (internal CSS)
3. External CSS file the link it to you page

#### External CSS

**`<link>`**:

The `<link>` element can be used in an HTML document to tell the browser where to find the CSS file used to style the page. It is an empty element (meaning it does not need a closing tag), and it lives inside the `<head>` element. It should use three attributes:

- *href*: This specifies the path to the CSS file (which is often placed in a folder called css or styles)
- *type*: This attribute specifies the type of document being linked to. The value should be text/css
- *rel*: This specifies the relationship between the HTML page and the file it is linked to. The value should be stylesheet when linking to a CSS file

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Using External CSS</title>
        <link href="css/styles.css" type="text/css" rel="stylesheet" />
    </head>
    <body>
        <h1>Potatoes</h1>
        <p>There are dozens of different potato
            varieties. They are usually described as
            early, second early and maincrop.</p>
    </body>
</html>
```

#### Internal CSS

**`<style>`**:

You can also include CSS rules within an HTML page by placing them inside a `<style>` element, which usually sits inside the `<head>` element of the page.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Using Internal CSS</title>
        <style type="text/css">
            body {
                    font-family: arial;
                    background-color: rgb(185,179,175);}
            h1 {
                    color: rgb(255,255,255);}
        </style>
    </head>
    <body>
        <h1>Potatoes</h1>
        <p>There are dozens of different potato
            varieties. They are usually described as
            early, second early and maincrop.</p>
    </body>
</html>
```

#### Inline CSS

You can also include CSS rules within HTML tag inside *style* attribute.

```html
<p style="color: blue;">This is a paragraph</p>
```

![javascript image](https://res.cloudinary.com/practicaldev/image/fetch/s--ohpJlve1--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://res.cloudinary.com/drquzbncy/image/upload/v1586605549/javascript_banner_sxve2l.jpg)

## JavaScript

### Statements

A **script** is a series of instructions that a computer can follow one-by-one. Each individual instruction or step is known as a statement, Statements should end with a semicolon.

```javascript
var today= new Date();
var hourNow = today.getHours() ;
var greeting;
if (hourNow > 18) {
greeting= 'Good evening';
else if (hourNow > 12) {
greeting= 'Good afternoon';
else if (hourNow > O) {
greeting 'Good morning';
else {
greeting 'Welcome';
}
document.write(greeting) ;
```

### comments

You should write comments to explain what your code does. They help make your code easier to read and understand. This can help you and others who read your code.

```javascript
/*
This script displays a greeting to the user based upon the current time.
It is an example from JavaScript & jQuer y book */

var today= new Date();
var hourNow = today.getHours();    // Create a ne1~ dat e object
var greeting;                      // Find the current hour
// Display the appropriate greeting based on the current time

if (hourNow > 18) {
greeting = 'Good evening ' ;
else i f (hourNow > 12) {
greeting = 'Good afternoon';
else if (hourNow > 0) {
greeting= ' Good morning';
else {
greeting = 'Welcome';
}
document.write(greeting) ;
```

To write a comment that stretches over more than one line, you use a multi-line comment, starting with the /\* characters and ending with the \*/ characters.

In a single-line comment, anything that follows the two forward slash characters on that line will not be processed by the JavaScript interpreter.

### Variable

A script will have to temporarily store the bits of information it needs to do its job. It can store this data in variables.

![define variable image](https://camo.githubusercontent.com/ef0c9428bb00617c0cf8b6bebba1573669e13e8b1a7bf6913a6e9350f58015c2/68747470733a2f2f312e62702e626c6f6773706f742e636f6d2f2d38556d5746546e676677592f586b5652756f5046666b492f4141414141414141436d492f39336a2d464d6b41394559796f52495431716c4a32734d55626f626e5754315567434c63424741735948512f77313230302d683633302d702d6b2d6e6f2d6e752f6a6176617363726970745f7661722e706e67)

Think about calculating the area of a wall; in math the area of a rectangle is obtained by multiplying two numbers: width x height = area

You may be able to do calculations like this in your head, but when writing a script to do this calculation, you need to give the computer very detailed instructions. You might tell it to perform the following four steps in order:

- Remember the value for width
- Remember the value for height
- Multiply width by height to get the area
- Return the result to the user

```html
<script>
    var x = 5;
    var y = 6;
    var z = x + y;
    document.getElementById("demo").innerHTML = "The value of z is: " + z;
</script>
```

### DATA TYPES

JavaScript distinguishes between numbers, strings, and true or false values known as Boolean.

**Numeric data type**: The numeric data type handles numbers `0.75`.

**String data type**: The strings data t ype consists of letters and other characters `H. 1 ' Ivy!`.

**Boolean data type**: Boolean data types can have one of two values: `true` or `false`.

### Rules for naming variables

![rulse for naming variable image](https://images.slideplayer.com/33/10138821/slides/slide_6.jpg)

### ARRAYS

An array is a special type of variable. It doesn't just store one value; it stores a list of values.

You should consider using an array whenever you are working with a list or a set of values that are related to each other.

You create an array and give it a name just like you would any other variable (using the var keyword followed by the name of the array).

The values are assigned to the array inside a pair of square brackets, and each value is separated by a comma. The values in the array do not need to be the same data type, so you can store a string, a number and a Boolean all in the same array.

```javascript
var colors;
colors ['white', 'black', ' custom ' ];
var el = document.getElementByld('colors');
el.textContent = col ors[O];
```

Values in an array are accessed as if they are in a numbered list. It is important to know that the numbering of this list starts at zero (not one).

Each item in an array is automatically given a number called an **index**. This can be used to access specific items in the array.

```javascript
var colors ;
colors= [' white ' ,
'black ' ,
' custom '];
```

To retrieve the third item on the list, the array name is specified along with the index number in square brackets.

```javascript
var itemThree;
itemThree = colors[2] ;
```

Each array has a property called **length**, which holds the number of items in the array.

```javascript
var numColors ;
numColors =colors.length ;
```

To access a valu e from an array, after the array name you specify the index number for that value inside square brackets.

You can change the value of an item an array by selecting it and assigning it a new value just as you would any other variable (using the equals sign and the new value for that item).

```javascript
// Create the array
var colors = ['white',
'black' ,
'custom'];
// Update the third item in the array
colors[2] = 'beige ';

// Get the element with an id of colors
var el = document .getElementByid(' colors');

// Replace with third item from the array
el .textContent = colors[2];
```

### EXPRESSIONS

An **expression** evaluates into (results in) a single value. Broadly speaking there are two types of expressions.

- Expressions that just assign a value to a variable. such as `var color = 'beige';`.  
- Expressions that use two or more values to return a single value such as `var area = 3 * 2;`.

### OPERATORS

Expressions rely on things called operators; they allow programmers to create a single value from one or more values.

- ASSIGNMENT OPERATORS: Assign a value to a variable `color = 'beige';`
- ARITHMETIC OPERATORS: Perform basic math `area = 3 * 2;`
- STRING OPERATORS: Combine two strings `greeting= 'Hi ' + 'Mol ly';`
- COMPARISON OPERATORS: Compare two values and return true or fa1se `buy = 3 > 5`
- LOGICAL OPERATORS: Combine expressions and return true or fa1se `buy = (3 > 5) && (8 <1 0)`

## Decisions and Loops

Scripts often need to behave differently depending upon how the user interacts with the web page and/or the browser window itself. To determine which path to take, programmers often rely upon the following three concepts:

- EVALUATIONS: You can analyze values in your scripts to determine whether or note they match expected results.
- DECISIONS: Using the results of evaluations, you can decide which path your script should go down.
- LOOPS: There are also many occasions where you will want to perform the same set of steps repeatedly.

There are often several places in a script where decisions are made that determine which lines of code should be run next. Flowcharts can help you plan for these occasions.

![flow chart image](https://miro.medium.com/max/432/1*0mFwslUH5H_X3HyfRia20Q.png)

### Arithmetic Operators

| Operator | Description                                          |
| -------- | ---------------------------------------------------- |
| +        | Adds two numeric operands.                           |
| ---      | Subtract right operand from left operand             |
| *        | Multiply two numeric operands.                       |
| /        | Divide left operand by right operand.                |
| %        | Modulus operator. Returns remainder of two operands. |
| ++       | Increment operator. Increase operand value by one.   |
| '--'     | Decrement operator. Decrease value by one.           |

**Example**:

```javascript
var x = 5, y = 10, z = 15;

x + y; //returns 15

y - x; //returns 5

x * y; //returns 50

y / x; //returns 2

x % 2; //returns 1

x++; //returns 6

x--; //returns 4

var a = 5, b = "Hello ", c = "World!", d = 10;

a + b; // "5Hello "

b + c; // "Hello World!"

a + d; // 15
```

### Comparison Operators

JavaScript language includes operators that compare two operands and return Boolean value true or false.

| Operator | Description                                                                                                      |
| -------- | ---------------------------------------------------------------------------------------------------------------- |
| ==       | Compares the equality of two operands without considering type.                                                  |
| ===      | Compares equality of two operands with type.                                                                     |
| !=       | Compares inequality of two operands.                                                                             |
| >        | Checks whether left side value is greater than right side value. If yes then returns true otherwise false.       |
| <        | Checks whether left operand is less than right operand. If yes then returns true otherwise false.                |
| >=       | Checks whether left operand is greater than or equal to right operand. If yes then returns true otherwise false. |
| <=       | Checks whether left operand is less than or equal to right operand. If yes then returns true otherwise false.    |

**Example**:

```javascript
ar a = 5, b = 10, c = "5";
var x = a;

a == c; // returns true

a === c; // returns false

a == x; // returns true

a != b; // returns true

a > b; // returns false

a < b; // returns true

a >= b; // returns false

a <= b; // returns true

a >= c; // returns true

a <= c; // returns true
```

### Logical Operators

Logical operators are used to combine two or more conditions. JavaScript includes following logical operators.

![logical operator and boolean values image](https://qph.fs.quoracdn.net/main-qimg-bc8139bb7744e28bd6a2512156cc3520)

```javascript
var a = 5, b = 10;

(a != b) && (a < b); // returns true

(a > b) || (a == b); // returns false

(a < b) || (a == b); // returns true

!(a < b); // returns false

!(a > b); // returns true
```

### If statements

The `if` statement evaluates (or checks) a condition. If the condition evaluates to `true`, any statements in the subsequent code block are executed.

![if statement image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRexBOM510QQhbAUXK3rJSIVMep6EF3CpIKug&usqp=CAU)

**if else statement**:

```javascript
if(condition){
    // do something if condition is true
}else {
    // do something if condition is false
}
```

**if else if statement**:

```javascript
if(condition){
    // do something if condition is true
}else if(otherCondition) {
    // do something if otherCondition is false
}else {
    // do something if condition is if no condition is true
}
```
