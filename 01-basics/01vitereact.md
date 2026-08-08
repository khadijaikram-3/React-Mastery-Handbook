
# 01vitereact — Vite Environment

## 📌 Project Overview
Introduction to Vite — a modern, fast build tool for React applications.

## 🎯 Key Concepts (Interview Ready)

### 1. Vite vs Create React App (CRA)
| Feature | Vite | CRA |
|---------|------|-----|
| Speed | ⚡ Very fast | 🐌 Slower |
| Bundle Size | Smaller | Larger |
| Configuration | Minimal | Heavy |
| 🎯 **Extension** | Requires `.jsx` | More lenient |

### 2. Why Vite Requires `.jsx`
- Vite uses native ES modules
- It needs to know which files contain JSX for proper compilation
- 🎯 Files with JSX **must** have `.jsx` extension

### 3. Script Injection Difference
- **CRA:** Uses `react-scripts` to inject bundle
- **Vite:** Uses standard `<script type="module">` tag directly in `index.html`

## 💻 Code Snippets

### Entry Point (`main.jsx`)
```javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'

ReactDOM.createRoot(document.getElementById('root')).render(<App />)

```

 ### Interview Questions
# Q: Why does Vite require .jsx extension?
A: Vite uses native ES modules and needs to identify files containing JSX for proper compilation.

# Q: What's the main advantage of Vite over CRA?
A: Vite is significantly faster and has a smaller bundle size because it uses native ES modules.

### Key Takeaway
Vite is the modern standard for React projects due to its speed and minimal configuration.
