# No `function` keyword

## Rationale

The `function` keyword simply isn't needed any more. There are shorter, better ways to write functions in every situation. And it would be infinitely preferable to have as close to 'one way to do it' as possible. Hence: `function` must die.

## Good

```javascript
let foo = {
    bar(message) {
        console.log(message);
    }
}
```

```javascript
let foo = {
    bar: (message) => {
        console.log(message);
    }
}
```

```javascript
let bar = (message) => {
    console.log(message);
}
```

```javascript
export let bar = (message) => {
    console.log(message);
}
```

```javascript
class Foo {
    bar(message) {
        console.log(message);
    }
}
```

```javascript
setTimeout(() => {
    console.log('hello world')
}, 1000);
```

## Bad

```javascript
let foo = {
    bar: function(message) {
        console.log(message);
    }
}
```

```javascript
let bar = function(message) {
    console.log(message);
}
```

```javascript
function bar(message) {
    console.log(message);
}
```

```javascript
export function bar(message) {
    console.log(message);
}
```

```javascript
setTimeout(function() {
    console.log('hello world')
}, 1000);
```

### Notes

- You might ask "what if I want to make sure all of my functions have names?". In all of the 'good' examples above, the `bar` function is actually given a name which appears in stack traces -- with the exception of the `setTimeout` example. This is where I would absolutely love to propose named arrow functions; but, alas, this repository is about taking away features not adding them. That would solve the problem though:

  ```javascript
  setTimeout(bar() => {
      console.log('hello world')
  }, 1000);
  ```
