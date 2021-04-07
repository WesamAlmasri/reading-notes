# The Call Stack and Debugging

![call stack](https://camo.githubusercontent.com/70d93ef84a13ef59e4a8742cd4707143e7dff406270672ad4dba581387798f09/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f323437382f312a724a3273682d713164655147474756473567597949512e706e67)

## THE CALL STACK

A **call stack** is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

### Example

```javascript
function greeting() {
   // [1] Some codes here
   sayHi();
   // [2] Some codes here
}
function sayHi() {
   return "Hi!";
}

// Invoke the `greeting` function
greeting();

// [3] Some codes here
```

![stack](https://camo.githubusercontent.com/70bf6b6f60682120033d4e598e23aa9197c2a0e3156c839c7c40db3a04eb4006/68747470733a2f2f692e7974696d672e636f6d2f76692f325a485f316438545956672f6d617872657364656661756c742e6a7067)

At the most basic level, a call stack is a data structure that uses the Last In, First Out (**LIFO**) principle to temporarily store and manage function invocation (call).

**LIFO**: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

**Temporarily store**: When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

![stack](https://camo.githubusercontent.com/106e8088696b801f263dab7d4bf940890d6e28cd7d91c8518b1d866265858839/68747470733a2f2f63646e2d6d656469612d312e66726565636f646563616d702e6f72672f696d616765732f5167523275496b37745730594e7a30586d3867306a4150655246493065347343656a7376)

**Manage function invocation (call)**: The call stack maintains a record of the position of each stack frame. It knows the next function to be executed (and will remove it after execution). This is what makes code execution in JavaScript synchronous.

## JavaScript error messages && debugging

![error](https://camo.githubusercontent.com/d94ccbee9cdb0136475a9d6e3a3a74130403025f833a971a20a826327a04d811/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313030302f312a4c48706d7378563366327a6e707868754146754971412e706e67)

### Types of error messages

#### Reference errors

This is as simple as when you try to use a variable that is not yet declared you get this type of errors.

```javascript
console.log(foo) // Uncaught ReferenceError: foo is not defined

foo = 'Hello' // Uncaught ReferenceError: foo is not defined
```

Whatever you are using (var, let or const) the fix is as simple has declaring the variable before any declaration is made.

```javascript
let foo;
foo = 'Hello'
```

#### Syntax errors

```javascript
JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1
```

This can be solved by just fixing the syntax, in this case the object should be a JSON.

```javascript
JSON.parse('{"foo":"bar"}')
```

##### Range errors

Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

```javascript
var foo= []
foo.length = foo.length -1 // Uncaught RangeError: Invalid array length
```
