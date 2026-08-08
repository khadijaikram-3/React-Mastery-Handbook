# 07reactRouter — React Router

## 📌 Project Overview
Learn how to build multi-page experiences in a Single Page Application using React Router.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 React Router Setup
```javascript
// main.jsx
const router = createBrowserRouter(
    createRoutesFromElements(
        <Route path='/' element={<Layout />}>
            <Route path='' element={<Home />} />
            <Route path='about' element={<About />} />
            <Route path='user/:userid' element={<User />} />
        </Route>
    )
)

ReactDOM.createRoot(document.getElementById('root')).render(
    <RouterProvider router={router} />
)
```
### 2. 🎯 Nested Routing with Outlet
Outlet acts as a placeholder for child routes

Layout component contains shared elements (Header, Footer)

## 3. 🎯 Link vs NavLink
Link: Navigates without page reload

NavLink: Same as Link + adds isActive state for styling

```javascript
import { NavLink } from 'react-router-dom'

<NavLink 
    to="/about"
    className={({ isActive }) => 
        isActive ? "text-orange-700" : "text-gray-700"
    }
>
    About
</NavLink>
```
## 4. 🎯 useParams (Dynamic URLs)
```javascript
import { useParams } from 'react-router-dom'

function User() {
    const { userid } = useParams() // Captures :userid from URL
    return <div>User: {userid}</div>
}
```
###  Interview Questions
Q: What is the difference between <Link> and <a>?
A: <Link> prevents full page reload (SPA behavior). <a> causes a full page refresh.

Q: What is the Outlet component used for?
A: It's a placeholder where nested routes render. Used in layout components.

Q: What are loaders in React Router?
A: They fetch data before rendering the route, improving performance and user experience.

# Key Takeaway
React Router enables multi-page navigation in SPAs. Nested routes with Outlet create consistent layouts.
