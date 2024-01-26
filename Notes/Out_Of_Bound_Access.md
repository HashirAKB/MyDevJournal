# Study Note: Array Access

Accessing elements outside the bounds of an array results in `undefined`. Here's an example:

```javascript
let myArray = [1, 2, 3, 4, 5];
console.log(myArray[5]); // Outputs: undefined
```

In the code above, `myArray[5]` is trying to access the 6th element of the array `myArray`. Since `myArray` only contains five elements, indexed from 0 to 4, this access is out of bounds, and JavaScript returns `undefined`.
