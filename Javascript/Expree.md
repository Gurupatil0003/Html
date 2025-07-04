# Express

###  index.js
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


##Registeratio for placement

```
<!DOCTYPE html>
<html>
<head>
  <title>Placement Registration Form</title>
</head>
<body>
  <h2>Register for Placement</h2>

  <form action="/register" method="POST">
    <!-- Basic Details -->
    <label>Full Name:</label><br>
    <input type="text" name="name" placeholder="Your name" required><br><br>

    <label>Email:</label><br>
    <input type="email" name="email" placeholder="Your email" required><br><br>

    <label>Branch:</label><br>
    <input type="text" name="branch" placeholder="Your branch" required><br><br>

    <label>CGPA:</label><br>
    <input type="number" name="cgpa" step="0.01" placeholder="Your CGPA" required><br><br>

    <!-- Gender (Radio Buttons) -->
    <label>Gender:</label><br>
    <input type="radio" name="gender" value="Male" required> Male<br>
    <input type="radio" name="gender" value="Female"> Female<br>
    <input type="radio" name="gender" value="Other"> Other<br><br>

    <!-- Skills (Checkboxes) -->
    <label>Skills:</label><br>
    <input type="checkbox" name="skills" value="C"> C<br>
    <input type="checkbox" name="skills" value="Java"> Java<br>
    <input type="checkbox" name="skills" value="Python"> Python<br>
    <input type="checkbox" name="skills" value="JavaScript"> JavaScript<br><br>

    <!-- Year Dropdown -->
    <label>Year of Study:</label><br>
    <select name="year" required>
      <option value="">Select year</option>
      <option value="1st">1st Year</option>
      <option value="2nd">2nd Year</option>
      <option value="3rd">3rd Year</option>
      <option value="4th">4th Year</option>
    </select><br><br>

    <!-- Resume Upload (Optional) -->
    <label>Upload Resume (optional):</label><br>
    <input type="file" name="resume"><br><br>

    <!-- Terms & Conditions -->
    <input type="checkbox" name="agree" required>
    I agree to the placement terms and conditions.<br><br>

    <!-- Submit Button -->
    <button type="submit">Register</button>
  </form>
</body>
</html>



```


```js
// index.js
import express from 'express';
import path from 'path';
import { fileURLToPath } from 'url';
import { dirname } from 'path';

const app = express();
const PORT = 3000;

// Fix __dirname in ES Module
const __filename = fileURLToPath(import.meta.url);
const __dirname = dirname(__filename);

// Middleware to parse POST data
app.use(express.urlencoded({ extended: true }));

// Serve static files from "public" folder
app.use(express.static(path.join(__dirname, 'public')));

// Route to serve form.html from public folder
app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'form.html'));
});

// Handle POST request from form
app.post('/register', (req, res) => {
  const { name, email, branch, cgpa } = req.body;

  console.log('📝 Student Registered:');
  console.log({ name, email, branch, cgpa });

  res.send(`<h3>✅ Thank you ${name}, registration complete!</h3>`);
});

// Start server
app.listen(PORT, () => {
  console.log(`🚀 Server running at http://localhost:${PORT}`);
});



```


# Placement Cell

### a.js
```js

import express from "express";
import bodyParser from "body-parser";
import path from "path";
import { fileURLToPath } from "url";

const app = express();
const port = 3000;

// Needed to resolve __dirname in ES modules
const __filename = fileURLToPath(import.meta.url);
const __dirname = path.dirname(__filename);

// Middleware
app.use(bodyParser.urlencoded({ extended: true }));
app.use(express.static(path.join(__dirname, "public")));

let students = [];
let companies = [];
let offers = [];

// Routes

app.get("/", (req, res) => {
  res.sendFile(path.join(__dirname, "views", "index.html"));
});

app.get("/student-register", (req, res) => {
  res.sendFile(path.join(__dirname, "views", "student-register.html"));
});

app.post("/student-register", (req, res) => {
  const { name, branch, cgpa } = req.body;
  students.push({ name, branch, cgpa });
  res.redirect("/students");
});

app.get("/students", (req, res) => {
  res.sendFile(path.join(__dirname, "views", "student-list.html"));
});

app.get("/students-data", (req, res) => {
  res.json(students);
});

app.get("/company", (req, res) => {
  res.sendFile(path.join(__dirname, "views", "company.html"));
});

