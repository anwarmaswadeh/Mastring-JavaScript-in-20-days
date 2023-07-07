# Day 4:

## Topics: 
### Objects
- Objects collect multiple values together to describe more complex data.
- Getting property values:
  ```
  js.name
  ```
- Using property values:
  ```
  js.name.startsWith("Java")
  ```
 - Setting property values:
   ```
   const indecisive = {
   lunch: "sandwich"
   };

   indecisive.lunch = "tacos";
   indecisive.snack = "chips";
   ```

### Functions
- Some functions need more than one value to work
```
function add(x, y) {
    return x + y;
}
add(2,3);
```
- Some functions don't even need any values
```
function getRandomNumber() {
    return Math.random();
}

getRandomNumber();
```
- parameters are the inputs a function expects
- arguments are the actual values the function is called with

### Arrow Functions
- For one-parameter functions, parentheses are optional, but for multiple parameters, parentheses are required.

## Coding Exercises:

Functions:

1. given 2 numbers, return their product:
```
function multiply(a,b){
return a*b;
}
```
2. given a lowercase string, log it in all caps to the console:
```
const yell = function(word){
   return word.toUpperCase();
}
```
3. longerThan: given 2 arrays, return whether the first is longer than the second:
```
function largerThan(ar1,ar2){
  return ar1.length > ar2.length;
}
```

Working With Strings:

1. given 2 numbers, return the first divided by the second:
```
   const divide = (a,b) => a / b;
```

 2. given an uppercase string, log it in all lowercase to the console:
```
    const toLower = (word) => console.log(word.toLowerCase());
```

 3. given 2 arrays, return whether the first is shorter than the second:
```
    const shorterThan = (ar1 , ar2) => ar1.length < ar2.length;
```

## challenges:
### [Use Multiple Conditional (Ternary) Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)
#### my solution:
```
function checkSign(num) {
    return (num > 0) ? "positive" : (num < 0) ? "negative" : "zero";
    }
  
  checkSign(10);
```
### [Golf Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)
#### my solution:
```
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  return strokes === 1 ? names[0] : strokes <= par - 2 ? names[1] : strokes === par - 1 ? names[2] : strokes === par ? names[3] : strokes === par+1 ? names[4] : strokes === par +2 ? names[5] : names[6] ;
}
golfScore(5, 4);
```
### [Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)
#### my solution:
```
const ratings = watchList.map(item => ({
  title: item["Title"],
  rating: item["imdbRating"]
}));
console.log(JSON.stringify(ratings));
```
### [Use the filter Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)
#### my solution:
```
const filteredList = watchList
  .filter(movie => {
    return parseFloat(movie.imdbRating) >= 8.0;
  })
  .map(movie => {
    return {
      title: movie.Title,
      rating: movie.imdbRating
    };
  });
console.log(filteredList);
```
