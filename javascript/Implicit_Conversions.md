# Implicit Conversions

What does this evaluate to?

```javascript
console.log(2.0 == '2' == new Boolean(true) == '1')
```

JavaScript evaluates the expression above by doing these steps:

1. Let's evaluate `2.0 == '2'`. JavaScript attempts to convert the RHS (the string `'2'`) to the LHS (the number `2.0`). The conversion will successfully return `true`.
2. Our returned value `true` is now our LHS while our RHS is `new Boolean(true)`. Evaluating the expression`true == new Boolean(true)` will also return `true` because JavaScript will successfully convert `new Boolean(true)` into the primitive (Boolean) value of `true`. Now the LHS (`true`) is equal to the RHS (`true`).
3. We now have to do a final comparison for `true == '1'`.In our previous steps, JavaScript converts the RHS to the LHS. Luckily those conversions were successful. Now JavaScript does something a little different. It sees that the comparison to be made is between a primitive type (`'true'`) and a String (`'1'`). So JavaScript tries to convert the LHS (`true`) to the RHS (`1`). A primitive boolean value of `true` converts to a String of value `1`. Therefore, `'1' == '1'`, which evaluates to `true`.

Our final answer is `true`.