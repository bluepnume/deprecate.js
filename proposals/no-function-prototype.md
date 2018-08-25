# No Function Prototype

## Rationale

We now have a quick and easy way to create classes, with support for single inheritance, super, and actually readable code. So let's stick with that and ditch all of that `MyClass.prototype.baz` nonsense?

## Good

```javascript
class Foo() {
    constructor(foo) {
        this.foo = foo;
    }
    baz() {
        console.log(this.foo);
    }
}
```

## Bad

```javascript
function Foo(foo) {
    this.foo = foo;
}

Foo.prototype.baz = function() {
    console.log(this.foo);
};
```
