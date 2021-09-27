# Tech Interview Guide

## Variables
Variables are used to store different types of data.

- variable names can't start with a number, they only accept the symbols `$` and `_`
- good practice means to start files with 'use strict' so implicit variables aren't created
- camelCase is vital, `let nAME is different than let naME`
- reserved names **CAN'T** be used as variable names `function, return, class, etc`

We can declare variables to store data by using the `var`, `let`, or `const` keywords.

- `var` – is an old-school variable declaration. Normally we don’t use it at all
- `let` – is a modern variable declaration.
- `const` – is like let, but the value of the variable can’t be changed.

### Local Variables
A variable declared inside a function is only visible inside that function
```
function alertName() {
  let name = 'Juan'
  alert(name);
}

alertName() // Juan
```

### Global Variables
Variables declared in the global scope can be accessed from any inner scope

It's good practice to minimize global variable declarations
```
let name = 'Juan'

function alertName() {
  alert(name);
}

alertName() // Juan
```

### var
var declarations are globally scoped or function/locally scoped.
var variables can also be redeclared
```
var hi = 'hi';
var hi = 'hello';
```
### let
let is block scoped, variables declared with let are only visible inside the scope they are defined in {}.
let can be updated but not redeclares

### const
const variables are block scoped, const cannot be updated or redeclared.
const objects are different, the properties or values inside a const object **CAN** be updated
```
const obj = {};
obj.name = 'Juan';
obj
//{name: 'Juan'}
```


## Data Types
There are 8 basic data types for variables in javascript with the first 5 being primitive types.

### Primitive data types
Primitive data types are those that can only store one single value

1. **Number** - Represents both integer and floating numbers
2. **BigInt** - Is for integer numbers of arbitrary length. It's created by appending n to the end of an integer: `const bigInt = 1234567890123456789012345678901234567890n;`
3. **String** - Represents letters, words and sentences, they have to be enclosed by `'single quotes'`, `"double quotes"` or `` `back ticks` ``
4. **Boolean** - Logical value, true or false
5. **null** - It represents an empty value let name = null
6. **undefined** - It represents when a value has not been assigned to a variable `let name`

### Non-Primitive data types

7. **Objects** - Store keyed collections of data
8. **Symbols** - 

### typeof
the typeof operator allows us to identify the type of value being assigned `typeof x //Returns value type, if its null it returns "object"`

## Type Conversion
Different ways to convert values to other types of data

### Convert to String
`String(value)` - function to convert a value to a string:

### Convert to Number
`Number(value)` - function to convert a value to a number:
if value is not a string of numbers, the result will be NaN, (not a number)
- null becomes 0
- undefined becomes NaN

### Convert to Boolean
`Boolean(value)` function to convert a value to a boolean
- Values that are intuitively “empty”, like 0, an empty string, null, undefined, and NaN, become false.
- Other values become true.

## Comparison
### ALL COMPARISON OPERATORS RETURN BOOLEAN VALUE
```
<, <=, <==, >, >=, >==, ==, ===, !=, !==
```
### A strict equality operator `===` checks the equality without type conversion.
```
1 == '1' // true
1 === '1' // false
```

## Loops while and for
Loops are used to repeat the same code multiple times

### While Loop
```
while (condition) {
  // code
  // so-called "loop body"
}
```
While the condition is truthy, the code will always be executed, in case of infinite iterations, loops can be killed from browser or server side

### Do While Loop
```
do {
  // loop body
} while (condition);
```
This loop is used when you want the code to be executed **at least once**

### For Loop
```
for (begin; condition; step) {
  // ... loop body ...
}
```

for loops can be exited when the condition is no longer truthy, but it can also be broken with a `break` or `return`
the `return` will break the loop after the 1 iteration

## Functions
They are the main  building blocks, they allow for code to be called many times without repetition.
- Functions are values. They can be assigned, copied or declared in any place of the code.
- Function Declarations are processed before the code block is executed. They are visible everywhere in the block.
- Function Expressions are created when the execution flow reaches them.

### Function Declaration
```
function functionName() {
  //function body
}
```

### Function Call
functionName();

