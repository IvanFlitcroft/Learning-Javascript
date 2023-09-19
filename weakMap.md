# Understanding weakMaps

In a previous md file we learnt about garbadge collection, this is a fundamental when learning about weakMaps and weakSets

## What is a weakMap and how is it different to a Map object?

A weakmap is simply a collection of key/value pairs whose keys must be an object or a non registered symbol. This is because we do not want to create a strong reference to the keys of the pair as the keys of weakMaps must be garbage collectable. 

With a map object, the properties are kept in memory while the data structure itself is in memory. In addition, if we add the object to an array but then set the object to null. That array will still exist in memory. With a weakMap object, it allows the properties of the object to be garbage collectable which is much more memory effecient.

## Methods for weakMaps

| Method | What does it do|
| ---|--- |
| weakMap.delete(key) | Removes the value in the weakMap that is associated with the key|
| weakMap.get(key) | Returns the value associated to the key, or undefined if there is none. |
| weakMap.has(key) | Returns a Boolean asserting whether a value has been associated to the key in the WeakMap object or not. |
| weakMap.set(key) | Sets the value for the key in the WeakMap object. Returns the WeakMap object. |

## Examples
```js
let weakMap = new WeakMap();

let obj = {};

weakMap.set(obj, "ok"); // works fine (object key)

// can't use a string as the key
weakMap.set("test", "Whoops"); // Error, because "test" is not an object

```

```js
let user = { name: "Ivan" };

let weakMap = new WeakMap();
weakMap.set(user, "...");

user = null; // overwrite the reference

// user is removed from memory!
```
