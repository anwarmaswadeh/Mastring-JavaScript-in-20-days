# Day 10

## Topics: 
### Asynchronous
- Asynchronicity is the backbone of modern web development in JavaScript yet.
- setTimeout is a built in function - its first argument is the function to delay followed by ms to delay by:
  ```
  function printHello(){
  console.log("Hello");
  }
  setTimeout(printHello,1000);
  console.log("Me first!");
  ```

### Promises
- Returned immediately when we make a call to a web browser API/feature (e.g. fetch) that’s set up to return promises.
Benefits
- Cleaner readable style with pseudo-synchronous style code
- Nice error handling process

## challenges
### [Asynch & Promises Questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md)
#### Question 1:
##### My Solution
```javascript
const executeInSequenceWithCBs = async (tasks, callback) => {
  const messages = [];

  for (const task of tasks) {
    await new Promise((resolve) => {
      task((message) => {
        messages.push(message);
        resolve();
      });
    });
  }

  callback(messages);
};

executeInSequenceWithCBs(asyncTasks, (messages) => {
  console.log(messages);
});
```
#### Question 2:
##### My Solution
```javascript
const executeInParallelWithPromises = (apis) => {
  const promises = apis.map(async (api) => {
    const response = await fetch(api.apiUrl);
    const apiData = await response.json();
    return { apiName: api.apiName, apiUrl: api.apiUrl, apiData };
  });

  return Promise.all(promises);
};

executeInParallelWithPromises(apis)
  .then((results) => {
    console.log(results);
  })
  .catch((error) => {
    console.error(error);
  });
```
#### Question 3:
##### My Solution
```javascript
const executeInSequenceWithPromises = (apis) => {
  if (apis.length === 0) {
    return Promise.resolve([]);
  }

  const [currentApi, ...remainingApis] = apis;
  return fetch(currentApi.apiUrl)
    .then((response) => response.json())
    .then((apiData) => {
      const result = {
        apiName: currentApi.apiName,
        apiUrl: currentApi.apiUrl,
        apiData,
      };
      return executeInSequenceWithPromises(remainingApis).then(
        (nextResults) => [result, ...nextResults]
      );
    });
};

executeInSequenceWithPromises(apis)
  .then((results) => {
    console.log(results);
  })
  .catch((error) => {
    console.error(error);
  });
```
