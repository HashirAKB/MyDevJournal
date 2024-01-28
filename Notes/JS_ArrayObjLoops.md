# **JavaScript Study Notes: Arrays, Objects, Loops, and More**

**Introduction:** This markdown file serves as a comprehensive study guide for understanding various aspects of JavaScript programming. It covers topics such as working with arrays and objects, looping constructs, and methods for manipulating data structures. The notes also delve into advanced concepts like checking for duplicates before adding items to an array and breaking down complex code lines. Whether you're a beginner looking to grasp the basics or an experienced programmer seeking to deepen your knowledge, this guide offers valuable insights and practical examples to enhance your JavaScript skills.

### Introduction to JavaScript Arrays

[{ category: 'Food', totalSpent: 10 }]
How to assign this into a variable in javascript?

In JavaScript, you can assign an array to a variable like this:

```javascript
let myVariable = [{ category: 'Food', totalSpent: 10 }];
```

This creates a variable named `myVariable` and assigns it an array containing one object. The object has properties `category` and `totalSpent`.

### Working with JavaScript Objects

How to append one more object into this array?
To append another object to the array, you can use the `push()` method. Here's how you can do it:

```javascript
myVariable.push({ category: 'Drinks', totalSpent: 5 });
```

This will add a new object `{ category: 'Drinks', totalSpent: 5 }` to the `myVariable` array.

I want to check whether a catergory is already there or not before pushing new object?
Sure, you can use the `some()` method to check if an object with a specific category already exists in the array before pushing a new object. Here's how you can do it:

```javascript
let newCategory = { category: 'Drinks', totalSpent: 5 };

if (!myVariable.some(item => item.category === newCategory.category)) {
    myVariable.push(newCategory);
}
```
### Exploring Object.entries() and Array.prototype.map() Methods

In this code, `some()` checks if there's any object in `myVariable` whose `category` property matches `newCategory.category`. If there isn't, it pushes `newCategory` to the array.

```js
return Object.entries(TotalSpentByCategory).map(([category, totalSpent]) => ({category, totalSpent}));
```
Didn't understood this line of code?
Sure, let's break down this line of code:

1. `Object.entries(TotalSpentByCategory)`: This part of the code converts the `TotalSpentByCategory` object into an array of key-value pairs. Each pair is itself an array where the first element is the key (in this case, the category) and the second element is the value (the total spent).

2. `.map(([category, totalSpent]) => ({category, totalSpent}))`: This part of the code uses the `Array.prototype.map()` method to create a new array based on the array returned by `Object.entries()`. The `map()` method calls the provided function once for each element in the array, in order.

   In this case, the provided function is `(category, totalSpent) => ({category, totalSpent})`, which is an arrow function that takes two arguments (the key and value from each pair) and returns a new object with those values.

So, overall, this line of code is converting the `TotalSpentByCategory` object into an array of objects, where each object represents a category and its total spent.

Absolutely, here's the same operation broken down into multiple steps:

```javascript
// Convert the object into an array of key-value pairs
let entries = Object.entries(TotalSpentByCategory);

// Map over the array of entries
let mappedEntries = entries.map(entry => {
    // Destructure the entry into key and value
    let [category, totalSpent] = entry;

    // Return a new object with the key and value
    return {category, totalSpent};
});

// Now mappedEntries is an array of objects
return mappedEntries;
```

This code does exactly the same thing as the single line of code, but it's broken down into multiple steps for clarity.

I'm new to the ```entries``` and ```map```. Give me a study note about these two with suitable examples.
Sure, here's a brief explanation of `Object.entries()` and `Array.prototype.map()` along with examples:

1. **Object.entries()**: This method returns an array of a given object's own enumerable string-keyed property [key, value] pairs. It's often used when you want to iterate over the properties of an object.

   Example:
   ```javascript
   let obj = { a: 1, b: 2, c: 3 };
   console.log(Object.entries(obj));
   // Output: [['a', 1], ['b', 2], ['c', 3]]
   ```
   In this example, `Object.entries(obj)` returns an array of arrays, where each sub-array is a [key, value] pair from the `obj` object.

2. **Array.prototype.map()**: This method creates a new array populated with the results of calling a provided function on every element in the calling array. It's often used when you want to transform all elements in an array in some way.

   Example:
   ```javascript
   let arr = [1, 2, 3, 4, 5];
   let squares = arr.map(num => num * num);
   console.log(squares);
   // Output: [1, 4, 9, 16, 25]
   ```
   In this example, `arr.map(num => num * num)` returns a new array where each element is the square of the corresponding element in the original `arr` array.

Remember, `Object.entries()` is used with objects, while `Array.prototype.map()` is used with arrays.

The `map` function in JavaScript is used to transform each element of an array according to a specified callback function. It creates a new array with the results of applying the callback function to each element of the original array. Here are some more examples of using the `map` function:

### Example 1: Doubling each element in the array

```javascript
let numbers = [1, 2, 3, 4, 5];
let doubledNumbers = numbers.map(num => num * 2);
console.log(doubledNumbers);
// Output: [2, 4, 6, 8, 10]
```

### Example 2: Converting strings to uppercase

```javascript
let words = ['apple', 'banana', 'cherry'];
let uppercasedWords = words.map(word => word.toUpperCase());
console.log(uppercasedWords);
// Output: ['APPLE', 'BANANA', 'CHERRY']
```

### Example 3: Mapping an array of objects

```javascript
let people = [
  { name: 'Alice', age: 30 },
  { name: 'Bob', age: 25 },
  { name: 'Charlie', age: 35 }
];

let names = people.map(person => person.name);
console.log(names);
// Output: ['Alice', 'Bob', 'Charlie']
```

### Example 4: Calculating the square root of each element

```javascript
let numbers = [4, 9, 16, 25];
let squareRoots = numbers.map(num => Math.sqrt(num));
console.log(squareRoots);
// Output: [2, 3, 4, 5]
```

### Example 5: Mapping an array of objects and adding a new property

```javascript
let people = [
  { name: 'Alice', age: 30 },
  { name: 'Bob', age: 25 },
  { name: 'Charlie', age: 35 }
];

let peopleWithFullName = people.map(person => ({
  ...person,
  fullName: `${person.name} Smith`
}));

console.log(peopleWithFullName);
// Output: [{ name: 'Alice', age: 30, fullName: 'Alice Smith' },
//          { name: 'Bob', age: 25, fullName: 'Bob Smith' },
//          { name: 'Charlie', age: 35, fullName: 'Charlie Smith' }]
```

These examples demonstrate the flexibility of the `map` function in transforming and creating new arrays based on the elements of an existing array. The key is to provide a callback function that defines the transformation logic for each element.

### Understanding the for...of Loop in JavaScript

what is ```for...of``` loop?
The `for...of` statement creates a loop iterating over iterable objects, including: built-in String, Array, array-like objects (e.g., arguments or NodeList), TypedArray, Map, Set, and user-defined iterables. It invokes a custom iteration hook with statements to be executed for the value of each distinct property of the object.

Here's a basic example:

```javascript
let iterable = [10, 20, 30];

for (let value of iterable) {
 console.log(value);
}

// Output:
// 10
// 20
// 30
```

In this example, the `for...of` loop iterates over the `iterable` array. On each iteration, the `value` variable is assigned the current value from the array, and then the body of the loop is executed.

The `for...of` loop is a simpler syntax compared to traditional `for` loops and is especially useful when working with data structures that are iterable, like arrays or sets.