# Day 5

## Topics: 
###  Events & Handlers
- .addEventListener() method lets us listen for events on a DOM element.
- event.target is the element the event fired on.
- .addEventListener() takes 2 parameters:
1. The name of the event to listen to (e.g. "click").
2. A handler function that JS calls when that event is fired on this element.
```
document.addEventListener("click", (event) => {
    console.log(event);
});
```

### map & filter
- map calls a function on each item in an array to create a new array.
```
const spices = [
    {name: "Emma", nickname: "Baby"},
    {name: "Geri", nickname: "Ginger"},
    {name: "Mel B", nickname: "Scary"},
    {name: "Mel C", nickname: "Sporty"},
    {name: "Victoria", nickname: "Posh"}
];
const nicknames = spices.map(s => s.nickname + " Spice");
```
- filter calls a true/false function on each item and creates a new array with only the items where the function returns true.
```
const mels = spices.filter(s => s.name.includes("Mel"));
```

### Spread (...)
- another neat trick for iterating over arrays.
- We can use it to put all the items from one array inside another array.
- We can also use it to pass all the items from an array as arguments to a function or method.
```
const skills = ["HTML", "CSS", "JS"];
const newSkills = ["React", "TypeScript", "Node"]
skills.push(...newSkills);
console.log(...skills);
```

## challenges
