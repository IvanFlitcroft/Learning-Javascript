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
```js
var name = "Ivan";
var age = 18;
var ageOfEarth = 489374837n;
var ageOfUniverse = BigInt(72374299827398478923);
var glasses = "true";

var sleep = null;
var breakfast = undefined;
```
## Big int vs number

BigInt values represent numeric values which are too large to be represented by the number primitive. 

BigInt variables are defined in two ways:
- Placing an `n` infront of an integer declaration
- Wrapping the integer decleration inside a `BigInt()` method
```js
var ageOfEarth = 489374837n;
var ageOfUniverse = BigInt(72374299827398478923);
```
## Symbol
```js
var Sym1 = Symbol("Description");
```
symbols are defined using the wrapper method `Symbol()` (ensure you use a CAPITAL s) and you cannot create the same symbol twice in a function or program. Symbols are immutable.
You can pass an optional string as its description. For example,

```js
const x = Symbol('hey');
console.log(x); // Symbol(hey)
```

And you can access the description by using `.description` at the end of the symbol variable
```js
console.log(x.description); // will output hey
```

You can add also symbols as a key in an object using square brackets []. For example,

```js
var id = Symbol("id");
var person = {
    name: "Ivan",

    // adding symbol as a key
    [id]: 123 // not "id": 123
};

console.log(person); // will output {name: "Ivan", Symbol(id): 123}
```
## undefined vs null

Undefined and null may appear similar however theyre very different. Null variables have no value assigned on purpose and the type of object is `object` whereas undefined variables have been declared they just havent been assigned a value and the type of object for an undefined variable is `undefined`

```js
var sleep = null;
var breakfast = undefined;
console.log(typeof(sleep)); //outputs object
console.log(typeof(breakfast));//outputs undefined
```
