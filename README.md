### Functions in JavaScript

A function in JavaScript is a reusable block of code designed to perform a particular task. Functions are defined with the `function` keyword followed by a name, parentheses `()`, and a block of code `{}`.

**Example:**

```javascript
function greet(name) {
  console.log('Hello, ' + name + '!');
}
greet('Alice');
```

### Parameters and Arguments in Functions

Parameters are variables listed as part of the function definition, while arguments are the actual values passed to the function when it is called. Functions can take any number of parameters, and when calling a function, you can pass as many arguments as there are parameters.

#### Example: Understanding Parameters and Arguments

```javascript
// Defining a function with two parameters: 'firstName' and 'lastName'
function fullName(firstName, lastName) {
  return firstName + ' ' + lastName;
}

// Calling the function with two arguments: 'Alice' and 'Smith'
console.log(fullName('Alice', 'Smith')); // Output: Alice Smith

// Function with a default parameter
function greet(name, greeting = 'Hello') {
  return `${greeting}, ${name}!`;
}

// Calling function with and without the second argument
console.log(greet('Bob')); // Output: Hello, Bob!
console.log(greet('Bob', 'Goodbye')); // Output: Goodbye, Bob!
```

#### Exercises

1. Write a function that accepts three numbers as parameters and returns their average.
2. Modify the above function to handle the case where only two numbers are passed as arguments, using default parameters to assume the third number is 0.

### Arrow Functions

Arrow functions provide a concise syntax for writing function expressions. They do not have their own `this`, do not have `arguments`, cannot be used as constructors, and are best suited for non-method functions. Arrow functions are anonymous, meaning they do not have a name unless assigned to a variable.

**Syntax:**

Create an anonyme arrow function:
```javascript
(name) => {
  console.log('Hello, ' + name + '!');
}
// Arrow function isnt saved anywhere so you cant call it.
```

Save an arrow function to a variable, so you can call and use it like a normal function:
```javascript
const greet = (name) => {
  console.log(`Hello, ${name}!`);
};
greet('Bob');
```

Arrow functions with a single parameter do not need parentheses around the parameter list, and a function with a single expression can omit the curly braces `{}` and the `return` keyword.

**Simplified Arrow Function:**

```javascript
const greet = name => `Hello, ${name}!`;
console.log(greet('Charlie'));
```

### Return Values in Functions and Arrow Functions

Functions in JavaScript can return a value using the `return` statement. The value returned from a function can be of any type, including numbers, strings, objects, or even other functions. Arrow functions also support return values, and when using a concise body (a single-expression arrow function), the return is implicit.

#### Example: Understanding Return Values

```javascript
// Standard function with return value
function add(a, b) {
  return a + b;
}
console.log(add(5, 3)); // Output: 8

// Arrow function with explicit return
const subtract = (a, b) => {
  return a - b;
};
console.log(subtract(10, 5)); // Output: 5

// Single-expression arrow function with implicit return
const multiply = (a, b) => a * b;
console.log(multiply(3, 4)); // Output: 12
```

#### Exercises

1. Write a function that takes a string and returns its length.
2. Convert the above function into an arrow function.
3. Create a function that returns an array containing three elements: the sum, difference, and product of two numbers.

### Custom `forEach` Function

Now, let's create a simple replica of the `forEach` function. The `forEach` method in JavaScript executes a provided function once for each array element. Here's a simplified version:

```javascript
function forEach(array, callback) {
  for (let i = 0; i < array.length; i++) {
    callback(array[i], i, array); // Pass the current item, index, and the entire array to the callback
  }
}
```

**Using the Custom `forEach` Function:**

```javascript
const numbers = [1, 2, 3, 4, 5];

forEach(/* array */ numbers, /* arrow function */ (item, index) => {
  console.log(`Element at ${index}: ${item}`);
});
```

### Exercises

1. Write a function called `sum` that takes an array of numbers and returns the sum of those numbers.
2. Convert the `sum` function into an arrow function.
3. Use the custom `forEach` function to iterate over an array of strings and print each string with the prefix "Item: ".

### Explanation of `forEach` and Callback Method

In the custom `forEach` example above, `forEach` is a function that takes an array and a callback function as parameters. It iterates over the array, and for each element, it executes the callback function, passing the current element, its index, and the entire array as arguments. This demonstrates how functions can be passed as arguments (callbacks) and executed within other functions, a powerful feature in JavaScript for asynchronous operations and handling events.

### Additional Task

1. Modify the custom `forEach` function to stop execution if the callback function returns `false`.

## Explanation

Pass an arrow function that does some sort of comparing using an if statement. Compare one of the parameter item or index with something else. If the condition is wrong, return false. In the forEach make an if statement that uses this arrow function and passes the needed variable (parameter) to that function. If the arrow function returns false, end the forEach. You can do this by simply writing "return" and nothing more. That basically means return a value from this function, but writing nothing after the return just ends this functio.
