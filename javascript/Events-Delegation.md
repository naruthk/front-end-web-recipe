# Event Delegation

A pattern where you attach one listener to an ancestor element.

For example, to listen for the `click` event on each item, attach the event listener on the `ul` Element rather than each individual `li`.

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
  <li>Item 4</li>
  <li>Item 5</li>
</ul>
```

```javascript
const listener = document.querySelector('ul')
listener.addEventListener('click', e => {
  if (e.target.matches('li')) {
    // This ensures that what we want to select is the Li tag, and not the Ul
    console.log(e.target)
  }
})
```