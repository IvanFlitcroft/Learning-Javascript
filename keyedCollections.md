# Understanding keyed collections
Keyed collections are data collections that are ordered by key not index
there are 2 tyoes if keyed collections:
- Map object
- set object

## Map object

Map is similar to a dictionary in c#, you insert key value pairs and can iterate through them via insertion order.

### Map methods

|Method|What does it do|
|---|---|
|.set(key,value)|Inserts the key value pair into the map object|
|.get(key)|Gets the value associated with the key|
|.has(key)|Checks if the map object contains that key, will output true/false|
|.delete(key)|deletes the key value pair associated with that key|
|.size|Returns the current size of the map ie how many key value pairs there are|

### Example

```js
const sayings = new Map();
sayings.set("dog", "woof");
sayings.set("cat", "meow");
sayings.set("elephant", "toot");
sayings.size; // 3
sayings.get("dog"); // woof
sayings.get("fox"); // undefined
sayings.has("bird"); // false
sayings.delete("dog");
sayings.has("dog"); // false

for (const [key, value] of sayings) {
  console.log(`${key} goes ${value}`);
}
// "cat goes meow"
// "elephant goes toot"

sayings.clear();
sayings.size; // 0

```
## Set object

The Set object lets you store unique values of any type, whether primitive values or object references. Its like an array but it stores data of different types aswell.

### Set methods
|Method|What does it do|
|---|---|
|.set(value)|Inserts the key value pair into the map object|
|.has(value)|Checks if the map object contains that key, will output true/false|
|.delete(value)|deletes the key value pair associated with that key|
|.size|Returns the current size of the map ie how many key value pairs there are|

### Example

```js
const mySet = new Set();
mySet.add(1);
mySet.add("some text");
mySet.add("foo");

mySet.has(1); // true
mySet.delete("foo");
mySet.size; // 2

for (const item of mySet) {
  console.log(item);
}
// 1
// "some text"

```
### Converting from set to array

To convert, use the `Array.from()` method.


