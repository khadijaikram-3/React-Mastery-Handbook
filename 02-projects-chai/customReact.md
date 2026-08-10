# customReact — Custom Renderer

## 📌 Project Overview
Build a mini-version of React from scratch to understand the **Virtual DOM** and **rendering process**.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 The React Element Structure
```javascript
const reactElement = {
    type: 'a',                // HTML tag name
    props: {
        href: 'https://google.com',
        target: '_blank'
    },
    children: 'Click me!'     // Text content
}
```
### 2. 🎯 The Render Function
```javascript
function customRender(reactElement, container) {
    const domElement = document.createElement(reactElement.type);
    domElement.innerHTML = reactElement.children;
    
    for (const prop in reactElement.props) {
        domElement.setAttribute(prop, reactElement.props[prop]);
    }
    container.appendChild(domElement);
}
```
3. Why JSX is Syntactic Sugar
JSX is not HTML — it's JavaScript

It gets compiled to React.createElement() calls

Those calls return objects like the one above

### 💻 Code Snippets
Full Renderer Logic
```javascript
function customRender(reactElement, container) {
    const domElement = document.createElement(reactElement.type);
    domElement.innerHTML = reactElement.children;
    
    for (const prop in reactElement.props) {
        if (prop === 'children') continue;
        domElement.setAttribute(prop, reactElement.props[prop]);
    }
    container.appendChild(domElement);
}
```
How React's createElement Works
```javascript
// What you write in JSX
<a href="https://google.com">Click me</a>

// What React sees
React.createElement('a', { href: 'https://google.com' }, 'Click me')

// What React creates (simplified)
{ type: 'a', props: { href: '...' }, children: 'Click me' }
```
### 🎯 Interview Questions
Q: What is the Virtual DOM?
A: A lightweight JavaScript representation of the real DOM. React uses it to calculate the minimal set of changes needed.

Q: What is JSX?
A: JSX is syntactic sugar for React.createElement(). It allows HTML-like syntax in JavaScript.

Q: Why can't you return multiple sibling elements in JSX?
A: JSX must return a single element. Use Fragments (<>...</>) to group siblings without adding extra DOM nodes.

## 🧠 Key Takeaway
React components are just functions that return objects describing the UI. JSX is a convenient way to write these objects.
