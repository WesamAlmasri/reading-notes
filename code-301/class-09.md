# Refactoring

![refactoring](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200922214602/7-Code-Refactoring-Techniques-in-Software-Engineering.png)

## Refactoring JavaScript

Think of refactoring your code as re-writing it so that it’s easier to read and easier to work with in the future.

```
<Checkbox
    checked={goldState}
    onChange={toggleGold}
    className="check"
    style={{ color: "white", fontFamily: "Baloo Bhai" }}
>
    Gold
</Checkbox>
<Checkbox
    checked={elixirState}
    onChange={toggleElixir}
    className="check"
    style={{ color: "white", fontFamily: "Baloo Bhai" }}
>
    Elixir
</Checkbox>
<Checkbox
    checked={darkState}
    onChange={toggleDark}
    className="check"
    style={{ color: "white", fontFamily: "Baloo Bhai" }}
>
    Dark Elixir x100
</Checkbox>
```

### Refactored Code

```
interface LootTypeCheckboxProps {
  checked: boolean;
  onChange: (checked: boolean) => void;
  text: string;
}

const LootTypeCheckbox = ({
  checked,
  onChange,
  text
}: LootTypeCheckboxProps) => {
  return (
    <Checkbox
      checked={checked}
      onChange={e => onChange(e.target.checked)}
      className="check"
      style={{ color: "white", fontFamily: "Baloo Bhai" }}
    >
      {text}
    </Checkbox>
  );
};

<LootTypeCheckbox
  checked={goldState}
  onChange={toggleGold}
  text="Gold"
/>

<LootTypeCheckbox
  checked={elixirState}
  onChange={toggleElixir}
  text="Elixir"
/>

<LootTypeCheckbox
  checked={darkState}
  onChange={toggleDark}
  text="Dark Elixir x100"
/>
```

### The Basics of Refactoring Your Code

To refactor your code, you can basically go through a fairly simple 3 step process. If you implement this into your coding habits, you will notice fairly quickly that your code will start to look much more professional and tidy. The image below shows the typical 3 step process that you should go through when refactoring your code.

![image](https://camo.githubusercontent.com/0d61eedfe52646223c8080350c5cf02168d519498bc74ac0d7bd44d88bc053fa/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313032342f312a6e4358366273534e55465f763268464b676e615149412e706e67)

## Functional Programming in JavaScript

we used to use Object-Oriented Programming in most of our real-world use-cases for better or for worse. Most use-cases of Functional Programming back then rely solely on mathematical computations whether simple or complex and the usage of it in components like buttons, textbox, checkbox never really fit in most of our scenarios.

### What is Functional Programming?

Functional Programming is a programming paradigm where you mostly construct and structure your code using functions. These functions take input which is called as arguments then shows the output based on the inputs being taken which, given the same input always results in the same output.

### Features of Functional Programming

1. First-Class Citizen Functions

    What’s good about Functional Programming is its functions are first-class citizens: you can always insert functions inside a function without any restrictions present.

    ```javascript
    function executeFunctions(x, y) {
        const add = (x, y) => x + y;
        const subtract = (x, y) => x — y;
        console.log(`sum: ${add(x,y)}`);
        console.log(`difference: ${subtract(x,y)}`);
    }
    ```

2. Higher-Order Functions

    A higher-order function is a function that gets a function as an argument. It may or may not return a function as its resulting output.

    ```javascript
    function greaterThan(n) {
    return x => x > n;
    }
    let greaterThanTwo = greaterThan(2);
    console.log(greaterThanTwo(5));
    ```

3. Function Composition

    Functional Programming won’t be completely functional without this feature. Function Composition is an act of composing/creating functions that allow you to further simplify and compress your functions by taking functions as an argument and return an output. It may also return another function as its output other than numerical/string values.

### Benefits of Functional Programming

1. It doesn’t have side-effects and it’s immutable
2. It’s clean, straightforward, succinct

### Exporting/Importing simple pure function

We can export and use a simple pure function such as this one in Bit’s tooling then reuse it in our various projects:

![pure function](https://camo.githubusercontent.com/b25d8a6f05aff1a9f59aa21411cb1a76d24f1f949f60c16a4ff5f36cafa233e2/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313136362f312a536e58515734695f6c32337772376439517a353257772e706e67)
