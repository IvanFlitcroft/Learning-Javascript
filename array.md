# Understanding arrays

This is just a short description of what an array is and how to create one in javascript

## What is an array object

## Creating an array

To create an array simply define a variable and equate it to square brackets

```js
Const Outfit = []

```

## Common array methods

| Method | What does it do |
| --- | --- |
| array.push() | Adds an item to an array |
| array.pop() | Removes an item from an array |
| array.map() | Acts like the map function in haskell. Creates a new array that has the results produced from the map function |
| array.concat() | Concatonates two arrays together |
| array.join() | It joins the elements of the array together 
```js
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// Expected output: "Fire,Air,Water"

console.log(elements.join(''));
// Expected output: "FireAirWater"

console.log(elements.join('-'));
// Expected output: "Fire-Air-Water"
 
```
 |
| array.slice() | Returns a shallow copy of a portion of an array into a new array object 
```js
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// Expected output: Array ["camel", "duck", "elephant"]
```
 |
