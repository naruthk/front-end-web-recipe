# Events Propagation

## Phrases

There are three phases in an event propagation:

- Capturing phrase
- Target phrase
- Bubbling phrase

**Determining which phrase you are in** can be done by using

`console.log(e.eventPhase, e.currentTarget)`

- `1` means you're in the capturing phrase
- `2` means the target phrase
- `3` means the bubbling phrase

### Capturing Phrase

JavaScript goes through `window` -> `document` -> every HTML element until it reaches the target element of the event.

### Target Phrase

JavaScript arrives at the target element and triggers all event listeners that are attached to the element.

### Bubbling Phrase

JavaScript goes through every HTML element, beginning with the target element and ending with `window`.

## Event Firing Sequence

The event listener that is attached first will run first.

```javascript
const button = document.querySelector('button')
button.addEventListener('click', e => console.log('#1'))
button.addEventListener('click', e => console.log('#2'))
```

Output:

```
#1
#2
```