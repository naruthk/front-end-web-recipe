# Events

## Events Listener

Full list of events in MDN's [Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events).

```js
Element.addEventListener('event-name', callback)
```

```js
const button = document.querySelector('button')
button.addEventListener('click', function() {
  console.log('Button is clicked')
})
```

### Example: Alternating background when clicked

```css
body.button-is-clicked {
  background-color: green;
}
button.is-clicked {
  background-color: yellow;
}
```

```js
const button = document.querySelector('button')

button.addEventListener('click', function () {
  const body = document.body
  
  if (button.classList.contains('is-clicked')) {
    body.classList.remove('button-is-clicked')
    button.classList.remove('is-clicked')
  } else {
    body.classList.add('button-is-clicked')
    button.classList.add('is-clicked')
  }
})
```

#### Functions in Callbacks Can Break

```js
function toggleStyles () {
  const body = document.body

  if (button.classList.contains('is-clicked')) {
    body.classList.remove('button-is-clicked')
    button.classList.remove('is-clicked')
  } else {
    body.classList.add('button-is-clicked')
    button.classList.add('is-clicked')
  }
}

const button = document.querySelector('button')
button.addEventListener('click', toggleStyles)
```

In the code above, the event listener's callback function `toggleStyles` will work because the constant variable `button` is declared before the function is used.

But if we do this, instead:

```js
function toggleStyles () {
  const body = document.body

  if (button.classList.contains('is-clicked')) {
    body.classList.remove('button-is-clicked')
    button.classList.remove('is-clicked')
  } else {
    body.classList.add('button-is-clicked')
    button.classList.add('is-clicked')
  }
}

const clickMe = document.querySelector('button')
clickMe.addEventListenor('click', toggleStyles)
```

The function `toggleStyles` will fail because inside the function, we have the constant variable `button` that has not been predefined.

---

## `this`

