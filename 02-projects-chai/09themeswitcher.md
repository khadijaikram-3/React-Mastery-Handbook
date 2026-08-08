# 09themeswitcher — Context + Tailwind

## 📌 Project Overview
A theme switcher (Light/Dark mode) that combines Context API with Tailwind CSS.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 Tailwind Dark Mode Setup
```javascript
// tailwind.config.js
export default {
    darkMode: "class", // Important! Enables manual theme switching
    content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
}
2. 🎯 Synchronizing State with DOM
javascript
useEffect(() => {
    const html = document.querySelector('html');
    html.classList.remove("light", "dark");
    html.classList.add(themeMode);
}, [themeMode]);
3. Production-Style Context Pattern
javascript
// theme.js — single file for context, provider, and hook
export const ThemeContext = createContext({
    themeMode: "light",
    darkTheme: () => {},
    lightTheme: () => {},
});

export const ThemeProvider = ThemeContext.Provider;

export default function useTheme() {
    return useContext(ThemeContext);
}
```
💻 Code Snippets
Context Definition
javascript
import { createContext, useContext } from "react";

export const ThemeContext = createContext({
    themeMode: "light",
    darkTheme: () => {},
    lightTheme: () => {},
});

export const ThemeProvider = ThemeContext.Provider;

export default function useTheme() {
    return useContext(ThemeContext);
}
Using the Hook in a Component
javascript
import useTheme from "../context/theme";

export default function ThemeBtn() {
    const { themeMode, lightTheme, darkTheme } = useTheme();

    const onChangeBtn = (e) => {
        const darkModeStatus = e.currentTarget.checked;
        if (darkModeStatus) darkTheme();
        else lightTheme();
    };

    return <input type="checkbox" onChange={onChangeBtn} checked={themeMode === "dark"} />;
}

```
🎯 Interview Questions
Q: Why set darkMode: "class" in Tailwind config?
A: It tells Tailwind to look for the dark class on the HTML element, allowing manual theme switching.

Q: Why use useEffect to add/remove classes?
A: useEffect synchronizes React state with the browser DOM, which is not controlled by React.

Q: What's the advantage of a custom hook like useTheme?
A: It simplifies consumption — components only need one import instead of two (Context + useContext).

🧠 Key Takeaway
Context + Tailwind works seamlessly when darkMode: "class" is configured. useEffect bridges React state and DOM manipulation.
