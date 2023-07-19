# Day 13

## Topics: 
### Static Typing
#### TypeScript & Flow
- Benefits:
1. Catch type-related mistakes.
2. Communicate type intent.
3. Provide IDE feedback.
- Caveats:
1. Inferencing is best-guess, not a guarantee.
2. Annotations are optional.
3. Any part of the application that isn't typed introduces uncertainty.

### Scope
- The kinds of references to a marble are: source and target.
- source: receiving a value.
- target: retrieve its value.
- undeclare never formally declared in any scope that we have accessed to & in strict mode it always results in that ref area & doesn`t exist.
- undefined doesn`t exist & doesn`t have a value.
- Lexical scope Elevator: The first floor is our current scope where the referenve is, and the top floor is the global scope.

## [challenges](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)
### STATIC TYPING QUESTIONS
#### Question 1:
##### My Solution:
 ```javascript
interface HelloWorldPromise {
  (): Promise<string>;
}

interface BooleanCheckPromise {
  (boolean: boolean): Promise<boolean>;
}

interface ReturnObjPromise {
  (): Promise<{ x: string; y: number }>;
}

type PromisesArray = [HelloWorldPromise, BooleanCheckPromise, ReturnObjPromise];

const sayHelloWorld: HelloWorldPromise = () =>
  new Promise((resolve, reject) => {
    resolve("Hello world!");
  });

const checkBoolean: BooleanCheckPromise = (boolean) =>
  new Promise((resolve, reject) => {
    if (boolean) {
      resolve(boolean);
    } else {
      reject(`Input is false :(`);
    }
  });

const returnObj: ReturnObjPromise = () =>
  new Promise((resolve, reject) => {
    resolve({
      x: "meow",
      y: 45,
    });
  });

const promisesArray: PromisesArray = [sayHelloWorld, checkBoolean, returnObj];

const convertToObj = async (array: PromisesArray) => {
  const obj = {};
  for (const promise of array) {
    const result = await promise();
    Object.assign(obj, result);
  }
  return obj;
};
```
### SCOPE & HOISTING QUESTIONS
#### Question 1:
##### My Solution:
- C) 1, ReferenceError, ReferenceError.
-  var has function scope, so it is accessible within the entire testScope1 function, let & const has block scope, It is only accessible within the if block.

#### Question 2:
##### My Solution:
- A) undefined, ReferenceError, ReferenceError.
-  variable a (var) is hoisted to the top of the function scope, let and const have block scope, It is not hoisted to the top of the block.

  #### Question 3:
  ##### My Solution:
- C) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1,100, 45 ]
-  The first console.log refers to the outer variables, The second console.log inside the if block refers to the newly declared variables,The third console.log after the if block, the outer variables have been modified by the inner block
 
