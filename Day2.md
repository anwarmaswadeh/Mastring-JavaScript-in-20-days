# Day 2:

## Topics: 
### Values And Data Types
- Values are chunks of information we want to work with.
- We can cast on a value to find out its type by using "typeof".
- JavaScript has two kinds of data, such as:
  1. Primitive types (e.g. srtings, numbers).
  2. Objects (e.g. documents & friends).

### Working With Strings
- Strings are made of characters.
- .length returns how many characters are in the string.
- Characters are in a specific order; each gets a number, starting at 0.
- .indexOf returns the index of a specific character.
- .includes returns if the string contains some other string or not.
- .startWith returns if the string starts with some other string or not.
- To connect strings together we use the `+` operator.

## Coding Exercises:
```html
Values And Data Types:

Which data type is each of these Values:
  1. false:
      boolean
  2. "true":
      string
  3. doucment.title:
      string
  4. "Some string".length:
      number
  5. null :
      object

Working With Strings:

  1. Add ypur  last name in the players listing:
      document.getElementById("p1-name").append(" Maswadeh").
  2. Retrieve the first "T" in the page title:
      document.title.indexsOf("T")
      document.title[9].
  3. Aswer whether the page title contain the string "JavaScript":
      document.title.include("JavaScript").
  4. Capitlize the heading "Tic Tac Toe":
     doucument.querySelector("header h1").textContent = doucument.querySelector("header h1").textContent.toUpperCase().
```
## challenges:
### [Profile Lookup:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)
#### My Solution
```
const contacts = [
    {
      firstName: "Akira",
      lastName: "Laine",
      number: "0543236543",
      likes: ["Pizza", "Coding", "Brownie Points"],
    },
    {
      firstName: "Harry",
      lastName: "Potter",
      number: "0994372684",
      likes: ["Hogwarts", "Magic", "Hagrid"],
    },
    {
      firstName: "Sherlock",
      lastName: "Holmes",
      number: "0487345643",
      likes: ["Intriguing Cases", "Violin"],
    },
    {
      firstName: "Kristian",
      lastName: "Vos",
      number: "unknown",
      likes: ["JavaScript", "Gaming", "Foxes"],
    },
  ];
  
  function lookUpProfile(name, prop) {
    // Only change code below this line
  
    for (let i = 0; i < contacts.length; i++) {
      if (contacts[i].firstName === name) {
        if (prop in contacts[i]) {
          return contacts[i][prop];
        } else {
          return "No such property";
        }
      }
    }
    return "No such contact";
  
    // Only change code above this line
  }
  
  lookUpProfile("Akira", "likes");
```
### [Copy Array Items Using slice():](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)
#### My Solution
```
// Only change code below this line
  
    return arr.slice(2, 4);
  }
  // Only change code above this line
  console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```
### [Combine Arrays with the Spread Operator:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)
#### My Solution
```
function spreadOut() {
    let fragment = ['to', 'code'];
    let sentence = ['learning', ...fragment, 'is', 'fun']; // Change this line
    return sentence;
  }
  
  console.log(spreadOut());
```
