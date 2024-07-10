
# 1531_Guide

# JavaScript

## Printing
```javascript
const name = "Sean";
const age = 69;
console.log(`Name: ${name}, Age: ${age}`); // Template Literal
console.log("Name: " + name + ", Age: " + age); // String concatenation
// Will result in "Name: Sean, Age: 69" (with a new line)
```

## Data Types
```javascript

```

## Const
```javascript
const pi = 3.14159;
// NOT ALLOWED
pi = 3.14; // Uncaught TypeError: Assignment to constant variable.
```
```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.push(6); // Allowed, numbers will become [1, 2, 3, 4, 5, 6]
// NOT ALLOWED
numbers = [7, 8, 9]; // Uncaught TypeError: Assignment to constant variable.
```
```javascript
const person = {
  name: 'Sean',
  age: 69
};
person.age = 420; // Allowed
// NOT ALLOWED
person = { name: 'Hayden', age: 69420 }; // Uncaught TypeError: Assignment to constant variable.
```

## Let
```javascript
let count = 10;
count = 20; // Allowed
```
```javascript
let x = 10;
if (x > 5) {
    let y = 20; // Let variables are only accessible in the block they are defined
}
// NOT ALLOWED
console.log(y); // Uncaught ReferenceError: y is not defined
```

## Array Looping C-Style
```javascript
const nums = [10, 9, 8, 7, 6];

for (let i = 0; i < nums.length; i++) {
    console.log(nums[i]);
}

let i = 0;
while (i < nums.length) {
    console.log(nums[i]);
    i++;
}
```

## Array Looping Recommended
```javascript
const nums = [10, 9, 8, 7, 6];

// For..of Loop - Gives you the array value on each iteration (i.e. 10, 9, 8, 7, 6)
for (const num of nums) {
    console.log(num);
}

// For..in Loop - Gives you the iterable variable on each iteration (i.e. 0, 1, 2, 3, 4)
for (const i in array) {
    console.log(nums[i]);
}

// Built-in prototype method for array
nums.forEach((num) => {
    console.log(num);
});
```

## Objects
```javascript
const person = {
  name: 'Sean',
  age: 69,
  title: 'Tutor'
};

console.log(person.sean); // Output: Sean
console.log(person.age);  // Output: 69

person.email = 'sean@gmail.com'; // Adding a new property
person.age = 420; // Modifying an existing property

delete person.title; // Removes a property and value
```

## Nested Objects
```javascript
const person = {
  name: 'Sean',
  age: 69,
  title: 'Tutor'
};
```

## Object Methods
```javascript

```

## Object Looping
```javascript

```

## Equality Checks
```javascript

```

## If, Else if, Else
```javascript

```

## Ternary Statements
```javascript

```

## Functions
```javascript

```

## Array Methods
```javascript
// 
```

## Importing & Exporting
```javascript

```

## Packages
```javascript

```

## Spread Operator
```javascript

```

# Testing
## General Structure
```javascript

```
## test.each
```javascript

```
## expect.any
```javascript

```

## HTTP Tests
```javascript

```

## HTTP Error Checking
```javascript

```

# TypeScript
## Parameter and Return Types
```javascript

```
## Interfaces
```javascript

```
## Types
```javascript

```

# Backend API
## Express Server Skeleton
```javascript

```
## HTTP Methods & Routes
```javascript

```
## Status Codes & Errors
```javascript

```

# Good Practice & Style
## Constant/Magic Variables
```javascript

```

## Casing
```javascript

```

# Git
