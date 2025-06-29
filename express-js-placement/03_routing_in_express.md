# 03. Routing in Express.js

## What is Routing?

Routing refers to how an application’s endpoints (URIs) respond to client requests. In Express, routes define how your server handles different HTTP methods and paths.

---

## Basic Route Syntax

```javascript
app.METHOD(PATH, HANDLER)
```
- **METHOD:** HTTP method (GET, POST, PUT, DELETE, etc.)
- **PATH:** URL path (e.g., '/', '/users')
- **HANDLER:** Function with `req` (request) and `res` (response) objects

---

## Examples

### 1. GET Route

```javascript
app.get('/', (req, res) => {
  res.send('Home Page');
});
```

### 2. POST Route

```javascript
app.post('/submit', (req, res) => {
  res.send('Form Submitted');
});
```

### 3. Route with Parameters

```javascript
app.get('/user/:id', (req, res) => {
  res.send(`User ID: ${req.params.id}`);
});
```
- Access route parameters via `req.params`

### 4. Route with Query Parameters

```javascript
app.get('/search', (req, res) => {
  const query = req.query.q;
  res.send(`Search Query: ${query}`);
});
```
- Access query parameters via `req.query`

---

## Real-World Example: Greeting Route

```javascript
app.get('/greet/:name', (req, res) => {
  res.send(`Hello, ${req.params.name}!`);
});
```
- Visiting `/greet/Satyam` responds with `Hello, Satyam!`

---

## Grouping Routes (Router)

For larger apps, use the Express Router:

```javascript
const express = require('express');
const router = express.Router();

router.get('/profile', (req, res) => {
  res.send('User Profile');
});

app.use('/user', router);
// Now '/user/profile' is handled by the router
```

---

## Interview Questions

### 1. How do you define a route in Express.js?
**Answer:**  
Using `app.METHOD(PATH, HANDLER)`, e.g., `app.get('/about', handlerFunction)`.

---

### 2. What is the difference between route parameters and query parameters?
**Answer:**  
Route parameters are part of the URL path (e.g., `/user/:id`), while query parameters are key-value pairs in the URL after `?` (e.g., `/search?q=term`).

---

### 3. How can you organize routes in a large Express application?
**Answer:**  
By using the Express Router to modularize routes into separate files.

---

### 4. How do you handle 404 (Not Found) routes?
**Answer:**  
Add a catch-all route at the end:
```javascript
app.use((req, res) => {
  res.status(404).send('Page Not Found');
});
```

---

**Next:** [04_middleware.md](./04_middleware.md)