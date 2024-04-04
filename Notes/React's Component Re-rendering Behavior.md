The statement "any time a parent re-renders, its child also gets re-rendered in React" essentially refers to React's behavior of propagating updates down the component tree. When a parent component re-renders due to a state or props change, React will also re-render all of its child components.

Here's a breakdown of why and how this happens:

1. **Virtual DOM Reconciliation**:
   React utilizes a virtual DOM to efficiently update the actual DOM. When a component re-renders, React reconciles the changes between the previous virtual DOM and the new one. This reconciliation process determines which parts of the DOM need to be updated.

2. **Component Tree Relationship**:
   React components are organized in a hierarchical structure, forming a component tree. Parent components contain child components, and changes in parent components can affect their children.

3. **Propagating Updates**:
   When a parent component re-renders due to a state change or receiving new props, React recursively traverses the component tree and re-renders all affected child components. This ensures that the UI stays in sync with the application state.

Let's illustrate this with a simple example:

```jsx
import React, { useState } from 'react';

// Child Component
const ChildComponent = ({ name }) => {
  console.log('ChildComponent rendering');
  return <div>Hello, {name}!</div>;
};

// Parent Component
const ParentComponent = () => {
  const [count, setCount] = useState(0);
  console.log('ParentComponent rendering');
  
  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Increment Count</button>
      <ChildComponent name="Alice" />
    </div>
  );
};

// App Component
const App = () => {
  console.log('App rendering');
  return <ParentComponent />;
};

export default App;
```

In this example, the `App` component renders the `ParentComponent`, which contains the `ChildComponent`. When the "Increment Count" button is clicked, the `ParentComponent`'s state changes, causing it to re-render. As a result, the `ChildComponent` also re-renders because it's a child of `ParentComponent`. You'll see the "ChildComponent rendering" log in the console each time the button is clicked.

This behavior ensures that the UI remains consistent with the application state throughout the component hierarchy in React.