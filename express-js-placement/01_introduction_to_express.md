# 01. Introduction to Express.js

## What is Express.js?

Express.js is a minimal and flexible Node.js web application framework that provides a robust set of features for building web and mobile applications. It simplifies the process of creating server-side applications with Node.js by providing a higher-level API for handling HTTP requests, routing, middleware, and more.

---

## Why Use Express.js?

- **Simplicity:** Reduces boilerplate code needed to create servers in Node.js.
- **Routing:** Built-in routing system for handling different HTTP methods and URLs.
- **Middleware Support:** Easily add functionality like logging, authentication, and error handling.
- **Scalability:** Suitable for both small and large-scale applications.
- **Community & Ecosystem:** Large number of middleware and plugins available.

---

## How Does Express.js Work?

Express.js sits on top of Node.js’s HTTP module. It listens for HTTP requests, processes them using middleware and route handlers, and sends responses back to the client.

**Basic Flow:**
1. Client sends an HTTP request.
2. Express receives the request.
3. Middleware functions process the request (e.g., logging, parsing).
4. Route handler sends a response.

---

## Real-World Use Cases

- RESTful APIs (e.g., for mobile apps)
- Single Page Applications (SPAs) backend
- Server-side rendering for web apps
- Proxies and gateways (API Gateway)
- Microservices

---

## Simple Example

```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello, Express!');
});

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

---

## Key Features

- **Routing:** Handle different HTTP methods and URLs.
- **Middleware:** Functions that execute during the request-response cycle.
- **Template Engines:** Support for rendering dynamic HTML.
- **Error Handling:** Centralized error management.
- **Serving Static Files:** Easily serve images, CSS, JS, etc.

---

## Interview Questions

### 1. What is Express.js and why is it used?
**Answer:**  
Express.js is a web application framework for Node.js that simplifies the process of building web servers and APIs. It is used because it provides a simple interface for routing, middleware, and HTTP utilities, making server-side development faster and more organized.

---

### 2. How is Express.js different from Node.js?
**Answer:**  
Node.js is a runtime environment for executing JavaScript on the server, while Express.js is a framework built on top of Node.js to simplify web application development by providing higher-level abstractions for routing, middleware, and more.

---

### 3. What are some real-world applications of Express.js?
**Answer:**  
- RESTful APIs for web/mobile apps
- Backend for single-page applications
- Microservices
- Proxies and API gateways

---

### 4. What are the core features of Express.js?
**Answer:**  
Routing, middleware support, template engine integration, error handling, and static file serving.

---

### 5. Can you explain the request-response cycle in Express.js?
**Answer:**  
When a client sends a request, Express processes it through a series of middleware functions and route handlers, then sends a response back to the client.

---

**Next:** [02_setting_up_express.md](./02_setting_up_express.md)