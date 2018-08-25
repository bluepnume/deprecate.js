# No `this` outside of classes

## Rationale

Show me a javascript engineer who thinks `this` is a great idea outside of the context of a class, and I'll show you a javascript engineer who doesn't want to waste all the time they spent learning the myriad values of `this`.

Here's what I propose:

Unless you're directly in a class method, or an arrow function inside a class method, `this` is a syntax error.

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
