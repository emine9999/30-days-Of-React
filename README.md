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
# Template Literals in JavaScript

Template literals are a powerful feature introduced in ES6 (ECMAScript 2015) that allows for easier string manipulation. They provide a way to embed expressions, create multi-line strings, and use string interpolation without the need for cumbersome string concatenation.

## Key Features of Template Literals

1. **String Interpolation**:
   - Template literals enable embedding variables and expressions directly within the string using the `${expression}` syntax.
   - This makes it easier to create dynamic strings without having to use the `+` operator for concatenation.

   **Example**:
   ```javascript
   const name = 'Alice';
   const age = 30;
   const greeting = `Hello, my name is ${name} and I am ${age} years old.`;
   console.log(greeting);
   // Output: Hello, my name is Alice and I am 30 years old.
    ```
**Multi-line Strings:**

Unlike regular strings, which require \n to create new lines, template literals can span multiple lines easily.
This is particularly useful for formatting strings that require line breaks.

```javascript
const message = `This is a multi-line string.
It allows for easy formatting.
You can write across multiple lines without any special characters.`;
console.log(message);
```
**Expression Evaluation:**

You can include any valid JavaScript expression inside the ${} braces. This can include arithmetic operations, function calls, and more.

```javascript
const x = 5;
const y = 10;
const sumMessage = `The sum of ${x} and ${y} is ${x + y}.`;
console.log(sumMessage);
// Output: The sum of 5 and 10 is 15.
```
# Default Parameters in JavaScript

Default parameters are a feature introduced in ES6 (ECMAScript 2015) that allow functions to have default values for their parameters. This means that if no value or `undefined` is passed for a parameter, the function will use the specified default value instead.

## Key Features of Default Parameters

1. **Setting Default Values**:
   - You can define default values for parameters by assigning them in the function definition.
   - If an argument is not provided or is explicitly set to `undefined`, the default value will be used.

   **Example**:
   ```javascript
   function greet(name = 'Guest') {
       console.log(`Hello, ${name}!`);
   }

   greet(); // Output: Hello, Guest!
   greet('Alice'); // Output: Hello, Alice!
   ```
# Spread and Rest Operators in JavaScript

The Spread and Rest Operators are powerful features introduced in ES6 (ECMAScript 2015) that simplify working with arrays and objects. They use the same syntax (`...`) but serve different purposes depending on the context.

## Spread Operator

The Spread Operator allows an iterable (like an array or object) to be expanded into its elements. This is particularly useful for combining arrays, passing elements to functions, or creating copies of arrays or objects.

### Key Features of the Spread Operator

1. **Combining Arrays**:
   - You can combine multiple arrays into one.

   **Example**:
   ```javascript
   const array1 = [1, 2, 3];
   const array2 = [4, 5, 6];
   const combined = [...array1, ...array2];
   console.log(combined); // Output: [1, 2, 3, 4, 5, 6]
   ```
**Copying Arrays:**

You can create a shallow copy of an array.
```javascript
const original = [1, 2, 3];
const copy = [...original];
console.log(copy); // Output: [1, 2, 3]
```
**Spreading in Function Calls:**

You can use the spread operator to pass elements of an array as individual arguments to a function.

```javascript
function sum(a, b, c) {
    return a + b + c;
}

const numbers = [1, 2, 3];
console.log(sum(...numbers)); // Output: 6
```
**Combining Objects:**

You can also merge objects using the spread operator.

```javascript
const obj1 = { name: 'Alice' };
const obj2 = { age: 25 };
const combinedObj = { ...obj1, ...obj2 };
console.log(combinedObj); // Output: { name: 'Alice', age: 25 }
```
**Rest Operator**
The Rest Operator allows you to represent an indefinite number of arguments as an array. It is used in function parameter lists to gather arguments into a single array.
**Key Features of the Rest Operator**
**Function Parameters:**

You can use the rest operator to handle multiple function arguments easily.

```javascript
function multiply(...args) {
    return args.reduce((product, current) => product * current, 1);
}

console.log(multiply(2, 3, 4)); // Output: 24 (2 * 3 * 4)
```
**Destructuring with Rest:**

