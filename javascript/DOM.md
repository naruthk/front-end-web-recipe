# DOM Manipulations

- Selecting a single element: `const element = Element.querySelector(selector)`
- Selecting multiple elements: 'element.querySelectorAll
- Select an element with ID: use `#`
- Select an element with class: use `.`
- Select an element with tag: write the tag directly
- Select an element with attribute: use `[]`

## Example

```javascript
<div id="master-yoda">Yoda</div>
<div class="class-of-assassins">Assassin</div>
<p>The three little pigs</p>
<div data-rocket>🚀</div>

document.querySelector('#master-yoda')
// <div id="master-yoda">Yoda</div>

document.querySelector('.class-of-assasins')
// <div class="class-of-assassins">Assassin</div>

document.querySelector('p')
// <p>...</p>

document.querySelector('[data-rocket]')
// <div data-rocket></div>

```

## Notes

```javascript
const liveCollection = document.getElementsByTagName('p')
const staticCollection = document.querySelectorAll('p')
```


`liveCollection`'s value will change if we add another paragraph. However, `staticCollection`'s value will remain the same.