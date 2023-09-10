# Understanding objects in javaScript

With Primitives, the variables only contain one value such as a number or string, however with objects, the variable can store keyed collections of various data and even more objects (such as an array inside another array).

## creating an object

Objects are created by using `{}` or by using the wrapper method of `new Object()`. The use of `{}` is known as object literal, and the use of `new Object()` is known as object constructor.

```js
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
```

Within the brackets or wrapper method, we can insert properties which are known to acts as a key value pair, for example 

```js
let user = {     // an object
  name: "Ivan",  // key "name" will store value "Ivan"
  age: 18        // by key "age" store value 18
};
```
Note -> it follows this structure `keyName: keyValue`

Object properties can be accessed by doing `objectName.keyName`

## Square brackets in an object

If we want to use properties that are multiword, we cannot use normal notation and so we must use square brackets such as the example below.
```js

let user = {};

// set
user["Has glasses"] = true;

// get
alert(user["Has glasses"]); // true

// delete
delete user["Has glasses"];
```
Here we wanted to create a property that would state whether the user had glasses.

### square brackets with prompts
```js
let user = {
  name: "Ivan",
  age: 18
};

let key = prompt("What do you want to know about the user?", "name");

// access by variable
alert( user[key] ); // Ivan (if enter "name")

```

Here we defined an object called user and gave it two properties. After, we instantiated a prompt (called key) which will prompt the client to enter something they want to know about the user. 
Because the prompt has `,"name"`, if they enter "name" then it will return user[name] which will be Ivan.

### computed properties

Using the example with prompts, we can actually use a prompt to form a property as we can see in this example

```js
let fruit = prompt("Which fruit to buy?", "apple"); // define a prompt and an answer we want

let bag = {
  [fruit]: 5, // the name of the property is taken from the variable fruit. Essentially we are saying there are 5 of the fruit if that fruit is mentioned during the prompt
};

alert( bag.apple ); // 5 if fruit="apple"
```
In the above example, the properties of bag will become {apple: 5} if the user enters apple.

## Property creation shortcut

Wasnt too sure on a title for this part but I think this summarises the point well. Lets say we had a function that would create a user when given two parameters `name and age`

```js
function createUser(name, age) {
  return {
    name: name,
    age: age,
    // ...other properties
  };
}

let user = createUser("Ivan", 18);
alert(user.name); // Ivan
```
As you can see we gave the function two values and we returned the values as properties to the object. Well there is actually a quicker way to do this. Instead of writing `name:name` we can just write `name` like this,

```js
function createUser(name, age) {
  return {
    name, // same as name: name
    age,  // same as age: age
    // ...
  };
}
```
