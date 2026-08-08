# 03tailwindprops — Props + Tailwind CSS

## 📌 Project Overview
Learn how to make components **reusable** using Props and style them with Tailwind CSS.

## 🎯 Key Concepts (Interview Ready)

### 1. Props (Properties)
- 🎯 **Read-only (immutable)** — child cannot modify props
- Passed from parent to child like HTML attributes
- Data flows **downward** (one-way data flow)

### 2. 🎯 Destructuring Props
```javascript
// Without destructuring
function Card(props) {
    return <h1>{props.username}</h1>
}

// With destructuring (cleaner)
function Card({ username, btnText = "Visit Me" }) {
    return <h1>{username}</h1>
}
```
### 3. 🎯 Default Props
```javascript
function Card({ username, btnText = "Visit Me" }) {
    // btnText defaults to "Visit Me" if not provided
}
```
## 4. Tailwind CSS Integration
Add className instead of class

🎯 Tailwind utility classes: p-4, bg-black, text-white, etc.

💻 Code Snippets
Parent Component Passing Props
```javascript
import Card from './components/Card'

function App() {
    return (
        <>
            <Card username="Chai aur Code" btnText="Click Me" />
            <Card username="Hitesh" />  {/* btnText defaults */}
        </>
    )
}
```
## Child Component Receiving Props
```javascript

function Card({ username, btnText = "Visit Me" }) {
    return (
        <div className="max-w-xs rounded-md shadow-md bg-black text-white">
            <h1 className="text-lg font-semibold">{username}</h1>
            <button className="mt-2 inline-flex cursor-pointer items-center text-sm font-semibold">
                {btnText}
            </button>
        </div>
    )
}
``` 
# 🎯 Interview Questions
Q: Are props mutable?
A: No, props are read-only. A child component cannot modify the props it receives.

Q: How do you pass data from child to parent?
A: You pass a callback function as a prop from parent to child, and the child calls it with data.

Q: Why use className instead of class?
A: class is a reserved keyword in JavaScript. React uses className to avoid conflicts.

# Key Takeaway
Props make components reusable. A component should be configured by its props, not modify them.
