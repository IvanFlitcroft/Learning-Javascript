# Understanding data types in Javascript
When instantiating a variable, we can use 'let', 'var' or 'const' and each have their own differences
## Let
```javascript
function letTest() {
 let x = 1;

  if (true) {
       console.log(x); // will print 1
  }

 console.log(x); // will print 1

}
```

```javascript
function letTest() {
  let x = 1;

  if (true) {
    let x = 2;
    console.log(x); // will print 2
  }

  console.log(x); // will print 1
}
```

When we use 'let', the variable only exists in the block in which it is instantiated, no other blocks inside or outside. This is why letTest() will output two different values of 'x' as we have one instance of x declared at the start of the function and another one declared in a block inside the main function block.

## Var
```javascript
function varTest() {
  var x = 1;

  if (true) {
    var x = 2;
    console.log(x); // will print 2
  }

  console.log(x); // will print 2
}

```
When we use 'var', the variable exists throughout the function, in every block inside or outside. The variable could be declared inside a deeply nested block and it will still exist within the whole function. In this example, we initially declare the variable 'x' with an integer value of 1, however, by declaring another variable with the same name, we override the value of the varaiable with the name hence 2 is outputted twice.


Lets take a look at this example. We have a function in which we instantiate two variables: 'functionVariable' and 'blockVariable'. In this test we show how the values can be accessed within the function and within nested blocks in the function itself. However if we try to print out the variables outside of the function, only 'functionVariable' can be printed, which is not something we would usually expect, right? Lets discuss why this occurs.

```javascript
function nestedLetVarTest() {
  if (true) {
    var functionVariable = 1;
    let blockVariable = 2;

    console.log(functionVariable); // will print 1
    console.log(blockVariable); // will print 2

    if (true) {
      console.log(functionVariable); // will print 1
      console.log(blockVariable); // will print 2
    }
  }

  console.log(functionVariable); // will print 1
  console.log(blockVariable); // will throw an error
}
```
## Why does this happen? JS hoisting

This occurs due to Javascript hoisting. This is a process whereby the interpreter appears to move the declaration of functions, variables, classes, or imports to the top of their scope, before the execution of the code.
So in the case above, the var declaration of functionVariable is hoisted to the top level of nestedLetVarTest() before execution, but the let declaration of blockVariable is not. This means the variable defined by var can be accessed outside of the function whereas let cannot as the let variable was defined inside the function block.

## Summary of let vs var

The main differences between let and var are:
- variables declared with `let` exist within its own block, hence multiple instances of the same variable can be declared with different values in different blocks and it will not affect the other values. Theyre essentially independant
- variables declared with `var` exist within the whole function, hence declaring another instance of the same variable will override its initial value. There is only one variable of that name