You can use the rest operator to destructure objects or arrays and gather the remaining elements.
```javascript
const array = [1, 2, 3, 4, 5];
const [first, second, ...rest] = array;
console.log(first); // Output: 1
console.log(second); // Output: 2
console.log(rest); // Output: [3, 4, 5]
```
**Rest in Object Destructuring:**

You can also use the rest operator when destructuring objects.
```javascript
const person = { name: 'Bob', age: 30, city: 'New York' };
const { name, ...rest } = person;
console.log(name); // Output: Bob
console.log(rest); // Output: { age: 30, city: 'New York' }
```
# JavaScript Modules

JavaScript modules provide a way to split code across different files, allowing for better organization, maintainability, and reusability of code. By using the `import` and `export` statements, developers can define dependencies between different parts of an application.

## Key Features of Modules

1. **Encapsulation**: Each module has its own scope. Variables and functions defined in a module are not accessible outside of it unless explicitly exported.

2. **Reusability**: Modules can be reused across different parts of an application or even in different projects.

3. **Maintainability**: By organizing code into separate modules, it's easier to manage and understand large codebases.

## Exporting Modules

To make variables, functions, or classes available to other modules, you can use the `export` keyword.

### Example: Named Exports

```javascript
// math.js
export const pi = 3.14;

export function add(x, y) {
    return x + y;
}
```
**Importing Modules**
To use exported modules in another file, the import keyword is used.

```javascript
// main.js
import { pi, add } from './math.js';

console.log(pi); // Output: 3.14
console.log(add(2, 3)); // Output: 5
```
# JavaScript Promises

Promises are a powerful feature in JavaScript that allow for managing asynchronous operations in a cleaner and more manageable way. They represent a value that may be available now, or in the future, or never. Promises help prevent callback hell, making the code easier to read and maintain.

## Key States of a Promise

A Promise can be in one of three states:

1. **Pending**: The initial state; the operation has not yet completed.
2. **Fulfilled**: The operation completed successfully, and the promise has a resulting value.
3. **Rejected**: The operation failed, and the promise has a reason for the failure (usually an error).

## Creating a Promise

You can create a Promise using the `Promise` constructor, which takes a function with two parameters: `resolve` and `reject`.

### Example:

```javascript
const myPromise = new Promise((resolve, reject) => {
    const success = true; // Simulating success or failure
    if (success) {
        resolve('Operation was successful!');
    } else {
        reject('Operation failed.');
    }
});
```
**Consuming a Promise**
You can handle the outcome of a Promise using the .then() method for fulfilled promises and .catch() for rejected promises.

```javascript
myPromise
    .then(result => {
        console.log(result); // Output: Operation was successful!
    })
    .catch(error => {
        console.error(error);
    });
```
**3. Promise.all()**
The Promise.all() method takes an iterable of Promises and returns a single Promise that resolves when all of the Promises in the iterable have resolved or when the iterable contains no Promises. It rejects with the reason of the first Promise that rejects.

```javascript
const promise1 = Promise.resolve(1);
const promise2 = Promise.resolve(2);
const promise3 = Promise.resolve(3);

Promise.all([promise1, promise2, promise3]).then(values => {
    console.log(values); // Output: [1, 2, 3]
});
```
**. Promise.race()**
The Promise.race() method takes an iterable of Promises and returns a Promise that resolves or rejects as soon as one of the Promises in the iterable resolves or rejects, with its value or reason.
```javascript
const promise1 = new Promise((resolve) => setTimeout(resolve, 100, 'One'));
const promise2 = new Promise((resolve) => setTimeout(resolve, 200, 'Two'));

Promise.race([promise1, promise2]).then(value => {
    console.log(value); // Output: One (the first promise to resolve)
});
```
**. Promise.reject()**
The Promise.reject() method returns a Promise that is rejected with a given reason (error). This is useful for returning a rejected Promise in a function that returns a Promise.
```javascript
const rejectedPromise = Promise.reject(new Error('Something went wrong.'));
rejectedPromise.catch(error => {
    console.error(error.message); // Output: Something went wrong.
});

```

