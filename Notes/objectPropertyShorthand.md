 # Object Property Shorthand

#### In JavaScript, there's a feature called "shorthand property names". This means that if the name of the variable matches the name of the property you want to create in the object, you can just write the name once.

Here's an example:

```javascript
let category = "food";
let totalSpent = 100;

let obj = {category, totalSpent};
```

This is equivalent to:

```javascript
let obj = {category: category, totalSpent: totalSpent};
```

But because the names match, you can use the shorthand version. So, `{category, totalSpent}` is a shorter way of writing `{category: category, totalSpent: totalSpent}`.

In your case, `category` and `totalSpent` are variables that hold values. When you write `{category, totalSpent}`, you're creating a new object with properties named `category` and `totalSpent`, and their values are whatever the current values of the `category` and `totalSpent` variables are.