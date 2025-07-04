# 05. Handling POST Data in Express.js

## Why Handle POST Data?

POST requests are used to send data from the client to the server, such as form submissions or API payloads. Express provides middleware to parse incoming data so you can access it in your route handlers.

---

## Parsing JSON Data

Use the built-in `express.json()` middleware to parse JSON bodies:

```javascript
app.use(express.json());

app.post('/api/data', (req, res) => {
  // Access data sent in the request body
  const data = req.body;
  res.json({ received: data });
});
```
- Send a POST request with JSON:  
  `{ "name": "Satyam", "age": 22 }`

---

## Parsing URL-Encoded Data

For HTML form submissions (default encoding):

```javascript
app.use(express.urlencoded({ extended: true }));

app.post('/submit-form', (req, res) => {
  // Access form fields
  const { username, password } = req.body;
  res.send(`Username: ${username}, Password: ${password}`);
});
```
- Form data is sent as `key=value&key2=value2`

---

## Real-World Example: Summing Two Numbers

```javascript
app.use(express.json());

app.post('/sum', (req, res) => {
  const { a, b } = req.body;
  if (typeof a === 'number' && typeof b === 'number') {
    res.json({ sum: a + b });
  } else {
    res.status(400).json({ error: 'Both a and b must be numbers' });
  }
});
```
- POST `{ "a": 5, "b": 7 }` to `/sum` returns `{ "sum": 12 }`

---

## Handling File Uploads

For file uploads, use third-party middleware like `multer`:

```javascript
const multer = require('multer');
const upload = multer({ dest: 'uploads/' });

app.post('/upload', upload.single('file'), (req, res) => {
  res.send(`File uploaded: ${req.file.originalname}`);
});
```

---

## Interview Questions

### 1. How do you parse JSON data in Express.js?
**Answer:**  
By using the `express.json()` middleware.

---

### 2. How do you handle form submissions in Express.js?
**Answer:**  
By using the `express.urlencoded()` middleware.

---

### 3. How can you handle file uploads in Express.js?
**Answer:**  
By using third-party middleware like `multer`.

---

### 4. What happens if you don’t use body-parsing middleware?
**Answer:**  
`req.body` will be `undefined` for POST/PUT requests with a body.

---

**Next:** [06_error_handling.md](./06_error_handling.md)