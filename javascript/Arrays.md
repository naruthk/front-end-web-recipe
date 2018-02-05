# Arrays (General)

- Length: `array.length`
- Getting value: `array[n]`
- Getting last item: `array[array.length - 1]`
- Find position: `array.indexOf(number)`
- Add to end: `array.concat(items)`
- Remove item from the front (slice): `array.slice(start, end)`
- Remove item from the end (slice): `array.slice(0, array.length - 1)`
- Remove an item from the middle: 
  ```javascript
  const numbers = [1,2,3,4,5,6,7,8]
  const firstPart = numbers.slice(0, 2) // [1,2]
  const secondPart = numbers.slice(4) // [5,6,7,8]
  const combinedArray = firstPart.concat(secondPart)
  // Or do this:
  const combinedArray = [].concat(firstPart, secondPart)
  ```
- Add to the middle:
  ```javascript
  const numbers = [1,2,3,4 7,8]
  const firstPart = numbers.slice(0, 2) // [1,2]
  const secondPart = numbers.slice(4) // [5,6,7,8]
  const arrayToAdd = [5, 6]
  const combinedArray = [].concat(firstPart, arrayToAdd, secondPart)
  ```
  
## Note!

- Do not use `pop`, `push`, `unshift`, `splice` because these methods **mutate** the array.