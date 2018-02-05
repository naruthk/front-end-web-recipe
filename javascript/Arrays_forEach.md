# Arrays (forEach)

## forEach

```javascript
array.forEach ((currentValue, index, array)) => {

})

array.forEach(currentValue => {

})
```

### Example

```javascript
const fruitBasket = ['banana', 'pear', 'guava']

// One-liner
fruitBasket.forEach(fruit => console.log(fruit))

fruitBasket.forEach(function (fruit) {
  console.log(fruit)
})

for (let fruit of fruitBasket) {
  console.log(fruit)
}

for (let i = fruitBasket.length - 1; i >= 0; i--) {
  console.log(fruitBasket[i])
}
```

```javascript
const paragraphs = document.querySelectorAll('p')
paragraphs.forEach(element => element.style.color = 'red')
```

