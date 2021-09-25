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

### var
pending
### let
pending
### const
pending

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

7. **Objects** -
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
