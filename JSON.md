# Understanding JSON

## What does JSON mean and what is it/

JSON stands for "JavaScript Object Notation" and it is a text based format for representing structured data. For example say we had an object with properties such as

```js
const user = {
firstName: "Ivan",
lastname: "Flitcroft"

```
This object would then be represented in JSON like so
```JSON
{
firstName: "Ivan",
lastname: "Flitcroft"
}
```

## What is JSON used for 

JSON is commonly used for API's and other files.  It allows developers to store configuration settings in a human-readable and structured format.
It also allows users to customize settings and perferences as JSON can be represented as an array.

## How do we access data from JSON

You would simply just use dot/bracket notation. For example if we loaded the JSON script above and parsed it into an Object called `user`, we could then do `user.firstName` to output the first name of the user.

However, if you had an object inside another object like the below example and it was in JSON and we loaded it in a parsed it into the `shop` object

```js
const shop = {
location: "England",
employees: [{
name: "Ivan",
age: 18
},
{
name: "Ben",
age: 34
}]

```

Then to access the deeper elements of Employees we would have to chain the required property names and array indexes together for example

```js
shop["employees"][1][age]
//outputs 34
```
