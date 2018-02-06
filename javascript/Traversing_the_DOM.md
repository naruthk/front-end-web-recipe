# Traversing the DOM

**Key Summary**:

- Traverse down
  - Use `querySelector` or `querySelectorAll`
  - Use `children`
- Traverse up
  - Use `parentElement`
  - Use `Element.closest`
- Traverse sideways
  - Use `Node.nextElementSibling`
  - Use `Node.previousElementSibling`

--- 
## Traverse Down

```html
<div class="component">
  <h2 class="component__title">Component 1 title</h2>
</div>
<div class="component">
  <h2 class="component__title">Component 2 title</h2>
</div>
```

### **`querySelector`** or **`querySelectorAll`**

```javascript
const components = document.querySelectorAll('.component')

components.forEach(component => {
  const title = component.querySelector('.component__title')
  console.log(component)  // <div class="component">..</div>
  console.log(title)  // <h2 class="component__title">Component 1 title</h2>
})
```

### With **`Element.children`** method

#### document.querySelector

```javascript
const list = document.querySelector('list')
const listItems = list.children

console.log(listItems)
```

#### document.querySelectorAll

Allows iteration on each individual `li` Element, like so:

```javascript
const listItems = document.querySelectorAll('list')
const fifthItem = listItems[4]

console.log(fifthItem)
```

---

## Traverse Up

```html
<ul class="list">
  <li><a href="#">Link 1</a></li>
  <li><a href="#">Link 2</a></li>
  <li><a href="#">Link 3</a></li>
  <li><a href="#">Link 4</a></li>
  <li><a href="#">Link 5</a></li>
</ul>
```

### With `parentElement`

```javascript
const firstListItem = document.querySelector('li')
const list = firstListItem.parentElement

console.log(list)   // <ul class="list">...</ul>
```

### With `Element.closest`

```javascript
const firstLink = document.querySelector('a')
const list = firstLink.closest('.link')

console.log(list)   // <ul class="list">...</ul>
```

---

## Traverse Sideways

```html
<ul class="list">
  <li><a href="#">Link 1</a></li>
  <li><a href="#">Link 2</a></li>
  <li><a href="#">Link 3</a></li>
  <li><a href="#">Link 4</a></li>
  <li><a href="#">Link 5</a></li>
</ul>
```

### With `Node.nextElementSibling`

```javascript
const firstListItem = document.querySelector('li')
const secondListItem = firstListItem.nextElementSibling

console.log(secondListItem)   // <li><a href="#">Link 2</a></li>
```

### With `Node.previousElementSibling`

```javascript
const secondListItem = document.querySelectorAll('li')[1]
const firstListItem = secondListItem.previousElementSibling

console.log(firstListItem)    // <li><a href='#">Link 1</a></li>
```