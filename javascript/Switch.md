# Switch Statements

## Typical format

```javascript
switch (expression) {
  case n:
    // do something
    break;
  case n:
    // do something
    break;
  default:
    // do something
}
```

## When there's a common code block

```javascript
switch (new Date().getDay()) {
  case 4:
  case 5:
    text = "Soon it is Weekend";
    break;
  case 0:
  case 6:
    text = "It is Weekend";
    break;
  default:
    // do something
}
```