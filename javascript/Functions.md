# Functions

A function is JavaScript procedure: a set of statements that performs a task or calculates a value. 

## Function Declaration

`function square(number) {}`

## Hoisting

This is an example of hoisting. What is returns is "TypeError: square is not a function". In JavaScript, if the function is defined as a variable, it gets hoisted to the top. And so the variable function tries to call the function square(5) but the function doesn't exist yet.

```javascript
console.log(square(5)); 
var square = function(n) { 
  return n * n; 
}

// Returns TypeError: square is not a function
```

## Arrow Functions

Note that `this` in an arrow function is set to a different value than a normal function.

```javascript
// Two arguments
const f = (arg1, arg2) => {
  console.log(arg1 + arg2)
}

// Zero argument
const f = () => {
  // Do something
}

// Zero argument (Underscore version)
const f = _ => {
  // Do something
}

// Implicit return
const sumArrow = (num1, num2) => num1 + num2
```
