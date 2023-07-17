# Day 12

## Topics: 
### Types 
- In JavaScript, not everything is an object.
- Objects: object, function, and array.
- Not objects: undefined, string, number, boolean, object, symbol, null, and bigint.
- In JavaScript, variables don't have types, values do.
##### typeof:
   ```javascript
   var v;
   typeof v; // undefined
   v = "1";
   ```
   ```javascript
   v = {};
   typeof v; // object
   ```
   ```javascript
   var x = 42n;
   typeof x; //Bigint.
   ```
##### undefined vs. undeclared vs. uninitialized 
- undefine: there's definitely a variable, and at the moment, it has no value.
- undeclared: its never been created in any scope.
- uninitialized: variable in block scope don`t ge initialized.

##### Special Values
- NaN not a number.
- NaN: Invalid Number:
1. undefined
2. null
3. false
4. -1
5. 0
- undefined are equal itself.
  
##### Negative Zero
```javascript
 var v = -0;
 v.toString(); //0
```

## [challenges](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
#### Question 1:

```javascript
function convertStringToNumber(input) {
  if (typeof input === 'string') {
    return +input;
  } else {
    return {
      value: input,
      type: typeof input
    };
  }
}
```

#### Question 2:

```javascript
const checkNaN = (value) => {
  return value !== value;
}
```

#### Question 3:

```javascript
function isEmptyValue(value) {
  return value === undefined || value === null || value === "";
}
```

#### Question 4:

```javascript
function compareObjects(input1, input2) {
  if (typeof input1 !== 'object' || typeof input2 !== 'object') {
    return [input1, input2];
  }

  const keys1 = Object.keys(input1);
  const keys2 = Object.keys(input2);

  if (keys1.length !== keys2.length) {
    return false;
  }

  for (let key of keys1) {
    if (!input2.hasOwnProperty(key) || input1[key] !== input2[key]) {
      return false;
    }
  }

  return true;
}
```

#### Question 5:

```javascript
const complexCoercion = (input) => {
  if (typeof input === 'number') {
    return Boolean(input.toString());
  } else if (typeof input === 'string') {
    return Boolean(input);
  } else if (input === null || input === undefined) {
    return false;
  } else {
    return input;
  }
};
```
