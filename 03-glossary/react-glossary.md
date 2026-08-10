
# React Glossary

## 🎯 Core Concepts

| Term | Definition |
|------|------------|
| **React** | A JavaScript library for building user interfaces |
| **JSX** | JavaScript XML — HTML-like syntax in JavaScript |
| **Component** | A function that returns JSX |
| **Props** | Read-only data passed from parent to child |
| **State** | Mutable data that triggers re-renders when changed |
| **Hook** | A function that "hooks into" React features (e.g., useState) |

## 🎯 Hooks

| Hook | Purpose |
|------|---------|
| `useState` | Manages local component state |
| `useEffect` | Handles side effects (API calls, DOM updates) |
| `useContext` | Accesses Context API data |
| `useRef` | Provides direct DOM access without re-renders |
| `useCallback` | Memoizes functions to prevent unnecessary re-renders |
| `useMemo` | Memoizes values to optimize performance |
| `useReducer` | Manages complex state logic |
| `useId` | Generates unique IDs for accessibility |

## 🎯 API & Architecture

| Term | Definition |
|------|------------|
| **Virtual DOM** | Lightweight copy of the real DOM for efficient updates |
| **Reconciliation** | Process of comparing Virtual DOM with real DOM |
| **Fiber** | React's reconciliation engine |
| **SPA** | Single Page Application — one HTML file |
| **Prop Drilling** | Passing props through unnecessary components |
| **Context API** | React's built-in global state management |
| **Custom Hook** | A hook you create to reuse stateful logic |

## 🎯 Performance

| Term | Definition |
|------|------------|
| **Memoization** | Caching results to avoid recalculating |
| **Lazy Loading** | Loading components only when needed |
| **Code Splitting** | Breaking code into smaller chunks |
| **Batching** | React grouping multiple state updates |

## 🎯 Common Patterns

| Pattern | Description |
|---------|-------------|
| **Controlled Component** | Input controlled by React state |
| **Uncontrolled Component** | Input controlled by DOM |
| **Derived State** | Values calculated from existing state |
| **Lazy Initialization** | `useState(() => expensive())` — runs once |
| **Fragment** | `<>...</>` — groups children without extra DOM nodes |
