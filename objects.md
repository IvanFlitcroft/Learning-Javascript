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

```js

let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];

```

let key = prompt("What do you want to know about the user?", "name");

// access by variable
alert( user[key] ); // John (if enter "name")

