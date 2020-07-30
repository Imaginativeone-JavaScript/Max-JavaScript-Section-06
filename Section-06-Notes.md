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

- Using the latter technique, the function (on the right side of the assignment operator) doesn't store the FUNCTION in the hoisted global scope. Rather, "start" is stored there and "multiply" (takes some sort of lesser role?) As a matter of fact, "multiply" can be omitted. An anonymous function can be used.

- Using Function Expressions forces me to define functions before I call them?