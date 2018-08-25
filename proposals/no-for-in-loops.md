# No for-in loops

## Rationale

For-in loops are weird, and behave erratically over both arrays and objects.

- For arrays, they behave weirdly if there are any sparse indexes.
- For objects, they also loop over keys in the prototype chain. And who needs that?

## Good

```javascript
for (let item of myArray) {
    console.log(item);
}
```

```javascript
for (let i = 0, i < myArray.length; i++) {
    console.log(i, myArray[i]);
}
```

```javascript
for (let key of Object.keys(myObject)) {
    console.log(key, myObject[key]);
}
```

## Bad

```javascript
for (let i in myArray) {
    console.log(i, myArray[i]);
}
```

```javascript
for (let key in myObject) {
    if (myObject.hasOwnProperty(key)) {
        console.log(key, myObject[key]);
    }
}
```

## Discussion

https://github.com/bluepnume/deprecate.js/issues/1
