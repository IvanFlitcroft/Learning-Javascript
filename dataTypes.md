# Understanding data types in javascript

## Primitive data types 

Primitive data types are data types that are not defined as an object and do not have properties or methods 

There are several types of primitive data types:
- string
- number
- bigint
- boolean
- undefined
- symbol
- null

## Big int vs number

BigInt values represent numeric values which are too large to be represented by the number primitive. 

BigInt variables are defined in two ways:
- Placing an `n` infront of an integer declaration
- Wrapping the integer decleration inside a `BigInt()` method
```js
var ageOfEarth = 489374837n;
var ageOfUniverse = BigInt(72374299827398478923);
```

## undefined vs null

Undefined and null may appear similar however theyre very different. Null variables have no value assigned on purpose and the type of object is `object` whereas undefined variables have been declared they just havent been assigned a value and the type of object for an undefined variable is `undefined`

```js
var sleep = null;
var breakfast = undefined;
console.log(typeof(sleep)); //outputs object
console.log(typeof(breakfast));//outputs undefined
```
