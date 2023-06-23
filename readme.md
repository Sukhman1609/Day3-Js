# Day-3 Interview Questions

## What are promises and why do we need them?
Promises are a way to handle asynchronous operations in JavaScript. In simpler terms, they allow you to handle code that may take some time to execute without blocking the rest of your code.

A Promise represents a value that may not be available yet, but will be at some point in the future. It is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

To create a Promise, you can use the Promise constructor. It takes a single argument, which is a function called the "executor". This function takes two parameters, resolve and reject, which are functions that are called when the Promise is resolved or rejected, respectively.

Here's an example of creating and using a Promise in JavaScript:

const myPromise = new Promise((resolve, reject) => {

  setTimeout(() => {

    const result = 42;

    resolve(result);

  }, 1000);

});


myPromise.then((result) => {

  console.log('The answer is ${result}');

}).catch((error) => {

  console.error('There was an error: ${error}');

});
<hr>

## What is promise chaining
Promise chaining is a way to use promises in JavaScript to execute a series of asynchronous operations in a specific order. It involves calling multiple promises in a sequence, where each promise depends on the result of the previous one.

Here's an example of promise chaining in JavaScript:

function stepOne() {

  return new Promise((resolve, reject) => {

    setTimeout(() => {

      resolve("Step One completed");

    }, 1000);

  });

}


function stepTwo(previousResult) {

  console.log(previousResult);

  return new Promise((resolve, reject) => {

    setTimeout(() => {

      resolve("Step Two completed");

    }, 2000);

  });

}


function stepThree(previousResult) {

  console.log(previousResult);

  return new Promise((resolve, reject) => {

    setTimeout(() => {

      resolve("Step Three completed");

    }, 3000);

  });

}


stepOne()

  .then((result) => stepTwo(result))

  .then((result) => stepThree(result))

  .then((result) => console.log(result))

  .catch((error) => console.error(error));
  <hr>

  ## What is the DOM?
  The DOM stands for Document Object Model, and it's a way for web developers to interact with and manipulate HTML and XML documents using JavaScript.

Here's a simple example code snippet that demonstrates how you can use JavaScript to access and modify the DOM:

```<!DOCTYPE html>
<html>
<head>
	<title>My Webpage</title>
</head>
<body>
	<h1>Welcome to my webpage!</h1>
	<p>Here's some text for you to read.</p>

	<script>
		// Select the first <p> element on the page
		var pElement = document.querySelector('p');

		// Change the text inside the <p> element
		pElement.textContent = 'This is new text!';

		// Create a new <button> element
		var buttonElement = document.createElement('button');

		// Add some text to the button
		buttonElement.textContent = 'Click me!';

		// Append the button to the end of the <body> element
		document.body.appendChild(buttonElement);
	</script>
</body>
</html>
```
<hr>

## What are closures? Give an example of closure
Closures are used in JavaScript to create private variables and methods, which are not accessible from outside the closure.

In simpler terms, when a function uses variables from outside of its own scope, those variables are "closed over" by the function and can still be accessed even after the function has finished executing.

```Here's an example to illustrate this concept:
function outerFunction() {
  const outerVariable = "Hello";

  function innerFunction() {
    const innerVariable = "World";
    console.log(outerVariable + " " + innerVariable);
  }

  return innerFunction;
}

const myFunction = outerFunction();
myFunction(); // Output: "Hello World"
```
<hr>

## How many operators do we have in JS ?
```
// Arithmetic operators
let a = 5;
let b = 10;
let c = a + b; // addition
let d = b - a; // subtraction
let e = a * b; // multiplication
let f = b / a; // division
let g = b % a; // modulus (remainder)

// Assignment operators
let x = 5;
x += 10; // equivalent to x = x + 10
x -= 5; // equivalent to x = x - 5
x *= 2; // equivalent to x = x * 2
x /= 3; // equivalent to x = x / 3
x %= 2; // equivalent to x = x % 2

// Comparison operators
let num1 = 10;
let num2 = 20;
let num3 = 10;
let isEqual = num1 == num2; // false
let isNotEqual = num1 != num2; // true
let isStrictEqual = num1 === num3; // true (checks both value and data type)
let isGreaterThan = num2 > num1; // true
let isLessThanOrEqual = num1 <= num3; // true

// Logical operators
let isTrue = true;
let isFalse = false;
let isAnd = isTrue && isFalse; // false
let isOr = isTrue || isFalse; // true
let isNot = !isTrue; // false

// Bitwise operators
let num4 = 5; // binary: 0101
let num5 = 10; // binary: 1010
let bitAnd = num4 & num5; // 0000 (AND)
let bitOr = num4 | num5; // 1111 (OR)
let bitXor = num4 ^ num5; // 1111 (XOR)
let bitNot = ~num4; // 1010 (NOT)
let bitLeftShift = num4 << 1; // 1010 (left shift)
let bitRightShift = num5 >> 1; // 0101 (right shift)
```
<hr>

## What are objects in javascript?

In JavaScript, objects are data structures that allow you to store and organize related data and functionality. They are created using the object literal notation or the Object constructor function.

```Here's an example of creating an object using the object literal notation:
const person = {
  name: 'Ajay',
  age: 22,
  address: {
    street: 'Gujarda',
    city: 'Mandsaur',
    state: 'MP',
    zip: '458002'
  },
  sayHello: function() {
    console.log('Hello, my name is ${this.name}');
  }
};
```

In this example, we define an object called person that has four properties: name, age, address, and sayHello. The address property is itself an object with its own properties. The sayHello property is a method that logs a message to the console using the this keyword to refer to the person object.

```We can access the properties and methods of an object using dot notation or bracket notation:
console.log(person.name); // "Ajay"
console.log(person.address.city); // "Mandsaur"
person.sayHello(); // "Hello, my name is Ajay."
```
<hr>