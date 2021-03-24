# JS Debugging

![js debugging](https://miro.medium.com/max/4000/1*zfmhGkf17LVNDB9LyFrfOA.jpeg)

## ORDER OF EXECUTION

To find the source of an error, it helps to know how scripts are processed. The order in which statements are executed can be complex; some tasks cannot complete until another statement or function has been run:

![js order of EXECUTION image](https://camo.githubusercontent.com/549c0a0cf5b36926ce05907552136ebdce0ec1117849cf6866df9d67f6cda0ee/68747470733a2f2f6c68332e676f6f676c6575736572636f6e74656e742e636f6d2f4b736c726b3355344a2d51726b4f58377a703368554332554942786f725673735548585f79625241554b454c57383638367370744f3165786139724d2d38377349354133304e37346149515a68384e7943657156514f3144343639614e496248385477464673317962506378316130587067395f6d383447724d3353366c6b536772337a57734e354b5a7247335033346d57615f5a7a5f66577a7a5f374d466d6a717343684463724e4c71617a4538776b77476c624c745f62625f61616c655568323647457743445f5776677635696a76504b3251774a6e55364932576d2d4a4d585a454e645378685075696a4a442d3676653754384d716c4a3548365566693157757a584b53732d6c6c756c734d6642506b417a324c6974776a47684b6f506962696a384f62596c67494c543930454b365a6c5238714b626e4347313933434a66473045614f39385551615a365a484a42534452573143356751456341745943536935624d3252436356465a415a56387a42455677656334796664306951486c4e476b6c7070684c7a7776377a504733796874776176395657712d4f52503062724a3269376f334953494b465435495938734f384e574e6b7a7839454e376a6732544555353853534b4e5861746a4735326c3062432d5f7257754b34625870656e6e4e5a6c313432557a426b464773526e3652773839655050516379686c5341393867773376657134444c6a497566696f334f6f365f6a786478502d4d4850363257305f42354c3831653845716f4e7262745f4d4f3958775a4c4a744b61616d745f35365f4c337165334c37316d436d595671416b30436f464c726e387158462d5f4c516d526a57474e7747664f74674d6c4c65454b7765716f76344b546f75376f50795a6d49513057447954446d4b334f3472544c793375414a586a684e4d52424e7158416730673d77313434302d683830352d6e6f)

## Execution context and the stack

Execution context (EC) is defined as the environment in which the JavaScript code is executed. By environment, I mean the value of this, variables, objects, and functions JavaScript code has access to at a particular time.

```javascript
var a = 10;

function functionA() {
    console.log("Start function A");
    function functionB(){
        console.log("In function B");
    }   
    functionB();
}

functionA();

console.log("GlobalContext");
```

![execution context stack image](https://camo.githubusercontent.com/53a024fc2c3cce14cad0fdf59c8d878a002740ce4ae5a184d65ce0dc686e092b/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313430302f312a62446562734f75685278394e4d79764c4859327a78412e676966)

As soon as the above code loads into the browser, JS engine pushes the global execution context in the execution context stack. When functionA is called from global execution context, JS engine pushes functionA execution context in the execution context stack and starts executing functionA.

When functionB is called from functionA execution context, JS engine pushes functionB execution context in the execution context stack. Once all the code of functionB gets executed, JS engine pops out functionB execution context. After this, as functionA execution context is on top of the execution context stack, JS engine starts executing the remaining code of functionA.

Once all the code from functionA gets executed, JS engine pops out functionA execution context from execution context stack and starts executing remaining code from the global execution context.

## ERROR OBJECTS

Error objects can help you find where your mistakes are and browser have tool to help you read them.

The error object provides two useful properties: name and message.

### Error Object Properties

| Property | Description                                 |
| -------- | ------------------------------------------- |
| name     | Sets or returns an error name               |
| message  | Sets or returns an error message (a string) |

### Error Name Values

| Error Name     | Description                                  |
| -------------- | -------------------------------------------- |
| EvalError      | An error has occurred in the eval() function |
| RangeError     | A number "out of range" has occurred         |
| ReferenceError | An illegal reference has occurred            |
| SyntaxError    | A syntax error has occurred)                 |
| TypeError      | A type error has occurred                    |
| URIError       | An error in encodeURI() has occurred         |

**Eval Error** An `EvalError` indicates an error in the `eval()` function.

**Range Error** A `RangeError` is thrown if you use a number that is outside the range of legal values.

For example: You cannot set the number of significant digits of a number to 500.

```javascript
var num = 1;
try {
  num.toPrecision(500);   // A number cannot have 500 significant digits
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

**Reference Error** A `ReferenceError` is thrown if you use (reference) a variable that has not been declared:

```javascript
var x;
try {
  x = y + 1;   // y cannot be referenced (used)
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

**Syntax Error** A `SyntaxError` is thrown if you try to evaluate code with a syntax error.

```javascript
try {
  eval("alert('Hello)");   // Missing ' will produce an error
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

**Type Error** A `TypeError` is thrown if you use a value that is outside the range of expected types:

```javascript
var num = 1;
try {
  num.toUpperCase();   // You cannot convert a number to upper case
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

**URI (Uniform Resource Identifier) Error**:

A `URIError` is thrown if you use illegal characters in a URI function:

```javascript
try {
  decodeURI("%%%");   // You cannot URI decode percent signs
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

## JavaScript Errors - Throw and Try to Catch

The `try` statement lets you test a block of code for errors.

The `catch` statement lets you handle the error.

The `throw` statement lets you create custom errors.

The `finally` statement lets you execute code, after try and catch, regardless of the result.

When executing JavaScript code, different errors can occur.

Errors can be coding errors made by the programmer, errors due to wrong input, and other unforeseeable things.

```html
<p id="demo"></p>

<script>
try {
  adddlert("Welcome guest!");
}
catch(err) {
  document.getElementById("demo").innerHTML = err.message;
}
</script>
```

### JavaScript try and catch

The `try` statement allows you to define a block of code to be tested for errors while it is being executed.

The c`atch statement allows you to define a block of code to be executed, if an error occurs in the try block.

The JavaScript statements try and catch come in pairs:

```javascript
try {
  Block of code to try
}
catch(err) {
  Block of code to handle errors
}
```

### JavaScript Throws Errors

When an error occurs, JavaScript will normally stop and generate an error message.

The technical term for this is: JavaScript will **throw an exception (throw an error)**.

JavaScript will actually create an **Error object** with two properties: **name** and **message**.

### The throw Statement

The **throw** statement allows you to create a custom error.

Technically you can **throw an exception (throw an error)**.

The exception can be a JavaScript `String`, a `Number`, a `Boolean` or an `Object`:

```javascript
throw "Too big";    // throw a text
throw 500;          // throw a number
```

If you use `throw` together with `try` and `catch`, you can control program flow and generate custom error messages.

![web developer tools image](https://www.keycdn.com/img/blog/web-development-tools-lg.webp)

## Use developer tool web browser

You can open developer tools from Chrom by following the steps in the image below.

![Useing developer tool web browser image](https://camo.githubusercontent.com/7f67d6b676564b6ca66498c525f10475892437441e9c79bf6f7e3b177923ef64/68747470733a2f2f646576656c6f706572732e676f6f676c652e636f6d2f7765622f746f6f6c732f6368726f6d652d646576746f6f6c732f696d616765732f6f70656e2d66726f6d2d6d61696e2e706e67)

### What you can do with Dev Tools

1. **Rearrange the text and images on a page**

    With Chrome Dev Tools, you can easily change of the order of elements as they appear on a page by simply dragging them with your mouse. Click the magnifying glass icon, hover over any element of the page - be it text paragraphs, images, or list items - and then drag that selection to place it at a different location.

    ![Rearrange the text and images on a page](https://camo.githubusercontent.com/503fa6d573151d27f0f5acc9617234a5c497e8ded1583780dac09c346618b292/68747470733a2f2f7777772e6c61626e6f6c2e6f72672f33376133613932353962643162343864343936623330663963323537373232622f6f726465722d6c6973742d6974656d732e676966)

2. **Experiment with different colors**:

    Web pages often use the hexadecimal format for writing colors but if the `#AABBCC` format makes no sense to you, just write the color names in plain English like Gold, Aqua and more. Just type the first character and Chrome Dev Tools will show all the available colors that begin with that letter.

    ![Experiment with different colors](https://camo.githubusercontent.com/e0f97fa66fe82d2b95d5d466b2d74fe5415e4ca2ea9bad042af9a089ed939eab/68747470733a2f2f7777772e6c61626e6f6c2e6f72672f62333961663962363238616239316266653365623864346638376233323331392f6368616e67652d636f6c6f72732e676966)

3. **Reveal the Hidden Passwords** Chrome may auto-fill the password field on a login form of a web page but you can’t view that password as it’s hidden behind asterisk characters. You can however use Chrome Dev Tools to change the type of the password input field from “password” to “text” and reveal the hidden password.

4. **Edit your Web Pages** inline Web pages are non-editable in the browser but there’s a little trick that will let you edit web pages inline as you do in a word processor. Open Chrome Dev Tools, switch to the Console tab and type document.body.contenteditable=true at the command prompt. Voila! The page becomes editable.

    ![Edit your Web Pages](https://camo.githubusercontent.com/71b30bf1b3bb062854a65562734adfa38714ee3d64f9a2c034fcd70d72decd13/68747470733a2f2f7777772e6c61626e6f6c2e6f72672f61666161656462613431316663616633393262323662643562396366666263372f636f6e74656e742d6564697461626c652e676966)

5. **Chrome as a Calculator** While the Console tab is active, you can write arithmetic expressions and also perform date calculations like how many days between two dates or write a date as a human-readable string. A little know of the Date object in JavaScript will come handy. Chrome stores the value of the previous calculation in a special $_ variable that can be used in lengthy calculations.

    ![Chrome as a Calculator](https://camo.githubusercontent.com/92bd7a6c5b96186cfbe5ceac65d80ba2c49b324ff7fa0081f969b60b4e71f14b/68747470733a2f2f7777772e6c61626e6f6c2e6f72672f38653831623130616637303735636566333630396330363537376162333266622f646174652d63616c63756c6174696f6e732e676966)
