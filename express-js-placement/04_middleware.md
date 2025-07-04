# 04. Middleware in Express.js

## What is Middleware?

Middleware are functions that execute during the request-response cycle. They have access to the request (`req`) and response (`res`) objects, and the `next()` function, which passes control to the next middleware.

**Middleware can:**
- Execute code
- Modify the request and response objects
- End the request-response cycle
- Call the next middleware in the stack

---

## Types of Middleware

1. **Application-level middleware:** Bound to an instance of `express()`.
2. **Router-level middleware:** Bound to an instance of `express.Router()`.
3. **Error-handling middleware:** Has four arguments: `(err, req, res, next)`.
4. **Built-in middleware:** Provided by Express (e.g., `express.json()`).
5. **Third-party middleware:** Installed via npm (e.g., `morgan`, `cors`).

---

## Application-Level Middleware Example

```javascript
// Logging middleware
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next(); // Pass control to the next middleware
});
```

---

## Built-in Middleware Example

```javascript
app.use(express.json()); // Parses incoming JSON requests
app.use(express.urlencoded({ extended: true })); // Parses URL-encoded bodies
```

---

## Third-Party Middleware Example

```javascript
const morgan = require('morgan');
app.use(morgan('dev')); // Logs HTTP requests
```

---

## Error-Handling Middleware Example

```javascript
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```
- Must have four parameters to be recognized as error-handling middleware.

---

## Real-World Example: Authentication Middleware

```javascript
function isAuthenticated(req, res, next) {
  if (req.headers.authorization === 'secret-token') {
    next();
  } else {
    res.status(401).send('Unauthorized');
  }
}

app.get('/protected', isAuthenticated, (req, res) => {
  res.send('This is a protected route.');
});
```

---

## Interview Questions

### 1. What is middleware in Express.js?
**Answer:**  
Functions that have access to the request and response objects and can modify them, end the request-response cycle, or pass control to the next middleware.

---

### 2. How do you use multiple middleware functions for a single route?
**Answer:**  
Pass them as arguments:
```javascript
app.get('/route', middleware1, middleware2, handler);
```

---

### 3. What is the difference between application-level and router-level middleware?
**Answer:**  
Application-level middleware is bound to the app instance, while router-level middleware is bound to an Express Router instance.

---

### 4. How do you handle errors in middleware?
**Answer:**  
By defining middleware with four parameters: `(err, req, res, next)`.

---

**Next:** [05_handling_post_data.md](./05_handling_post_data.md)