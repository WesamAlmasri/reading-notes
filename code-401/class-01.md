# Node Ecosystem, TDD, CI/CD

## `Array map()`

This is an array method which accept a function as parameter and do the following:

- Iterate over all the elements in an array and excute a function on each iteration that accept the array's element and it's index as parameter.

- Return a new array and the elements of the new array is the returned value in each iteration.

**Syntax**:

```javascript
Array.map(function(item, index){
    //body of the function
})
```

## `Array reduce()`

This is an array method which accept a function as parameter and do the following:

- Reduce the array to a single value and it could be any type of data.
- Iterate over all the elements in the array and execute the input function on each iteration.
- The function accept a cumulative variable that returned from the last iterator as argument, the current element in the array and it's index.
- The reduce function take an optional argument as the initial value of the accumulator

**Syntax**:

```javascript
Array.reduce(function callbackFn(accumulator, currentValue) { ... }, intialValueAcc)
```

## `superagent()`

**`Promise.then()` syntax**:

```javascript
const superagent = require('superagent');

let url = 'https://geocode.xyz/Amman?json=1'

superagent.get(url)
    .then((response) => {
        return console.log(response.body);
    })
    .catch(error => console.log(error));
```

**`async/await` syntax**:

```javascript
const superagent = require('superagent');


async function getData(){
    let url = 'https://geocode.xyz/Amman?json=1'

    try {
        let data = await superagent.get(url);
        console.log(data.body);
    } catch(e) {
        console.log(e);
    }
}

getData();
    
```

## Promises

**JavaScript Promises** allows you to associate handlers with an asynchronous action's eventual success value or failure reason. This lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.

```javascript
function isEven(num){
  return new Promise((resolve , reject)=>{
    if(num % 2 == 0){
      resolve(num)
    }else{
      reject("not a even number")
    }
  })
}

let numArray = [1,2,3,4,5,6,7,8,9]
numArray.forEach(num=>{
  isEven(num)
  .then(data=>{
    console.log(data)
  })
  .catch(err=>{
    console.log(err)
  })
})
```

## Are all callback functions considered to be Asynchronous? Why or Why Not?

No , not every call back considerred as asynchronous. for examply the forEach consider as a call back function but not a asynchronous.