# Attributes

- Think of things like `checked` attribute
- Set attribute: `Element.setAttribute('name-of-attribute', 'value to set')`
- Get/Read attribute: `Element.getAttribute`
- Remove attribute: `Element.removeAttribute('attribute-name')`

## Example

```javascript
<div class="clown-hat" data-color="red" data-size="big">A Clown hat</div>

const clownHat = document.querySelector('.clown-hat')
const clownHatColor = clownHat.getAttribute('data-color')
const clownHatSize = clownHat.getAttribute('data-size')

console.log(clownHatColor) // 'red'
```

## Another Example

```html
<div class="clown-hat" data-color="red" data-num-stripes="3">A Clown hat</div>
```

```javascript
const clownHat = document.querySelector('.clown-hat')
clownHat.removeAttribute('data-color')
```

```html
// Result:
<div class="clown-hat" data-num-stripes="3">A Clown hat</div>
```