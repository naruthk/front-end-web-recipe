# Attributes

- Think of things like `checked` attribute
- Set attribute: `Element.setAttribute('name-of-attribute', 'value to set')`
- Get/Read attribute: `Element.getAttribute`

## Example

```javascript
<div class="clown-hat" data-color="red" data-size="big">A Clown hat</div>

const clownHat = document.querySelector('.clown-hat')
const clownHatColor = clownHat.getAttribute('data-color')
const clownHatSize = clownHat.getAttribute('data-size')

console.log(clownHatColor) // 'red'
```