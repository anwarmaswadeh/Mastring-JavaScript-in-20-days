# Day 3:

## Topics: 
### Statements vs. Expressions
- An expression "asks" JS for a value:
 ```
  myAssignedVariable
  6 + 4
  document.getElementById("board").
```
- A statement "tells" JS to do something (e.g. declare/assign a variable):
 ```
  let ten = 6 + 4;
  myDeclaredVariable = "new value";
  let board = document.getElementById("board");
  ```

### Arrays
- Arrays let us keep multiple values together in a single collection.
- Arrays have a length and each value has an index.
- We can modify arrays.
- We can check if an array contains a certain value.

  **Some methods used in Arrays:**
 - length: find out the length of an array.
 - includes: returns true if an array contains a specified value.
 - push: to add one or more items to the end of an array.
 - pop: to remove the last item from the array.
 - sort: allows you to sort elements of an array in place.
 - join: creates and returns a new string by concatenating all of the elements in an array, separated by commas or a specified separator string.
 - concat: is used to merge two or more arrays, this method does not change the existing arrays but instead returns a new array.

**mutable vs. immutable**
 - "Mutable" data can be edited (e.g. Arrays), "Immutable" data is always the same (e.g. string & other primitives)
 - if u have the choice, using immutable data & variables is usually best.

## challenges:
### [Return a Value from a Function with Return:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)
#### My Solution
```
function timesFive(num) {
    return num * 5;
  }
  
  const answer = timesFive(3);
```
### [Global Scope and Functions:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)
#### My Solution
```
// Declare the myGlobal variable below this line
let myGlobal = 10;

function fun1() {
  oopsGlobal = 5;// Assign 5 to oopsGlobal here

}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```
### [Local Scope and Functions:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)
#### My Solution
```
function myLocalScope() {
    // Only change code below this line
    const myVar = "anwar";
  
    console.log('inside myLocalScope', myVar);
  }
  myLocalScope();
  
  // Run and check the console
  // myVar is not defined outside of myLocalScope
  console.log('outside myLocalScope', myVar);
```
### [Global vs. Local Scope in Functions:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)
#### My Solution
```
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
  const outerWear = "sweater";

  // Only change code above this line
  return outerWear;
}

myOutfit();
```
### [Stand in Line:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)
#### My Solution
```
function nextInLine(arr, item) {
    // Only change code below this line
    arr.push(item);
    const value = arr.shift();
    return value;
    // Only change code above this line
  }
  
  // Setup
  let testArr = [1, 2, 3, 4, 5];
  
  // Display code
  console.log("Before: " + JSON.stringify(testArr));
  console.log(nextInLine(testArr, 6));
  console.log("After: " + JSON.stringify(testArr));
```
