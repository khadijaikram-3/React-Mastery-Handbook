# 08miniContext — Context API

## 📌 Project Overview
Introduction to the Context API — React's built-in solution for **global state management**.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 The Problem: Prop Drilling
- Prop drilling = passing data through components that don't need it
- Becomes messy in large applications

### 2. 🎯 Context API Solution
Three-step pattern:
1. **Create:** `const MyContext = createContext()`
2. **Provide:** `<MyContext.Provider value={data}>`
3. **Consume:** `const data = useContext(MyContext)`

### 3. 🎯 Context vs Redux
| Context | Redux |
|---------|-------|
| Built into React | Third-party library |
| Good for small-medium apps | Better for large apps |
| Simple setup | More boilerplate |

## 💻 Code Snippets

### Creating Context
```javascript
// UserContext.js
import React from "react";
const UserContext = React.createContext();
export default UserContext;
Provider Implementation

```
```javascript
// UserContextProvider.jsx
import React, { useState } from "react";
import UserContext from "./UserContext";

const UserContextProvider = ({ children }) => {
    const [user, setUser] = useState(null);
    return (
        <UserContext.Provider value={{ user, setUser }}>
            {children}
        </UserContext.Provider>
    );
};
```
Consuming Context
```javascript
// Login.jsx
import { useContext } from "react";
import UserContext from "../context/UserContext";

function Login() {
    const { setUser } = useContext(UserContext);
    // Now you can use setUser
}
```
###  Interview Questions
Q: What is prop drilling and how do you solve it?
A: Prop drilling is passing data through intermediate components that don't need it. Solved using Context API or Redux.

Q: What is the Provider component?
A: A wrapper that "provides" data to all components nested inside it via the value prop.

Q: Context vs Redux — when to use which?
A: Context for small to medium apps with simple state. Redux for large apps with complex state and frequent updates.

## Key Takeaway
Context API provides a way to share data across the component tree without prop drilling. It's React's built-in state management solution.

text
