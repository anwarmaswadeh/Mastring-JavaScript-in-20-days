# Day 14

## Topics: 
### Scope & Function Expressions

### Advanced Scope
- The most predominat example of the dynamic scoping model is actully Bash script.
- Lexical scope is actually so populas is because it's optimizable.
- Even though Js dose not have dynamic scope , JS have a mechanism that gives us this same kinds so flexibility.
- Dynamic scope that is determined based on conditions at runtime, whereas lexical scope is determined at author time.

## challenges
### [Scope & Function Expressions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day3-tasks/tasks.md)
#### Question 1
#### My Solution
```javascript
const exampleNormalFunc1 = (a, b, c) => {
  return a * (b + c);
};

const exampleNormalFunc2 = (x, y) => {
  return x * y;
};

const exampleNormalFunc3 = (string) => {
  return string + " " + string + " " + string + "!";
};

const arrowHOF = (normalFunc) => {
  return (...args) => {
    return (...repeatTimes) => {
      const result = normalFunc.apply(null, args);
      const times = repeatTimes.length > 0 ? repeatTimes[0] : 1;
      return Array(times).fill(result);
    };
  };
};

const hofNormalFunc1 = arrowHOF(exampleNormalFunc1);
const hofNormalFunc2 = arrowHOF(exampleNormalFunc2);
const hofNormalFunc3 = arrowHOF(exampleNormalFunc3);

console.log(hofNormalFunc1(3, 4, 5)(2)); // logs [60, 60] (twice)
console.log(hofNormalFunc2(20, 35)(4)); // logs [700, 700, 700, 700] (four times)
console.log(hofNormalFunc3("Meow")()); // logs ["Meow Meow Meow!"] (once)
```

#### Question 2
#### My Solution
```javascript
const preserveThis = (func) => {
  return func.bind(func['this']);
};

// Example object
const obj = {
  name: 'John',
  greet: function (greeting) {
    console.log(`${greeting}, ${this.name}!`);
  }
};

// Wrap the greet function using preserveThis
const preservedGreet = preserveThis(obj.greet);

// Call the wrapped function as a method of the object
preservedGreet('Hello'); // Output: "Hello, John!"
```

#### Question 3
#### My Solution
```
Reasoning for example 1's output:
In this example, we have two functions: outer1 and inner1.
outer1 declares a variable x with a value of 10 and then defines the inner1 function, which logs the value of x.
When outer1() is called, it executes inner1(). 
Since inner1 is a closure, it has access to the variables defined in its parent function, outer1.
Therefore, when inner1() is called, it logs the value of x, which is 10.
```

```
Reasoning for example 2's output:
In this example, we have two functions: outer2 and inner2.
outer2 declares a variable x with a value of 10 and then defines the inner2 function.
Inside inner2, there's another variable x declared with a value of 20.
When inner2() is called, it logs the value of the inner x, which is 20.
Although inner2 is a closure and has access to variables in its parent function, the inner x variable shadows the outer x variable.
Therefore, when inner2() is called, it logs the value of the inner x, which is 20.
The outer x variable with a value of 10 remains unchanged and is not affected by the inner x variable declaration.
```
