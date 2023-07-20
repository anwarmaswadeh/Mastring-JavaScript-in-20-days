# Day 15

## Topics: 
### Hoisting
- We can use hoisting to try to describe something without needing to get into the nitty-gritty details.
- Let dosen't hoist ? -> false.
- Lets and consts still hoist but there is a difference between how they hoist:
  1. let's and consts only hoist to a block, whereas vars hoist to a function.
  2. var when scope starts, initialize it to undefined. let create a location but don't initialize it.

### Closuer
- Closure is  when a function “remembers” its lexical scope even when the function is executed outside that lexical scope.
- We use closure for asynchronous AJAX, and all sort of different things.
- Modules: encapsulate data and behavior (methods) together. The state (data) of a module is held by its methods via closure.

## [challenges](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md)
### ADVANCED SCOPE
#### QUESTION 1:
#### My Solution
```javascript
for (let i = 0; i < 5; i++) {
    setTimeout(function() {
        console.log("value of [i] is: ", i);
    }, 100);
}
```

#### QUESTION 2:
#### My Solution
```javascript
let array = [];

for (let i = 0; i < 5; i++) {
   array.push(i);
   console.log("Current array is: ", array);
}
```

#### QUESTION 3:
#### My Solution
```javascript
let functions = [];

for (let i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```

### CLOSURE
#### QUESTION 1:
#### My Solution
```javascript
function privateCounter() {
  let count = 0;

  function increment() {
    count++;
  }

  function getCount() {
    return count;
  }

  return {
    increment,
    getCount
  };
}

const counter = privateCounter();

counter.increment();
counter.increment();
console.log(counter.getCount()); 
```

#### QUESTION 2:
#### My Solution
```javascript
function generateFibonacci(count) {
  let currentCount = 0;
  let currentFibonacci = 0;
  let nextFibonacci = 1;

  function generateNext() {
    if (currentCount >= count) {
      return null;
    }

    const temp = currentFibonacci;
    currentFibonacci = nextFibonacci;
    nextFibonacci = temp + nextFibonacci;

    currentCount++;

    return currentFibonacci;
  }

  return generateNext;
}

const fibonacciGenerator = generateFibonacci(10);

for (let i = 0; i < 10; i++) {
  console.log(fibonacciGenerator());
}
```
