# 30 Days of React

Welcome to my **30 Days of React** repository! This project documents my journey of learning React over the course of 30 days. Each day, I tackle a new concept, build small projects, and deepen my understanding of this powerful JavaScript library.

## Table of Contents

1. [About](#about)
2. [Daily Breakdown](#daily-breakdown)
3. [Getting Started](#getting-started)
4. [Technologies Used](#technologies-used)
5. [Contributing](#contributing)
6. [License](#license)

## About

This repository serves as a personal log of my learning process and contains various projects that showcase my understanding of React concepts. Each day's work includes notes, code snippets, and reflections on what I've learned.

## Daily Breakdown

| Day | Topic                       | Description                               |
|-----|-----------------------------|-------------------------------------------|
| 1   | ES6+ features               |Arrow Functions,Destructuring,Template Literals,Default Parameters,Spread and Rest Operators,Modules,Promises, |
| 2   | DOM & file structure & best practices       | Understanding what is the DOM and how to structure your project|
| 3   | State Management            | Managing state in React components.      |
| 4   | Lifecycle Methods           | Exploring component lifecycle methods.    |
| 5   | Hooks                       | Introduction to hooks, including useState and useEffect. |
| ... | ...                         | ...                                       |
| 30  | Final Project               | Building a complete application using learned concepts. |

## Getting Started
## Day 1
# Understanding JavaScript Arrow Functions

In modern JavaScript, arrow functions provide a concise and flexible way to define functions. Introduced in ES6 (ECMAScript 2015), arrow functions are a more readable alternative to traditional function expressions, particularly in scenarios involving callbacks and functional programming.

## 1. Syntax Simplicity

The key attraction of arrow functions is their concise syntax. Instead of writing a full function declaration, you can quickly define a function with minimal syntax. Here's an example comparing traditional and arrow functions:

**Traditional Function:**
```javascript
function add(a, b) {
  return a + b;
}
```
**Arrow Function**
```
const add = (a, b) => a + b;
```
As seen, the arrow function eliminates the need for the function keyword, curly braces for single-line expressions, and even the return statement (for single expressions).
**2. Implicit Return**
Arrow functions implicitly return the result of the expression if it's written in a single line, which reduces boilerplate code:
```javascript
const square = x => x * x;
```
This function will return the square of the input x without the need for an explicit return statement.
**3. Handling Parameters**
Arrow functions can handle zero, one, or multiple parameters. For no parameters, empty parentheses are used, while single parameters don’t require parentheses:

No parameters: () => "Hello!"
One parameter: x => x * 2
Multiple parameters: (a, b) => a + b

# Destructuring in JavaScript

**Destructuring** in JavaScript is a syntax feature introduced in ES6 that allows you to extract values from arrays or properties from objects and assign them to variables in a more concise and readable way. It simplifies how data can be unpacked from structures, making your code easier to understand and maintain.

## 1. Array Destructuring

Array destructuring allows you to assign values from an array to variables in a single statement.

### Example:
```javascript
const numbers = [1, 2, 3];

// Destructuring assignment
const [first, second, third] = numbers;

console.log(first);  // Output: 1
console.log(second); // Output: 2
console.log(third);  // Output: 3
```
You can also skip elements by leaving spaces in the destructuring pattern:

```javascript
const numbers = [1, 2, 3, 4];

// Skip the second element
const [first, , third] = numbers;

console.log(first);  // Output: 1
console.log(third);  // Output: 3
```
**2. Object Destructuring**
Object destructuring lets you extract properties from an object into variables, using property names as the variable names.

```javascript
const person = {
  name: 'Amine',
  age: 25,
  city: 'Marrakech'
};

// Destructuring assignment
const { name, age, city } = person;

console.log(name);  // Output: Amine
console.log(age);   // Output: 25
console.log(city);  // Output: Marrakech
```
If the variable names need to be different from the property names, you can assign them like this:
```javascript
const person = { name: 'Amine', age: 25 };

const { name: fullName, age: yearsOld } = person;

console.log(fullName); // Output: Amine
console.log(yearsOld); // Output: 25
```
**3. Default Values**
Destructuring allows you to set default values for variables in case the property or array element is undefined:

```javascript
const { name = 'Guest', age = 18 } = { name: 'Amine' };

console.log(name); // Output: Amine
console.log(age);  // Output: 18 (default value)
```
**4. Nested Destructuring**
You can destructure nested objects or arrays as well.

```javascript
const numbers = [1, [2, 3], 4];

const [one, [two, three], four] = numbers;

console.log(two);  // Output: 2
console.log(three); // Output: 3
```
**5. Function Parameters Destructuring**
You can use destructuring in function parameters to extract values from an object or array passed to a function.

```javascript
function greet({ name, age }) {
  console.log(`Hello, my name is ${name} and I am ${age} years old.`);
}

const person = { name: 'Amine', age: 25 };
greet(person);  // Output: Hello, my name is Amine and I am 25 years old.
```

