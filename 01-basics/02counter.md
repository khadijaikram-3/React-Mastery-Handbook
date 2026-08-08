# 02counter — useState Hook

## 📌 Project Overview
A simple counter app that demonstrates **state management** and the **React mindset**.

## 🎯 Key Concepts (Interview Ready)

### 1. useState Hook
- **Syntax:** `const [state, setState] = useState(initialValue)`
- Returns an array with two elements: current state and a setter function
- 🎯 When `setState` is called, React **re-renders** the component

### 2. 🎯 Batching Updates (Critical Interview Topic)
React **batches** state updates for performance.
```javascript
// ❌ This only increments once!
const addValue = () => {
    setCounter(counter + 1);
    setCounter(counter + 1);
    setCounter(counter + 1);
}

// ✅ This increments three times!
const addValue = () => {
    setCounter(prev => prev + 1);
    setCounter(prev => prev + 1);
    setCounter(prev => prev + 1);
}
``` 
## 3. Why Use Callback in Setter?
Guarantees you're working with the most recent state

Prevents race conditions in async operations

🎯 Always use callback when new state depends on previous state

## 💻 Code Snippets
useState Initialization
javascript
import { useState } from 'react'
const [counter, setCounter] = useState(15)
Handler with Callback
javascript
const addValue = () => {
    setCounter(prevCounter => prevCounter + 1)
}
## 🎯 Interview Questions
Q: What happens when you call setState?
A: React schedules a re-render of the component and all its children.

Q: Why use prev => prev + 1 instead of counter + 1?
A: React batches updates. Using the callback ensures you're working with the most recent state.

Q: How does React handle multiple setState calls?
A: React batches them together for performance and applies them in a single re-render.

# 🧠 Key Takeaway
State updates trigger re-renders. Always use the callback pattern when the new state depends on the previous state.
