# Concepts in JavaScript

## Filter
- The `filter()` method creates a new array with all elements that pass the test implemented by the provided function.
- Example:
  ```javascript
  const numbers = [1, 2, 3, 4, 5];
  const evenNumbers = numbers.filter(num => num % 2 === 0);
  // evenNumbers will be [2, 4]```

## Map
 - The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.
 - Example:
```javascript
const numbers = [1, 2, 3, 4, 5];
const doubledNumbers = numbers.map(num => num * 2);
// doubledNumbers will be [2, 4, 6, 8, 10]
```

## Arrow Functions
 - Arrow functions are a more concise way of writing function expressions in JavaScript.
 - Example:
```javascript
const add = (a, b) => a + b;
```

## ForEach
 - The forEach() method executes a provided function once for each array element.
 - Example:
 ```javascript
const numbers = [1, 2, 3];
numbers.forEach(num => console.log(num));
// Output: 1, 2, 3
```

## Reduce
 - The reduce() method executes a reducer function on each element of the array, resulting in a single output value.
 - Example:
```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
// sum will be 15
```

## Spread Operator
 - The spread operator (...) allows an iterable to be expanded into individual elements.
 - Example:
```javascript
const numbers = [1, 2, 3];
const combined = [...numbers, 4, 5];
// combined will be [1, 2, 3, 4, 5]
```

## Destructuring
 - Destructuring allows you to extract values from arrays or objects and assign them to variables.
 - Example:
```javascript
const person = { name: 'John', age: 30 };
const { name, age } = person;
// name will be 'John' and age will be 30
```

### These concepts are fundamental in JavaScript for manipulating arrays and creating concise and readable code.