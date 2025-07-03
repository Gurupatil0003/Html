# Express

// index.js
```js
import express from 'express';

const app = express();
const port = 3000;

// Route
app.get('/', (req, res) => {
  res.send('Hello, Express!');
});

// Start the server
app.listen(port, () => {
  console.log(`Server is running at http://localhost:${port}`);
});

```


```

// app.js
import express from 'express';

const app = express();
const PORT = 3000;

// To handle JSON input
app.use(express.json());

// GET route
app.get('/', (req, res) => {
  res.send('Hello GURANNA! Welcome to your first API 🎉');
});

// Simple POST route
app.post('/hello', (req, res) => {
  const { name } = req.body;
  res.send(`Hello ${name}! You just hit a POST API 🎯`);
});

// Start server
app.listen(PORT, () => {
  console.log(`✅ Server running at http://localhost:${PORT}`);
});
```

## CRUD Operation
```js
import express from 'express';

const app = express();
const port = 3000;

app.use(express.json());

// 🧪 Dummy in-memory data
let users = [
  {
    id: 1,
    name: 'Mounesh Goud',
    email: 'mounesh@example.com'
  }
];

let nextId = 2; // since 1 is already used

// ➕ Create - POST /users
app.post('/users', (req, res) => {
  const { name, email } = req.body;
  const newUser = { id: nextId++, name, email };
  users.push(newUser);
  res.status(201).json(newUser);
});

// 📥 Read All - GET /users
app.get('/users', (req, res) => {
  res.json(users);
});

// 📥 Read One - GET /users/:id
app.get('/users/:id', (req, res) => {
  const user = users.find(u => u.id === parseInt(req.params.id));
  if (!user) return res.status(404).json({ message: 'User not found' });
  res.json(user);
});

// ✏️ Update - PUT /users/:id
app.put('/users/:id', (req, res) => {
  const user = users.find(u => u.id === parseInt(req.params.id));
  if (!user) return res.status(404).json({ message: 'User not found' });

  const { name, email } = req.body;
  if (name) user.name = name;
  if (email) user.email = email;

  res.json(user);
});

// ❌ Delete - DELETE /users/:id
app.delete('/users/:id', (req, res) => {
  const index = users.findIndex(u => u.id === parseInt(req.params.id));
  if (index === -1) return res.status(404).json({ message: 'User not found' });

  const deletedUser = users.splice(index, 1)[0];
  res.json(deletedUser);
});

// Start server
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
```


## DataBase

```js
<!DOCTYPE html>
<html>
<head>
  <title>Simple Form</title>
</head>
<body>
  <h2>Submit Your Info</h2>
  <form action="/submit" method="POST">
    <label>Name:</label>
    <input type="text" name="name" required><br><br>

    <label>Email:</label>
    <input type="email" name="email" required><br><br>

    <button type="submit">Submit</button>
  </form>
</body>
</html>



```

## 
```js
import express from 'express';
import path from 'path';
import { fileURLToPath } from 'url';
import sqlite3 from 'sqlite3';
import { open } from 'sqlite';

const __filename = fileURLToPath(import.meta.url);
const __dirname = path.dirname(__filename);

const app = express();
const PORT = 3000;

// Middleware
app.use(express.urlencoded({ extended: true }));
app.use(express.static(path.join(__dirname, 'public')));

// SQLite database setup
let db;
const initDB = async () => {
  db = await open({
    filename: './database.db',
    driver: sqlite3.Database,
  });

  await db.run(`
    CREATE TABLE IF NOT EXISTS users (
      id INTEGER PRIMARY KEY AUTOINCREMENT,
      name TEXT NOT NULL,
      email TEXT NOT NULL
    )
  `);
};

// Routes
app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'form.html'));
});

app.post('/submit', async (req, res) => {
  const { name, email } = req.body;
  await db.run('INSERT INTO users (name, email) VALUES (?, ?)', [name, email]);
  res.send('<h2>✅ Data Saved! <a href="/">Go Back</a></h2>');
});

// Start the server
app.listen(PORT, async () => {
  await initDB();
  console.log(`🚀 Server running at http://localhost:${PORT}`);
});
```





