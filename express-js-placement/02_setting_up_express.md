# 02. Setting Up Express.js

## Prerequisites

- **Node.js installed:** Download from [nodejs.org](https://nodejs.org/)
- **Basic JavaScript knowledge**
- **A code editor:** (e.g., VS Code)

---

## Step 1: Initialize a New Project

Open your terminal and run:
```bash
mkdir expressjs_placement_guide
cd expressjs_placement_guide
npm init -y
```
This creates a new directory and initializes a `package.json` file.

---

## Step 2: Install Express

```bash
npm install express
```
This command adds Express as a dependency in your project.

---

## Step 3: Create Your First Express Server

Create a file named `index.js`:

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

## Step 4: Run Your Server

In the terminal, run:
```bash
node index.js
```
Visit [http://localhost:3000](http://localhost:3000) in your browser. You should see:  
`Hello, Express!`

---

## Step 5: Project Structure (Recommended)

```
expressjs_placement_guide/
│
├── index.js
├── package.json
└── node_modules/
```

As your project grows, you can add folders like `routes/`, `controllers/`, and `middleware/`.

---

## Real-World Example: Custom Welcome Route

Add a new route to your server:

```javascript
app.get('/welcome', (req, res) => {
  res.send('Welcome to Placement Prep!');
});
```
Now, visiting [http://localhost:3000/welcome](http://localhost:3000/welcome) will show your custom message.

---

## Common Interview Questions

### 1. How do you set up an Express.js project from scratch?
**Answer:**  
Initialize with `npm init`, install Express with `npm install express`, create an entry file (e.g., `index.js`), and write basic server code.

---

### 2. How do you run an Express.js server?
**Answer:**  
Use `node index.js` in the terminal after writing your server code.

---

### 3. What is the purpose of `package.json`?
**Answer:**  
It manages project metadata, scripts, and dependencies.

---

**Next:** [03_routing_in_express.md](./03_routing_in_express.md)