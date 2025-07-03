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

## CRUD Operation
```
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


