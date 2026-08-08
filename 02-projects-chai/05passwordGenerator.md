# 05passwordGenerator — useCallback & useRef

## 📌 Project Overview
A dynamic password generator that teaches **performance optimization** and **DOM access**.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 useCallback (Memoization)
- **Purpose:** Prevents unnecessary re-creation of functions on every render
- **When to use:** When a function is used as a dependency in `useEffect` or passed to child components
- **Syntax:** `useCallback(callback, [dependencies])`

```javascript
const passwordGenerator = useCallback(() => {
    // Function logic here
}, [length, numberAllowed, charAllowed])
```
### 2. 🎯 useRef (DOM Access)
Purpose: Access DOM nodes directly without causing re-renders

Common use cases: Focus management, text selection, measuring elements

```javascript
const passwordRef = useRef(null);

// Later: focus or select text
passwordRef.current?.select();
```
### 3. useEffect with Dependencies
🎯 Empty array [] → runs only once on mount

With dependencies → runs when dependencies change

No array → runs on every render (avoid if possible)

##  Code Snippets
## useCallback Generator
```javascript
const passwordGenerator = useCallback(() => {
    let pass = "";
    let str = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
    if (numberAllowed) str += "0123456789";
    if (charAllowed) str += "!@#$%^&*-_+=[]{}~`";

    for (let i = 1; i <= length; i++) {
        let charIndex = Math.floor(Math.random() * str.length + 1);
        pass += str.charAt(charIndex);
    }
    setPassword(pass);
}, [length, numberAllowed, charAllowed, setPassword]);
```
## Copy to Clipboard
```javascript
const passwordRef = useRef(null);

const copyPasswordToClipboard = useCallback(() => {
    passwordRef.current?.select(); // Visual feedback
    window.navigator.clipboard.writeText(password);
}, [password]);

// In JSX
<input ref={passwordRef} value={password} readOnly />
<button onClick={copyPasswordToClipboard}>Copy</button>
```
## Interview Questions
Q: What does useCallback do?
A: It memoizes a function, preventing it from being recreated on every render. Useful when passing functions to child components or as useEffect dependencies.

Q: What is the difference between useRef and useState?
A: useRef doesn't trigger re-renders when updated. useState triggers re-renders.

Q: Why use useEffect with [passwordGenerator] as a dependency?
A: The generator function changes when its dependencies change, so we want the effect to re-run when the generator changes.

# Key Takeaway
useCallback optimizes performance by memoizing functions. useRef provides direct DOM access without causing re-renders.
