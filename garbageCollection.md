# Understanding garbage collection


## What is garbage collection

There is a built in process in the JS engine called a garbage collection and it will monitor all primitives and objects created and will remove the ones that have become unreachable in order to save memory.

For example, If we create a user object and store a string property of name but then make the user null. The name primitive becomes unreachable as the object is now null so the garbage collector will junk the data and free memory

```js
let user = {
name ="Ivan"  
};

user = null;
// user.name is no longer accessible so it will be junked
```
However, if we link another object to the user object beforehand, then the property will not be junked as it still needs to be accessed so all references will need to be deleted aswell

```js
let user = {
name ="Ivan"  
};
let admin = user;

user = null;
//the object is still reachable via admin global variable, so it must stay in memory. If we overwrite admin too, then it can be removed.
```

## How does the garbage collection work?

The process follows an algorithm called "mark-and-sweep"
It works by:
- Taking roots and "marks" them
- visits and "marks" all references from them
- visits marked objects and their references
- visits until every reachable references are visited
- all objects except marked ones are removed
