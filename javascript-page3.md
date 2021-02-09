## A FUNCTION

Functions let you group a series of statements together to perform a specific task. If different parts of a script repeat the same task, you can reuse the function (rather than rep eating the same set of st atements).

**Declaring a function**

To create  a function, follow the syntax below:

```javascript
function fuctionName (params,){
    instructions // (you can use params here)
    return returnedValue
}


```

**Calling a function**

To call a function just use 

```javascript
functionName (params,);
```

If the functoin return some value, you can store the returned value in a variable.

```javascript
var value = functionName (params,);
```

You can return multiple values from the function using an array.

```javascript
function fuctionName (wisth, height, depth){
    var area = width * height;
    var volume = area * depth;
    var size = [area, volume];
    return size;
}


```