app.post("/company", (req, res) => {
  const { cname, role, salary } = req.body;
  companies.push({ cname, role, salary });
  offers.push({ cname, role, salary });
  res.redirect("/offers");
});

app.get("/offers", (req, res) => {
  res.sendFile(path.join(__dirname, "views", "offers.html"));
});

app.get("/offers-data", (req, res) => {
  res.json(offers);
});

app.listen(port, () => {
  console.log(`Placement Cell running at http://localhost:${port}`);
});



```


## Index.html
```js

<!DOCTYPE html>
<html>
<head>
  <title>Placement Cell</title>
  <link rel="stylesheet" href="/style.css">
</head>
<body>
  <h1>Welcome to Placement Cell</h1>
  <a href="/student-register">Register Student</a>
  <a href="/students">View Students</a>
  <a href="/company">Register Company</a>
  <a href="/offers">Placement Offers</a>
</body>
</html>


```


## student-register.html
```js

<!DOCTYPE html>
<html>
<head>
  <title>Student Registration</title>
</head>
<body>
  <h2>Register Student</h2>
  <form action="/student-register" method="POST">
    <input type="text" name="name" placeholder="Name" required><br>
    <input type="text" name="branch" placeholder="Branch" required><br>
    <input type="number" step="0.01" name="cgpa" placeholder="CGPA" required><br>
    <button type="submit">Register</button>
  </form>
  <a href="/">Back to Home</a>
</body>
</html>


```


## student-list.html
```js

<!DOCTYPE html>
<html>
<head>
  <title>Student List</title>
</head>
<body>
  <h2>Registered Students</h2>
  <ul>
    <!-- This will be dynamically filled using Express in next version -->
    <script>
      fetch('/students-data').then(res => res.json()).then(data => {
        document.write('<ul>');
        data.forEach(s => {
          document.write(`<li>${s.name} - ${s.branch} - ${s.cgpa}</li>`);
        });
        document.write('</ul>');
      });
    </script>
  </ul>
  <a href="/">Back</a>
</body>
</html>


```


# company.html
```
<!DOCTYPE html>
<html>
<head>
  <title>Register Company</title>
</head>
<body>
  <h2>Company Registration</h2>
  <form action="/company" method="POST">
    <input type="text" name="cname" placeholder="Company Name" required><br>
    <input type="text" name="role" placeholder="Job Role" required><br>
    <input type="number" name="salary" placeholder="Salary (in LPA)" required><br>
    <button type="submit">Submit</button>
  </form>
  <a href="/">Back to Home</a>
</body>
</html>


```

## offers.html
```js
<!DOCTYPE html>
<html>
<head>
  <title>Placement Offers</title>
</head>
<body>
  <h2>Latest Placement Offers</h2>
  <script>
    fetch('/offers-data').then(res => res.json()).then(data => {
      document.write('<ul>');
      data.forEach(o => {
        document.write(`<li>${o.cname} - ${o.role} - ₹${o.salary} LPA</li>`);
      });
      document.write('</ul>');
    });
  </script>
  <a href="/">Back</a>
</body>
</html>



```



## code Main

### form.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <form action="/submit" method="post">
    <input type="text" name="name"> 
    <input type="text" name="email">
    <button type="submit">button</button>
  </form>
  
</body>
</html>

```
### Form.js
```js
import express from 'express';
import path from 'path'
import { fileURLToPath } from 'url';

const port=3000;
const app=express()

// Setup __dirname for ES modules
const __filename = fileURLToPath(import.meta.url);
const __dirname = path.dirname(__filename);

// Middleware
app.use(express.urlencoded({ extended: true }));
app.use(express.static(path.join(__dirname, 'public')));

app.use(express.json());


app.get ('/',(req,res)=>{
  res.send("hello")
});

app.post('/submit',(req,res)=>{
  const {name,email}=req.body;
  console.log({name} , {email})
  res.send(`<h2> thnaks ${name} (${email})`)

});

app.listen(port,()=>{
  console.log(`server http://localhost:${port}/form.html`);

});

```

## placement Registaration
```js
app.post('/register', (req, res) => {
  const { name, email, branch, cgpa } = req.body;

  console.log('📝 Student Registered:');
  console.log({ name, email, branch, cgpa });

  res.send(`<h3>✅ Thank you ${name}, registration complete!</h3>`);
});
```
