# 04bgChanger — Dynamic Styling

## 📌 Project Overview
A full-screen background color switcher that demonstrates **state** and **event handling** in React.

## 🎯 Key Concepts (Interview Ready)

### 1. Inline Styles in React
- 🎯 Use **camelCase** for CSS properties (e.g., `backgroundColor`, not `background-color`)
- Pass a JavaScript object to `style` attribute

```javascript
// ✅ Correct
<div style={{ backgroundColor: color }}>
// ❌ Wrong
<div style="background-color: red">
2. 🎯 Event Handling
javascript
// ❌ This executes immediately on render!
<button onClick={setColor("red")}>

// ✅ This executes only when clicked
<button onClick={() => setColor("red")}>
```
### 3. State-Driven UI
The UI is a function of state

Change state → UI updates automatically

💻 Code Snippets
State Initialization
```javascript
const [color, setColor] = useState("olive")
Dynamic Styling
javascript
<div 
    className="w-full h-screen duration-200"
    style={{ backgroundColor: color }}
>
Button with Correct Event Handling
javascript
<button
    onClick={() => setColor("red")}
    className="outline-none px-4 py-1 rounded-full text-white"
    style={{ backgroundColor: "red" }}
>
    Red
</button>
```
##  Interview Questions
Q: Why do we wrap setColor in an arrow function?
A: Without it, the function executes immediately during render, causing an infinite loop.

Q: What's the difference between onClick={setColor} and onClick={() => setColor("red")}?
A: onClick={setColor} passes a function reference. onClick={() => setColor("red")} calls the function with an argument.

# Key Takeaway
State controls the UI. To change the UI, update the state — React handles the DOM updates.
