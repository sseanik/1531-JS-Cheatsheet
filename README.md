
# 1531 Cheatsheet

# JavaScript

## Data Types
```javascript
// Strings (can use ' or " or `)
const character = 'a';
const name =  'Sean';
const phrase  = "Hello World";
const sentence = `Hey ${word}, welcome to my ${phrase} program`;

// Numbers
const integer = 69;
const pi = 3.14159265;
const negative = -420;
const inf = infinity;

// Arrays
const emptyArray = [];
const letters = ['a', 'b', 'c', 'd'];
const objects = [{letter: 'a'}, {letter: 'b'}, {letter: 'c'}]
const mixed = [1, 'a', [1,2,3]]
const nums = [1, 2, 3, 4];

nums[0] = 1.5; // nums becomes [1.5, 2, 3, 4]

// Objects
const emptyObject = {};
const person = {
  name: "Sean",
  age: 69,
  isTutor: true
};

// Nested Objects
const person = {
  name: "Sean",
  age: 69,
  work: {
     university: "UNSW",
     course: "COMP",
     courseNum: 1531,
     role: "Tutor"
   }
};

// Reading specific values from an object (name and age are keys)
console.log(person.name); // Output: Sean
console.log(person['age']);  // Output: 69

// Modifying an object
person.email = 'sean@gmail.com'; // Adding a new property 
// person becomes { name: 'Sean', age: 69, title: 'Tutor', email: 'sean@gmail.com' }

person.age = 420; // Modifying an existing property
// person becomes { name: 'Sean', age: 420, title: 'Tutor', email: 'sean@gmail.com' }

delete person.title; // Removes a key and value, 
// person becomes { name: 'Sean', age: 420, email: 'sean@gmail.com' }
```

## Printing
```javascript
const name = "Sean";
const age = 69;
// Template Literal
console.log(`Name: ${name}, Age: ${age}`); // Output: Name: Sean, Age: 69 (with a new line)
// String concatenation
console.log("Name: " + name + ", Age: " + age); // Output: Name: Sean, Age: 69 (with a new line)
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
person.age = 420; // Allowed, person will become { name: 'Sean', age: 420 }
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

## Recommended Array Looping
```javascript
const nums = [10, 9, 8, 7, 6];

// For..of Loop - Gives you the array element on each iteration (i.e. 10, 9, 8, 7, 6)
for (const num of nums) {
    console.log(num);
}

// For..in Loop - Gives you the index on each iteration (i.e. 0, 1, 2, 3, 4)
for (const i in array) {
    console.log(nums[i]);
}

// Built-in prototype method for array
nums.forEach((num) => {
    console.log(num);
});
```

## Array Methods

**Checking & Finding**
```javascript
const numbers = [1, 2, 3, 4, 5]; 

// .some - Check if one element of the array statisfies a condition
const hasNegative = numbers.some(num => num < 0); // False

// Equivalent Longer way:
let hasNegative = false;
for (const num of numbers) {
  if (num < 0) {
	hasNegative = true;
	break;
  }
}

// .every - Check if every element of the array satisfies a condition
const allPositive = numbers.every(num => num > 0); // True

// Equivalent Longer way:
let allPositive = false;
for (const num of numbers) {
  if (num > 0) {
	allPositive = true;
  } else {
	allPositive = false;
	break;
  }
}

// .includes - Check if the array contains an element
const hasThree = numbers.includes(3); // True

// Equivalent Longer way:
let hasThree = false;
for (const num of numbers) {
  if (num === 3) {
	hasThree = true;
	break;
  }
}

// .find - Returns the first element that satisfies a condition
const firstEven = numbers.find(num => num % 2 === 0); // Output: 2

// Equivalent Longer way:
let firstEven = undefined;  
for (const num of numbers) {
  if (num % 2 === 0) { 
    firstEven = num;
    break;  
  }
}

const notPresent = numbers.find(num => num === 69); // Output: undefined
```

