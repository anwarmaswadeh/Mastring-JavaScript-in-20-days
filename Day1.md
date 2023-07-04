# Day 1

## Topics: 
###  Introdution to JavaScript
- JavaScript is a dynamic programming language.
- Brendan Eich created JavaScript in 1995 within a span of approximately 10 days.
- JavaScript can be executed in various environments, including web browsers, servers, and embedded devices.

### DOM (Document Object Model)
#### Finding Elements
- document.title : the page (document) title.
- document.body : the body element.
- document.body.children : all the elements within the body.
- document.getElementsById("board") || document.querySelector("#board") : the first element with id = "board". 
- document.getElementsByTagName("h1") || document.querySelectorAll("h1") : all the h1 elements.
- document.getElementsByClassName("player") || document.querySelectorAll(".player") : all the elements with class="player".
- document.getElementsByClassName("player").length || document.querySelectorAll(".player").length : the number of elements with class="player".
- document.getElementById("p1-name").textContent => the text inside the element with id="p1-name".

#### Changing a Web Page
- document.title = "My Page" => change the page title.
- document.getElementById("p1-name").textContent = "Sofia" => replace the text of the #p1-name element.
- document.getElementById("p1-name").append(" & friends") => add to the end of the element's current text.

## Coding Exercises
```html
Finding Elements:

 1. All the p elements
     document.getElementsByName("p").
 2. The text "X"
     document.getElementById("p1-symbol").textContent.
 3. The number of squares in the board
     document.querySelectorAll(".square").length.
 4. The text "A game you know" 
     document.querySelector("h2").textContent.

Changing a Web Page:

 1. Change the player names to you & neighbor
     document.quarySelector("#p1-name").textContent = "Anwar"
     document.quarySelector("#p2-name").textContent = "Salma"
 2. Swap the player symbols
     document.getElementById("p1-symbol").textContent = "O"
     document.getElementById("p2-symbol").textContent = "X"
 3. Change subtitle to "A game you know and love"
     document.querySelector("h2").appened("and love")
```

## challenges
### [Compound Assignment With Augmented Multiplication:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)
#### My Solution
```
let a = 5;
let b = 12;
let c = 4.6;

a = a * 5;
b = 3 * b;
c = c * 10;
```
### [Concatenating Strings with the Plus Equals Operator:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)
#### My Solution
```
let myStr = "This is the first sentence. ";
myStr += "This is the second sentence.";
```
### [Use Bracket Notation to Find the Nth-to-Last Character in a String:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)
#### My Solution
```
const lastName = "Lovelace";

 //Only change code below this line
const secondToLastLetterOfLastName = lastName[lastName.length - 2]; // Change this line
```
