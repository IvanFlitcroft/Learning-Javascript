# Understanding typeCasting in js

Type casting is just a fancy word that means transferring the data from one type of variable to another e.g string to integer 
When I used c# there were methods like Cint() or Cstr() that could typeCast for you. Luckily in javascript, it is much the same with typecasting happening automatically in many cases, for example with the `alert()` method, it converts any of its content into a string automatically.

## How do we typeCast

typeCasting will occur when we wrap a value in a method that is called the data type that we want.
For example, If we want to convert a integer to a string then we would simply wrap it in `String()`

```js
let value = 123;
console.log(typeof value); //number

value = String(value); 
console.log(typeof value); //string

```
