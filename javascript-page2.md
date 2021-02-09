# Javascript

## Comparison and logical operators

You can evaluate a situation by comparing one value in the script to what you except it might be. The result will be a Boolean: `true` or `false`.

* `==` Equall.

* `!=` Is not equall to.

* `===` Strick equall to.

* `!==` Strick not equall to,

* `>` Greator than.

* `<` Less than.

* `>=` Greator than or equall to.

* `<=` Less than or equall to.
  
 **Structuring comparison operators**

In ant condition there is usually one operator and two operand. The operands are placed on each side of the operator. The can be valuse or variables. You often see expressions enclosed in brackets.

`(operand >= operand)` example: `(5 >= 2)`

We can use expressoins with comparison operators as below:

`((score1 + score2 ) > (hightScire1 + hightScore2))`


**Logical operators**

Comparison operators usually return single values iof `true` or `false`. Logical operators allow you to compare the results of more than one comparison operator.

`((5 < 2) && (2 >= 3))`

* `&&` Logical and.

* `||` Logical or.

* `!` Logical not.

## Loops

Loops check a condition. If it returns `true`, a code block will run. Then the condition will be checked again and if it still returns `true`, the code will run again. It repeats untill the condition returns `false`.

There are three common types of loops.

**For**

```javascript
    for(var i = 0; i < 10; i++){
        document,write(i);
    }
```

`var i = 0;` Initialization which creates a variable and set it to zero and it acts as the counter. The variable is only created the first time the loop is run.

`i < 10` The condition that will be checked in every cycle.

`i++` The Update to the variable. It will bw run in every cycle after runing the body of the for statement.

**While**

```javascript
initVariable;
while(condition){
    statements;
    updatingTheVariable;
}
```

In while loop you have to initialize the variable before the while statement and we have to update the variable at the end of while body.

[Next Page](javascript-page3.md)