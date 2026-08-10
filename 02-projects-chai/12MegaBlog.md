# 12MegaBlog — Full Stack CRUD

## 📌 Project Overview
A full-stack blog application that implements **CRUD operations** with authentication and database integration.

## 🎯 Key Concepts (Interview Ready)

### 1. 🎯 CRUD Operations in React
| Operation | Method | Description |
|-----------|--------|-------------|
| **Create** | POST | Add new blog post |
| **Read** | GET | Fetch all posts or single post |
| **Update** | PUT/PATCH | Edit existing post |
| **Delete** | DELETE | Remove a post |

### 2. 🎯 Authentication Flow
- User registration and login
- Token-based authentication (JWT)
- Protected routes for authenticated users
- Role-based access control

### 3. 🎯 API Integration with Axios
```javascript
import axios from 'axios'

const api = axios.create({
    baseURL: process.env.REACT_APP_API_URL,
    headers: {
        'Authorization': `Bearer ${token}`
    }
})
```
### 4. 🎯 File Upload with Appwrite
Upload images to cloud storage

Associate images with blog posts

Display images in posts

### 💻 Code Snippets
Creating a Post
```javascript
const createPost = async (data) => {
    const response = await api.post('/posts', data)
    return response.data
}
```
# Reading Posts
```javascript
const getPosts = async () => {
    const response = await api.get('/posts')
    return response.data
}
Updating a Post
javascript
const updatePost = async (id, data) => {
    const response = await api.put(`/posts/${id}`, data)
    return response.data
}
```
# Deleting a Post
```javascript
const deletePost = async (id) => {
    const response = await api.delete(`/posts/${id}`)
    return response.data
}
```
### 🎯 Interview Questions
Q: What are CRUD operations?
A: Create, Read, Update, Delete — the four basic operations for persistent storage.

Q: How do you handle authentication in React?
A: Use JWT tokens stored in localStorage or cookies. Include token in API request headers.

Q: What is a protected route?
A: A route that only authenticated users can access. Redirects to login if unauthenticated.

# 🧠 Key Takeaway
Full-stack React apps involve CRUD operations, authentication, and API integration.
