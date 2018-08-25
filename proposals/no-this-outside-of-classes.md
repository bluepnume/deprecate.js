# No `this` outside of classes

## Rationale

Show me a javascript engineer who thinks `this` is a great idea outside of the context of a class, and I'll show you a javascript engineer who doesn't want to waste all the time they spent learning the myriad values of `this`. (If you want to learn all the possible values of `this`, see [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this). This is all of the evidence you should need that this needs to be fixed...)

Here's what I propose:

Unless you're directly in a class method, or an arrow function inside a class method, `this` is a syntax error.

Reason: there are always better alternatives when you're outside of a class. Inside of a class, `this` is pretty much irreplaceable.

## Good

```javascript
class Foo {
    bar() {
        console.log(this.baz);
    }
}
```

```
class Foo {
    bar() {
        setTimeout(() => {
            console.log(this.baz)
        }, 1000);
    }
}
```

## Bad

```javascript
console.log(this.baz);
```

```javascript
function foo() {
    console.log(this.baz);
}
```

```javascript
let foo = () => {
    console.log(this.baz);
}
```

```javascript
let foo = {
    bar() {
        console.log(this.baz);
    }
}
```

```javascript
eval(`console.log(this.baz)`); // I mean this is like, doubly evil...
```

### Notes

- As a caveat to this, let's:
  - Remove `.bind()` entirely
  - Make `.call()` / `.apply()` only take arguments, and remove the context argument
