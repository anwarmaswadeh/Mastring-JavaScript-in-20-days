# Day 6

## Topics: 
###  Fetching Data
- URLs point to resources on the web.
`https://images.dog.ceo/breeds/bluetick/n02088632_924.jpg`
- APIs or application programming interfaces are services that exposing a whole bunch of data at certain URLs.
- APIs provide URLs that point at data we care about.

### Promises
- `fetch()` lets us use JS to load data from APIs.
```fetch("https://dog.ceo/api/breed/hound/list")```
- Promises can be in 3 possible states:
```
1. pending: still waiting for the value, hang tight.
2. fulfilled (aka "resolved"): finally got the value, all done.
3. rejected: sorry couldn't get the value, all done.
```
- It takes time for Promises to resolve, so they are `asynchronous`.

### await
- await lets us tell JS to stop and wait for an asynchronous operation to finish.
- The Promise we get from `fetch()` resolves to a `Response` object.
```
  let response = await fetch("https://dog.ceo/api/breed/hound/list");
console.log(response);
```
- Calling the .json() method on the response parses its body as a JSON object
```
  response.json()
```

### Destructuring Data
- Destructuring is a fancy way of declaring multiple variables at once.
  ```
  let {name, nickname} = spices[0];
  ```
- We can destructure, ignore, and use commas to "skip" values n the array.

### Async Functions
- If we try to await something in a regular function, JS doesn't allow it, so we need to make it an async function.
- ```
  async function fetchResponse(url) {
    const response = await fetch(url);
    return response;
}
```

     document.quarySelector("#p2-name").textContent = "Salma"
 2. Swap the player symbols
     document.getElementById("p1-symbol").textContent = "O"
     document.getElementById("p2-symbol").textContent = "X"
 3. Change subtitle to "A game you know and love"
     document.querySelector("h2").appened("and love")
