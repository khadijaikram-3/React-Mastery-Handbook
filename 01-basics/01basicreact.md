# 01basicreact — React Fundamentals

## 📌 Project Overview
The foundational "Hello World" project that demystifies React's file structure and shows how React injects itself into a web page.

## 🎯 Key Concepts (Interview Ready)

### 1. Single Page Application (SPA)
- Only **one HTML file** is ever served
- JavaScript handles all subsequent UI updates
- No page reloads — smooth user experience

### 2. JSX (JavaScript XML)
- HTML-like syntax inside JavaScript
- 🎯 **Syntactic sugar** for `React.createElement()`
- Must use `className` (not `class`) because `class` is a reserved keyword

### 3. Component Naming
- 🎯 Must use **PascalCase** (e.g., `Chai`, not `chai`)
- React distinguishes custom components from HTML tags by capitalization

### 4. The "Single Element" Rule
- JSX cannot return multiple sibling elements
- 🎯 **Solution:** Wrap in a **Fragment** (`<>...</>`) or a parent `<div>`

## 💻 Code Snippets

### Entry Point (`index.js`)
```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```
Simple Functional Component
javascript
function Chai() {
    return <h3>Chai is ready</h3>;
}
export default Chai;
🎯 Interview Questions
Q: Why use className instead of class?
A: class is a reserved keyword in JavaScript. React uses className to avoid conflicts.

Q: What is JSX?
A: JSX is syntactic sugar for React.createElement(). It allows HTML-like syntax in JavaScript.

🧠 Key Takeaway
React components are just functions that return JSX. The library handles the DOM updates.
