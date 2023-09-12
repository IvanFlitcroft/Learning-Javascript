# Understanding Object Prototypes and prototypal inheritance 

## What is a prototype?

For a given object `o`, the object from which `o` inherits properties is called the prototype of `o`. So in an OOP way, the father 'class' is called the prototype
An object inherits data from its prototype hence if we look at the example below and assume that the dad object is the prototype of son then this will occur.
```js
let dad = {age: 40};
let son = {glasses: true};

console.log(son.age) //output 40 IF we assume dad is the prototype of son
```
## how does an object know if it inherits of the other?

In javascript, each object has a built in prototype attribute `[[Prototype]]` which holds a reference to the prototype (parent) of that object

So, now that we know this we can correctly write the code example,

```js
let dad = {age: 40};
let son = {
glasses: true,
[[Prototype]]: dad
};

console.log(son.age) //output 40
```
In addition, if we are going to create an object using the `.create` method then we would follow this structure

```js
Object.create(prototype[, properties])

```
