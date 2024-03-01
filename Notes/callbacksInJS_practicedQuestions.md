#### Understanding callbacks in JavaScript is crucial for asynchronous programming. Here are a few coding problems that will help you get a complete understanding of callbacks:

### 1. Simple Callback

**Problem Statement:**
Create a function `printMessage` that takes a string `message` and a callback function as arguments. The `printMessage` function should print the message to the console and then call the callback function.

**Solution:**
```javascript
function printMessage(message, callback) {
    console.log(message);
    callback();
}

// Usage
printMessage("Hello, World!", function() {
    console.log("This is a callback function.");
});
```

### 2. Callback with Parameters

**Problem Statement:**
Modify the `printMessage` function to accept a callback function that itself takes a parameter. The callback function should be called with a string "Callback was called."

**Solution:**
```javascript
function printMessage(message, callback) {
    console.log(message);
    callback("Callback was called.");
}

// Usage
printMessage("Hello, World!", function(callbackMessage) {
    console.log(callbackMessage);
});
```

### 3. Callback Chaining

**Problem Statement:**
Create a function `processData` that simulates data processing. It should take an array of numbers, process each number (for example, by multiplying it by 2), and then call a callback function with the processed data.

**Solution:**
```javascript
function processData(data, callback) {
    const processedData = data.map(num => num * 2);
    callback(processedData);
}

// Usage
processData([1, 2, 3, 4], function(result) {
    console.log(result); // [2, 4, 6, 8]
});
```

### 4. Callback with Error Handling

**Problem Statement:**
Modify the `processData` function to include error handling. If the input data is not an array, the callback should be called with an error message.

**Solution:**
```javascript
function processData(data, callback) {
    if (!Array.isArray(data)) {
        callback("Error: Data is not an array.");
        return;
    }
    const processedData = data.map(num => num * 2);
    callback(null, processedData);
}

// Usage
processData([1, 2, 3, 4], function(error, result) {
    if (error) {
        console.error(error);
    } else {
        console.log(result); // [2, 4, 6, 8]
    }
});
```

### 5. Callback in a Loop

**Problem Statement:**
Create a function `processArray` that takes an array of numbers and a callback function. The function should iterate over the array, process each number (for example, by multiplying it by 2), and then call the callback function with the processed number.

**Solution:**
```javascript
function processArray(array, callback) {
    array.forEach(function(num) {
        const processedNum = num * 2;
        callback(processedNum);
    });
}

// Usage
processArray([1, 2, 3, 4], function(result) {
    console.log(result); // Called for each number in the array
});
```