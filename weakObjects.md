# Understanding weak objects

In a previous md file we learnt about garbadge collection, this is a fundamental when learning about weakMaps and weakSets
## WeakMaps
### What is a weakMap and how is it different to a Map object?

A weakmap is simply a collection of key/value pairs whose keys must be an object or a non registered symbol. This is because we do not want to create a strong reference to the keys of the pair as the keys of weakMaps must be garbage collectable. 

With a map object, the properties are kept in memory while the data structure itself is in memory. In addition, if we add the object to an array but then set the object to null. That array will still exist in memory. With a weakMap object, it allows the properties of the object to be garbage collectable which is much more memory effecient.

### Methods for weakMaps

| Method | What does it do|
| ---|--- |
| weakMap.delete(key) | Removes the value in the weakMap that is associated with the key|
| weakMap.get(key) | Returns the value associated to the key, or undefined if there is none. |
| weakMap.has(key) | Returns a Boolean asserting whether a value has been associated to the key in the WeakMap object or not. |
| weakMap.set(key) | Sets the value for the key in the WeakMap object. Returns the WeakMap object. |

### Examples
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

## WeakSets

WeakSets behave the same way as WeakMaps but they relate to the `Set()` object. An object only exists inside a set if it is reachable from somewhere else.

### Examples

```js
let visitedSet = new WeakSet();

let john = { name: "John" };
let pete = { name: "Pete" };
let mary = { name: "Mary" };

visitedSet.add(john); // John visited us
visitedSet.add(pete); // Then Pete
visitedSet.add(john); // John again

// visitedSet has 2 users now

// check if John visited?
alert(visitedSet.has(john)); // true

// check if Mary visited?
alert(visitedSet.has(mary)); // false

john = null;

// visitedSet will be cleaned automatically
```

## Limitations

WeakSets and WeakMaps cannot be iterated through therefore there is an inabilty to get all the current content.

## Summary

WeakMap is Map-like collection that allows only objects as keys and removes them together with associated value once they become inaccessible by other means.

WeakSet is Set-like collection that stores only objects and removes them once they become inaccessible by other means.

Their main advantages are that they have weak reference to objects, so they can easily be removed by garbage collector (making use for effecient memory usage).

WeakMap and WeakSet are used as “secondary” data structures in addition to the “primary” object storage. Once the object is removed from the primary storage, if it is only found as the key of WeakMap or in a WeakSet, it will be cleaned up automatically.
