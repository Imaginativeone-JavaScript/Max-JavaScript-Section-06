# JavaScript - The Complete Guide 2020 (Beginner + Advanced)

## Section 06: More on Functions

## 123 Module Introduction
- Different Ways of Creating Functions
- Anonymous Functions
- Callback Functions & Functions in Functions
- Default Arguments & Rest Operator

## 124 Recapping Functions Knowledge - What We Know Thus Far
- Functions are "Code on Demand"
- Variables and constants created in functions "belong" to that function
- Functions CAN take parameters (arguments) and CAN return a value
- Functions can be called multiple times (with different arguments)

## 125 Parameters vs Arguments
- Throughout this course, you'll hear me use the words "parameters" and "arguments" interchangeably.
- Technically, there is a difference though:
- Parameters are these variables which you specify between parentheses when defining a function.

```javascript
function sayHi(name) { ... } 
```

- In this example, name is a parameter.
- Arguments then are the concrete values you pass to a function when calling that function:
- sayHi('Max');
- 'Max' is an argument of the function therefore - for the name parameter to be precise.
- Since both concepts obviously are extremely close connected, I will often say "let's define which arguments a function receives" or something comparable, since defining the arguments of a function in the end means that you set up its parameters (and vice-versa).

## 126 Functions vs Methods
- In an object, we have property/value pairs
- A "method" is when a property has a function for a value

```javascript
const person = {
    name: 'Doug',
    greet: function greet() {
        console.log('Hello there');
    }
}

person.greet();
```

## 127 Functions are Objects
```javascript
function greet() {
    const userName = 'Doug';
    console.log('Hello ' + userName);
}

console.log(typeof greet);  // 'function' is the type
console.dir(greet);         // Object properties show here

greet();
```

## 128 Function Expressions: Storing Functions in Variables
- One way of making a function is this: **Function Declaration**
```javascript
function multiply(a, b) {
    console.log(a*b);
}
```

- Another way of making a function is this: **Function Expression**
```javascript
const start = function multiply(a, b) {
    console.log(a*b);
}
```

## 129 More Notes on Function Expressions
- Using the latter technique, the function (on the right side of the assignment operator) doesn't store the FUNCTION in the hoisted global scope. Rather, "start" is stored there and "multiply" (takes some sort of lesser role?) As a matter of fact, "multiply" can be omitted. An anonymous function can be used.

- Using Function Expressions forces me to define functions before I call them?

## 130 Anonymous Functions
- Single use
- Used in eventListeners
- Assigning anonymous functions to variables helps with debugging

## 133 Introducing Arrow Functions
- Nested ternary expression example

- General difference (saves time and code lines)
```javascript
const add = (a, b) => a + b;

const add2 = function(a, b) {
    return a + b;
}
```

- General Syntax: (arg1, arg2) => { ... } // ... = function body
- No arguments: () => { ... }
- Exactly one argument: arg => { ... }
- Exactly one expression in function body: (a, b) => a + b // can omit curly braces
  - "return" must be omitted, there's an invisible return

## 136 Default Arguments

```javascript
const someFunction = (choiceA, choiceB = DEFAULT_ARGUMENT);
```

This keeps choiceB from being undefined within the function that uses it as a parameter.

## 137 Introducing Rest Parameters

```javascript
const sumUp = (a, b, c, d) => {}; // I need a variable amount of arguments

sumUp(1, 2, 3, 4);
sumUp(1, 2, 3, 4, 5);
```

I could use a loop...

It looks like the spread operator: [...]

```javascript
const sumUp = (...numbers) => { // arguments get merged into an array inside the function
                                // must be the LAST parameter
                                // I can only use one of these
  let sum = 0;
  
  for (const num of numbers) {
    sum += num;
  }
  return sum;
}
```

- Using the "function" keyword, and not arrow functions, I can use the "arguments" keyword.

## 138 Creating Functions Inside of Functions
- Locally scoped because of block scope
- Usually, I want global functions

## 139 Understanding Callback Functions
- The function is "called for me in the future".
- Alternative to return

## 140 Working with bind()
- Need to pass in a value, but don't want to directly execute a function
- Prepare my "to be called" function, which I don't call myself

## 142 call() and apply()
- 