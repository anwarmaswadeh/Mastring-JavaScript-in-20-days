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
### [Rick & Morty Characters List:](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/task.md)
#### My Solution
##### script.js
```
async function fetchCharacters() {
    try {
      const response = await fetch('https:/\
    /rickandmortyapi.com/api/character?status=alive');
      if (!response.ok) {
        throw new Error('Failed to fetch character data');
      }
      const data = await response.json();
  
      const characters = data.results.slice(0, 50);
  
      const characterList = document.getElementById('characterList');
  
      characters.forEach((character) => {
        const listItem = document.createElement('li');
        listItem.innerHTML = `
          <img src="${character.image}" alt="${character.name}">
          <div>
            <h3>${character.name}</h3>
            <p><strong>Location:</strong> ${character.location.name}</p>
            <p><strong>Species:</strong> ${character.species}</p>
            <p><strong>Gender:</strong> ${character.gender}</p>
          </div>
        `;
        characterList.appendChild(listItem);
      });
    } catch (error) {
      const characterList = document.getElementById('characterList');
      characterList.innerHTML = `<li>${error.message}</li>`;
    }
  }
  
  fetchCharacters();
  ```

##### styles.css
```
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 20px;
  }
  
  h1 {
    text-align: center;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    display: flex;
    align-items: center;
    padding: 10px;
    border: 1px solid #ccc;
    margin-bottom: 10px;
  }
  
  img {
    width: 100px;
    height: 100px;
    margin-right: 10px;
    object-fit: cover;
  }
  
  h3 {
    margin: 0;
  }
  
  p {
    margin: 5px 0;
  }
```

##### index.html
```
<!DOCTYPE html>
<html>
<head>
  <title>Alive Character List</title>
  <link rel="stylesheet" href="./styles.css">
</head>
<body>
  <h1>Alive Character List</h1>
  <ul id="characterList"></ul>

  <script src="./script.js"></script>
</body>
</html>
```