### Function Parameters
We can call pass data to a function by using parameters
```
function sayHello(name){
  alert(`Hello ${name}`);
}

sayHello('Juan'); // Hello Juan
```

### Returning a value
- Functions can return a value back into the calling code
- A function that doesn't return a value is the same as if it returns undefined
- lines added after the return statement are ignored
- Functions should only do one action at a time (good practices)

```
function sum(a, b) {
  return a + b;
}

let result = sum(1, 2);
alert( result ); // 3
```

### Function Expressions
A function expression is when a function is assigned to a variable, it still needs () to be called
```
function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```

### Callback functions
These are functions that are sent as a parameter to a function

```
function ask(question, yes){
  if(confirm(question)){
    yes();
  }
}

function showOk(){
  alert('you confirmed');
}

ask('Do you agree?', showOk)
```

### Arrow Functions
This is a more simple and organized way to write functions
```
const func = (param1, param2) => {
//code body
return value;
}

if there is one param, the parenthesis can be ommitted
const func = param => {}

if the only line inside the code body is a return then the curly braces adn return can be ommitted
const func = param => value
```

## Unit Testing
Tests are necessary to validate that your code is doing what it's meant to do, they are created in spec files
In BDD, the spec goes first, followed by implementation. At the end we have both the spec and the code.

The spec can be used in three ways:
- As Tests – they guarantee that the code works correctly
- As Docs – the titles of describe and it tell what the function does
- As Examples – the tests are actually working examples showing how a function can be used

With the spec, we can safely improve, change, even rewrite the function from scratch and make sure it still works right.

## Polyfill and Transpilers

### Polyfills
Transform modern functions into vanilla functions that can be interpreted by previous versions of javascript

### Transpilers
Translates code to another source code. It can parse (read and understand) modern code and rewrite it with older syntax so it works in outdated engines.
Usually, a transpiler runs on your own computer and then deploys the transpiled code to the server (Babel)
Webpack runs the transpiler on every code change

## Objects
- Objects are associative arrays with several special features.
- 
An object can be created with figure brackets `{…}` with an optional list of properties. A property is a “key: value” pair, where key is a string (also called a “property name”), and value can be anything.

```
let user = {};
let user = new Object();
```

Property values are accessible with dot notation and can be removed with the `delete` keyword. they have to be exact. Square brackets identifiers works with any string and can obtain a property name as the result of an expression
```
alert(user.name);
delete user.name;

let key = "likes birds";

// same as user["likes birds"] = true;
user[key] = true;
```

### "in" keyword
Used to test if a **key** value exists inside an object
```
let user = { name: "John", age: 30 };

alert( "age" in user ); // true, user.age exists
alert( "blabla" in user ); // false, user.blabla doesn't exist
```

## for...in loop
Used to loop through the keys of an object
```
for (key in object) {
  // executes the body for each key among object properties
}

let user = {
  name: "John",
  age: 30,
  isAdmin: true
};

for (let key in user) {
  // keys
  alert( key );  // name, age, isAdmin
  // values for the keys
  alert( user[key] ); // John, 30, true
}
```

## Object Reference and copying
One of the fundamental differences of objects versus primitives is that objects are stored and copied “by reference”, whereas primitive values: strings, numbers, booleans, etc – are always copied “as a whole value”.

Two objects are the same if they reference the same object
```
let a = {};
let b = a; // copy the reference

alert( a == b ); // true, both variables reference the same object
alert( a === b ); // true
```

Two independent objects will always be different
```
let a = {};
let b = {}; // two independent objects

alert( a == b ); // false
```

### Cloning Objects
```
let user = {
  name: "John",
  age: 30
};

let clone = {}; // the new empty object

// let's copy all user properties into it
for (let key in user) {
  clone[key] = user[key];
}

// now clone is a fully independent object with the same content
clone.name = "Pete"; // changed the data in it

alert( user.name ); // still John in the original object
```

### this (context)
`this` is defined depending on the context for where it is being called. It references the scope it is inside
```
let user = {
  name: "John",
  age: 30,

  sayHi() {
    // "this" is the "current object"
    alert(this.name);
  }

};

user.sayHi(); // John
```

Arrow functions have no `this`. It's taken from outside