**Filter, Map, Reduce**
```javascript
const numbers = [1, 2, 3, 4, 5]; 

// .filter - Creates a new array based on elements that pass a condition
const evenNumbers = numbers.filter(num => num % 2 === 0); // Output: [2, 4]

// Equivalent Longer way:
const evenNumbers = [];
for (const num of numbers) {
  if (num % 2 === 0) {
	evenNumbers.push(num);
  }
}

// .map - Creates a new array based on transforming each of the array elements
const doubled = numbers.map(num => num * 2); // Output: [2, 4, 6, 8, 10]

// Equivalent Longer way:
const doubled = [];
for (const num of numbers) {
  doubled.push(num * 2);
}

// .reduce - Executes a function on each element of the array, resulting in a singular output
const sum = numbers.reduce((prev, curr) => prev + curr, 0); // Output: 15

// Equivalent Longer way:
let sum = 0;
for (const num of numbers) {
  sum += num;
}
```
**Adding n elements to start or end of an Array**
```javascript
const numbers = [4, 5, 6];

// .push - Adds n number of elements to the END of an array
const newLength = numbers.push(7); // Output: 4 - returns new length of the array
numbers.push(8, 9, 10) // Output: 7, numbers is now [4,5,6,7,8,9,10]

// .unshift - Adds n number of elements to the START of an array
const newLength = numbers.unshift (3); // Output: 8 - returns new length of the array
numbers.unshift (1, 2) // Output: 10, numbers is now [1,2,3,4,5,6,7,8,9,10]
```
**Removing one element from start or end of an Array**
```javascript
const numbers = [1, 2, 3, 4, 5]

// .pop - Removes the last element from the array and returns that element
const lastElement = numbers.pop(); // Output: 5, numbers is now [1,2,3,4]

const emptyArray = [];
emptyArray.pop(); // Output: undefined

// .shift - Removes the first element from the array and returns that element
const firstElement = numbers.shift(); // Output: 1, numbers is now [2, 3, 4]

emptyArray.shift(); // Output: undefined
```
**Splice (Removing, Inserting or Replacing)**
```javascript
// First arg is start index (required and can be negative to index from the end)
// Second arg is delete count
// Rest of the args are n elements to add to the array
```
Removing Element(s)
```javascript
// Remove n elements from given array index to the end (inclusive)
const nums = [1, 2, 3, 4, 5];
// Remove every element from index 3 to the end
nums.splice(3) // Output: [4,5], nums becomes [1,2,3]

// Remove supplied n delete count of elements from the given index
const letters = ['a', 'b', 'c', 'd', 'e'];
// Remove 2 elements from index 1
letters.splice(1, 2); // Output: ['b', 'c'], letters becomes ['a', 'd', 'e']

// You can use a negative index to index from the end of the array
const array = [1, 2, 3, 4, 5];
// Remove 2 elements starting from index -3 (3rd from the end) 
array.splice(-3, 2); // Output: [3, 4], array becomes [1, 2, 5]
```
Inserting Element(s)
```javascript
// When delete count is provided as 0
const array = [1, 2, 3, 4, 5];
// Add 'a' and 'b' at index 2
array.splice(2, 0, 'a', 'b'); // Output: [], array becomes [1, 2, 'a', 'b', 3, 4, 5]
```
Replacing Element(s)
```javascript
// When delete count is provided as greater than 0
const array = [1, 2, 3, 4, 5];
// Replace 3 elements at index 2
array.splice(2, 3, 'a', 'b', 'c'); // Output: [3, 4, 5], array becomes [1, 2, 'a', 'b', 'c']
```
**Creating a Subarray from an Array**
```javascript
const numbers = [1, 2, 3, 4, 5];
// .slice - Returns a shallow copy portion of an array from start to end index (end not included)
const sliced = numbers.slice(1, 3); // Output: [2, 3], numbers array unchanged
```
**Reversing an array**
```javascript
const numbers = [1, 2, 3, 4, 5];
// .reverse - Reverses an array inplace
numbers.reverse(); // Returns reference to same array - [5, 4, 3, 2, 1]
```

## Object Methods
```javascript
// .entries - Returns an array of objects [key, value] pairs
const obj = { a: 1, b: 2, c: 3 }; 
const entries = Object.entries(obj); // entries: [['a', 1], ['b', 2], ['c', 3]]

// .keys - Returns an array of the object property keys (left hand side)
const keys = Object.keys(obj); // keys: ['a', 'b', 'c']

// .values - Returns an array of the object property (right hand side) values
const values = Object.values(obj); // values: [1, 2, 3]

// Check if a key is in the object
if ('b' in obj) { // true
  //
} else if ('d' in obj) { // false
  //
}
```

## Object Looping
```javascript
const obj = { a: 1, b: 2, c: 3 }; 

// Goal Output: 
// a: 1 
// b: 2 
// c: 3

for (const key in obj) { 
  if (obj.hasOwnProperty(key)) { 
    console.log(`${key}: ${obj[key]}`); 
  }
}

Object.keys(obj).forEach(key => { 
  console.log(`${key}: ${obj[key]}`); 
});

Object.entries(obj).forEach(([key, value]) => { 
  console.log(`${key}: ${value}`); 
});

for (const [key, value] of Object.entries(obj)) { 
  console.log(`${key}: ${value}`); 
}
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

## Importing & Exporting
```javascript

```

## Packages
```javascript

```

## Spread Operator
```javascript

```

## Sorting
```javascript

```

## String Manipulation
```javascript

```

## Persistance
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

## HTTP Tests
```javascript

```

## HTTP Error Checking
```javascript

```

## Exceptions
```javascript

```

# Good Practice & Style
## Object Shorthand
```javascript

```

## Constant/Magic Variables
```javascript

```

## Casing
```javascript

```

## If Else Returns
```javascript

```

## JSDoc
```javascript

```

# Git
