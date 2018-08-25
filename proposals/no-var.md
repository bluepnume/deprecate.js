# No `var`

## Rationale

There's no longer a need for `var`. `let` and `const` manage the same thing, without hoisting, and with block-scoping. If you're still using var you may need to reevaluate your life choices.

## Good

```javascript
let foo = `bar`;
```

```javascript
const foo = `bar`;
```

## Bad

```javascript
var foo = `bar`;
```
  
## Discussion

https://github.com/bluepnume/deprecate.js/issues/6
