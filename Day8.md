# Day 8

## Topics:
### Intoduction
- Created to run the code of a function has two parts :
1. Goes through the code line-by-line and runs executes each line.
2. Saves data like strings and arrays.
   
###  Callbacks & Higher Order Functions:
- Higher order function is any function that takes in a function or returns out automatically.
- Callback function: The function we insert.
- Makes the code more declarative and readable.

### Arrow Functions
- Shorthand way to save our code.

## challenges
### [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
#### My Solution
```
const squareList = arr => {
  // Only change code below this line
  return arr.filter(num => num > 0 && num % parseInt(num) == 0)
  .map(num => Math.pow(num, 2));
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```

### [Apply Functional Programming to Convert Strings to URL Slugs:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)
#### My Solution
```
// Only change code below this line
function urlSlug(title) {
return title.split(" ")
            .filter(substr => substr !== "")
            .join("-")
            .toLowerCase();

}
// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```
### [Functions and Callbacks:](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
#### My Solution
```
function mapAsync(array, callback) {
  return new Promise((resolve, reject) => {
    const result = [];
    let completed = 0;

    function handleResult(index, value) {
      result[index] = value;
      completed++;

      if (completed === array.length) {
        resolve(result);
      }
    }

    for (let i = 0; i < array.length; i++) {
      callback(array[i], i)
        .then((value) => handleResult(i, value))
        .catch(reject);
    }
  });
}
```

### [Call Stack and Recursion:](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
#### My Solution
```
function sumRange(start, end) {
  if (start === end) {
    return start;
  } else {
    return start + sumRange(start + 1, end);
  }
}
```
