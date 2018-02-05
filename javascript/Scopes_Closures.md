# Scopes & Closures

An outer function cannot obtain the value of the inner function, but the inner function (the closure) can.

## Block Scope

- A `var` variable do not respect the block scope.

  ```javascript
  
  // Doesn't work when declared with "const"
  {
    const hello = 'Hello world!'''
  }
  
  // Works when declared with "var"
  {
    var hello = 'Hello world!'
    console.log(hello)
  }
  console.log(hello)  // Hello world!
  ```

## Infamous `For` Loop Problem

```javascript
// Here the variable declared as "var" do not
// respect the block scope. 
// Output is: 1,2,3,4,5,5,5,5
// Fix by changing var to const

for (var i = 1; i < 5; i++) {
  console.log(i)
  setTimeout(function () {
    console.log(i)
  }, 1000)
};
```

## Closures

```javascript
// Generic pattern
function outerFn () {
  var outerVar = `I'm a variable in the outer function!`
  return function innerFn () {
    console.log(outerVar)   // Inner function have access to outer function
  }
}

const theInnerFunction = outerFn()
theInnerFunction()    // Use the parens to call the inner function
```