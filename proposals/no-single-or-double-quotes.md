# No Single or Double Quotes

## Rationale

We now have template strings. They cover a superset of use-cases over regular strings (multi-line support, interpolation).

So maybe let's not keep around three different ways to create strings?

## Good

```javascript
let foo = `bar`;
```

```javascript
console.log(`bar ${ baz }`);
```

## Bad

```javascript
let foo = 'bar';
```

```javascript
console.log("bar " + baz);
```
