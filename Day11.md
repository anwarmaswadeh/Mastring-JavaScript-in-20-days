# Day 11

## Topics: 
### Classes & Prototypes (OOP)
#### The Object-oriented paradigm aims is to let us achieve these three goals in our code:
1. Easy to reason about.
2. Easy to add features to (new functionality).
3. Nevertheless efficient and performant.

#### Our code is getting repetitive, we're breaking our DRY principle. And suppose we have millions of users!
#### What could we do?

#### Solution 1. Generate objects using a function
- Benefits: It's simple and easy to reason about!
```javascript
  function userCreator(name, score) {
  const newUser = {};
  newUser.name = name;
  newUser.score = score;
  newUser.increment = function() {
  newUser.score++;
  };
  return newUser;
 };
 const user1 = userCreator("Will", 3);
 const user2 = userCreator("Tim", 5);
 user1.increment()
```
#### Solution 2: Using the prototype chain
- Benefits: Super sophisticated but not standard.
```javascript
 function userCreator (name, score) {
 const newUser = Object.create(userFunctionStore);
 newUser.name = name;
 newUser.score = score;
 return newUser;
 };
 const userFunctionStore = {
 increment: function(){this.score++;},
 login: function(){console.log("Logged in");}
 };
 const user1 = userCreator("Will", 3);
 const user2 = userCreator("Tim", 5);
 user1.increment();
```

#### Solution 3 - Introducing the keyword that automates the hard work: new
- Benefits:Faster to write. Often used in practice in professional code.
1. Create a new user object
2. Return the new user object
```javascript
 function userCreator(name, score){
 this.name = name;
 this.score = score;
}
userCreator.prototype.increment = function(){ this.score++; };
userCreator.prototype.login = function(){ console.log("login"); };
const user1 = new userCreator(“Eva”, 9)
user1.increment()
```

#### Solution 4: The class ‘syntactic sugar’
- Benefits:
1. Emerging as a new standard.
2. Feels more like style of other languages (e.g. Python).
```javascript
 class UserCreator {
 constructor (name, score){
 this.name = name;
 this.score = score;
 }
 increment (){ this.score++; }
 login (){ console.log("login"); }
}
const user1 = new UserCreator("Eva", 9);
user1.increment();
```
