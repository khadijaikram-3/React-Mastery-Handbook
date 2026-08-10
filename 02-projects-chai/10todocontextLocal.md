# 10todocontextLocal — Context + localStorage

## 📌 Project Overview
A full Todo application combining Context API for state management and localStorage for data persistence.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 localStorage with React
- **String only:** `localStorage` stores only strings
- **JSON methods:** Use `JSON.stringify()` to save, `JSON.parse()` to retrieve

### 2. 🎯 Two useEffect Hooks Pattern
```javascript
// On mount — load from localStorage
useEffect(() => {
    const todos = JSON.parse(localStorage.getItem("todos"))
    if (todos && todos.length > 0) {
        setTodos(todos)
    }
}, [])

// On state change — save to localStorage
useEffect(() => {
    localStorage.setItem("todos", JSON.stringify(todos))
}, [todos])
```

### 3. 🎯 CRUD Operations in React
Create (Add)

```javascript
const addTodo = (todo) => {
    setTodos((prev) => [{ id: Date.now(), todo, completed: false }, ...prev])
}
```
Read (Display)

```javascript
todos.map(todo => <TodoItem key={todo.id} todo={todo} />)
Update (Edit/Toggle)

javascript
const updateTodo = (id, newTodo) => {
    setTodos((prev) => prev.map(todo => 
        todo.id === id ? { ...todo, todo: newTodo } : todo
    ))
}

const toggleComplete = (id) => {
    setTodos((prev) => prev.map(todo => 
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
    ))
}
```
Delete

```javascript
const deleteTodo = (id) => {
    setTodos((prev) => prev.filter(todo => todo.id !== id))
}
```
### 💻 Code Snippets
Context Definition
```javascript
export const TodoContext = createContext({
    todos: [],
    addTodo: (todo) => {},
    updateTodo: (id, todo) => {},
    deleteTodo: (id) => {},
    toggleComplete: (id) => {}
})
```
### 🎯 Interview Questions
Q: Why use JSON.stringify() with localStorage?
A: localStorage only stores strings. JSON.stringify converts arrays/objects to strings.

Q: Why use prev in setTodos?
A: Ensures you're working with the most recent state, especially important for multiple updates.

Q: What's the difference between .map() and .filter()?
A: .map() transforms each element. .filter() returns a new array with elements that pass a condition.

# 🧠 Key Takeaway
Context + localStorage = persistent global state. CRUD operations in React use immutable patterns with map, filter, and spread operators.
