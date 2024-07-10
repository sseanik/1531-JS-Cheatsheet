# 1531_Guide

Printing
```javascript
const name = "Sean";
const age = 69;
console.log(`Name: ${name}, Age: ${age}`); // Template Literal
console.log("Name: " + name + ", Age: " + age); // String concatenation
```

Const & Let
```javascript
const pi = 3.14159;
// NOT ALLOWED
pi = 3.14; // Uncaught TypeError: Assignment to constant variable.
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
```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.push(6); // Allowed
// NOT ALLOWED
numbers = [7, 8, 9]; // Uncaught TypeError: Assignment to constant variable.
```
