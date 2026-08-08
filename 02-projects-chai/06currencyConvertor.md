# 06currencyConvertor — Custom Hooks

## 📌 Project Overview
A real-world currency converter that teaches **custom hooks**, **API integration**, and **component reusability**.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 Custom Hooks
- **Purpose:** Extract and reuse stateful logic
- **Naming Convention:** Must start with "use" (e.g., `useCurrencyInfo`)
- Benefits: Cleaner components, reusable logic, easier testing

### 2. API Integration with useEffect
```javascript
function useCurrencyInfo(currency) {
    const [data, setData] = useState({})
    useEffect(() => {
        fetch(`https://api.example.com/${currency}`)
            .then(res => res.json())
            .then(res => setData(res))
    }, [currency]) // Re-fetch when currency changes
    return data
}
```
## 3. 🎯 The useId Hook (Accessibility)
Generates unique IDs for linking inputs and labels

Prevents ID collisions in large applications

### Code Snippets
Custom Hook
```javascript
function useCurrencyInfo(currency) {
    const [data, setData] = useState({})
    useEffect(() => {
        fetch(`https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/latest/currencies/${currency}.json`)
        .then((res) => res.json())
        .then((res) => setData(res[currency]))
    }, [currency])
    return data
}
```
## Reusable Input Component
```javascript
function InputBox({ label, amount, onAmountChange, currencyOptions }) {
    const id = useId(); // Unique ID for accessibility
    return (
        <div>
            <label htmlFor={id}>{label}</label>
            <input 
                id={id}
                type="number"
                value={amount}
                onChange={(e) => onAmountChange(Number(e.target.value))}
            />
            <select>{/* Options */}</select>
        </div>
    )
}
```
###  Interview Questions
Q: What is a custom hook?
A: A function that starts with "use" and can call other hooks. It allows you to extract and reuse stateful logic.

Q: Why use useId?
A: It generates a unique, stable ID for accessibility, ensuring labels and inputs are correctly linked.

Q: How do you handle API data in React?
A: Use useEffect for the fetch, useState for storing data, and display loading/error states.

###  Key Takeaway
Custom hooks make your code more reusable and testable. They're the foundation of clean React architecture.
