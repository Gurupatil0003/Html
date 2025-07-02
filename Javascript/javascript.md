# 📘 JavaScript Data Types – Complete Guide

JavaScript data types are divided into **two categories**:

- ✅ **Primitive Data Types** – Immutable, stored by value
- ✅ **Non-Primitive (Reference) Data Types** – Mutable, stored by reference

---

## 📊 Data Types Table

| Data Type     | Category       | Description                                      | Example                                 | `typeof` Result | Common Operations                                           |
|---------------|----------------|--------------------------------------------------|------------------------------------------|------------------|--------------------------------------------------------------|
| **Number**    | Primitive       | Integer or floating-point numeric values         | `let x = 42;`<br>`let y = 3.14;`         | `number`         | `+`, `-`, `*`, `/`, `%`, `Math.round()`, `Math.random()`     |
| **String**    | Primitive       | Sequence of characters                           | `let name = "John";`                     | `string`         | `.length`, `.slice()`, `.replace()`, `+` for concat          |
| **Boolean**   | Primitive       | Logical value: true or false                     | `let isReady = true;`                    | `boolean`        | `&&`, `||`, `!`, used in `if`, `while`                       |
| **Undefined** | Primitive       | Declared but not assigned a value                | `let z;`                                 | `undefined`      | Check with `=== undefined`                                  |
| **Null**      | Primitive       | Intentional absence of object value              | `let a = null;`                          | `object`*        | Check with `=== null`                                       |
| **BigInt**    | Primitive       | For arbitrarily large integers                   | `let big = 12345678901234567890n;`       | `bigint`         | `+`, `-`, `*`, `/` (with `n`)                                |
| **Symbol**    | Primitive       | Unique and immutable identifier                  | `let id = Symbol("id");`                | `symbol`         | Used as unique keys, `Symbol.for()`, comparison              |
| **Object**    | Non-Primitive   | Collection of key-value pairs                    | `let obj = {name: "Alice"};`             | `object`         | `obj.key`, `Object.keys()`, `Object.values()`, modify props  |
| **Array**     | Non-Primitive   | Ordered collection (special object)              | `let arr = [1, 2, 3];`                   | `object`         | `.push()`, `.pop()`, `.map()`, `.length`, `.filter()`        |
| **Function**  | Non-Primitive   | Callable block of code                           | `function greet() {}`                   | `function`       | `()`, `.call()`, `.apply()`, `.bind()`                       |
| **NaN**       | Special Number  | Result of invalid math operation                 | `let result = 0 / "abc";`               | `number`         | `isNaN(x)`, `Number.isNaN()`                                |
| **Infinity**  | Special Number  | Mathematical Infinity                            | `let x = 1 / 0;`                         | `number`         | Comparison: `=== Infinity`, `-Infinity`                      |

> **⚠️ Note**: `typeof null` returns `"object"` — this is a known bug in JavaScript since its early days.
>  
> **🧠 Tip**: All non-primitive data types are mutable and stored by reference. Changes to them reflect across variables pointing to the same memory.

---

## ✅ Summary of Classification

```txt
Primitive:
  - Number
  - String
  - Boolean
  - Undefined
  - Null
  - BigInt
  - Symbol

Non-Primitive (Reference):
  - Object
  - Array
  - Function


```

# ⚙️ JavaScript Operators Cheat Sheet

This table covers all major JavaScript operators with clear descriptions, usage, examples, and outputs.

---

## 📚 Full JavaScript Operators Table

| Operator Type         | Operator | What It Does                                | How to Use (Syntax)       | Example                           | Output       |
|-----------------------|----------|---------------------------------------------|----------------------------|------------------------------------|--------------|
| **Arithmetic**        | `+`      | Adds two numbers or strings                 | `a + b`                   | `5 + 3`                            | `8`          |
|                       | `-`      | Subtracts right from left operand           | `a - b`                   | `10 - 4`                           | `6`          |
|                       | `*`      | Multiplies two numbers                      | `a * b`                   | `2 * 3`                            | `6`          |
|                       | `/`      | Divides left by right operand               | `a / b`                   | `10 / 2`                           | `5`          |
|                       | `%`      | Returns remainder                          | `a % b`                   | `10 % 3`                           | `1`          |
|                       | `**`     | Exponentiation (power)                      | `a ** b`                  | `2 ** 3`                           | `8`          |
| **Assignment**        | `=`      | Assigns value to variable                   | `x = y`                   | `x = 5`                            | `5`          |
|                       | `+=`     | Adds and assigns                           | `x += y`                  | `x = 3; x += 2`                    | `5`          |
|                       | `-=`     | Subtracts and assigns                      | `x -= y`                  | `x = 5; x -= 2`                    | `3`          |
|                       | `*=`     | Multiplies and assigns                     | `x *= y`                  | `x = 4; x *= 2`                    | `8`          |
|                       | `/=`     | Divides and assigns                        | `x /= y`                  | `x = 10; x /= 2`                   | `5`          |
| **Comparison**        | `==`     | Equal (loose, type-converting)             | `a == b`                  | `5 == '5'`                         | `true`       |
|                       | `===`    | Strictly equal (value + type)              | `a === b`                 | `5 === '5'`                        | `false`      |
|                       | `!=`     | Not equal (loose)                          | `a != b`                  | `5 != '5'`                         | `false`      |
|                       | `!==`    | Strict not equal                           | `a !== b`                 | `5 !== '5'`                        | `true`       |
|                       | `>`      | Greater than                               | `a > b`                   | `6 > 4`                            | `true`       |
|                       | `<`      | Less than                                  | `a < b`                   | `3 < 2`                            | `false`      |
|                       | `>=`     | Greater than or equal to                   | `a >= b`                  | `5 >= 5`                           | `true`       |
|                       | `<=`     | Less than or equal to                      | `a <= b`                  | `4 <= 6`                           | `true`       |
| **Logical**           | `&&`     | Logical AND                                | `a && b`                  | `true && false`                   | `false`      |
|                       | `||`     | Logical OR                                 | `a || b`                  | `true || false`                   | `true`       |
|                       | `!`      | Logical NOT (negation)                     | `!a`                      | `!true`                           | `false`      |
| **Bitwise**           | `&`      | Bitwise AND                                | `a & b`                   | `5 & 1`                            | `1`          |
|                       | `|`      | Bitwise OR                                 | `a | b`                   | `5 | 1`                            | `5`          |
|                       | `^`      | Bitwise XOR                                | `a ^ b`                   | `5 ^ 1`                            | `4`          |
|                       | `~`      | Bitwise NOT                                | `~a`                      | `~5`                               | `-6`         |
|                       | `<<`     | Bitwise left shift                         | `a << b`                  | `5 << 1`                           | `10`         |
|                       | `>>`     | Bitwise right shift                        | `a >> b`                  | `5 >> 1`                           | `2`          |
| **String**            | `+`      | Concatenates strings                       | `a + b`                   | `"Hello" + " JS"`                 | `"Hello JS"` |
| **Unary**             | `typeof`| Returns type of operand                    | `typeof a`                | `typeof 42`                       | `"number"`   |
|                       | `delete`| Deletes object property                    | `delete obj.key`          | `delete user.name`                | `true`       |
|                       | `++`     | Increment                                  | `a++` or `++a`            | `let a = 1; a++`                  | `2` (after)  |
|                       | `--`     | Decrement                                  | `a--` or `--a`            | `let a = 1; --a`                  | `0`          |
| **Ternary**           | `? :`    | Conditional expression                     | `cond ? val1 : val2`      | `5 > 3 ? "Yes" : "No"`            | `"Yes"`      |
| **Spread / Rest**     | `...`    | Expands / gathers array/items              | `[...arr]`, `(...args)`   | `[... [1,2]]`                     | `[1,2]`       |
| **Nullish Coalescing**| `??`     | Fallback if `null` or `undefined`         | `val ?? default`          | `null ?? "Guest"`                 | `"Guest"`     |
| **Optional Chaining** | `?.`     | Safe nested access                         | `obj?.prop`               | `user?.name`                      | `"John"` or `undefined` |
| **Membership**        | `in`     | Checks if key exists in object             | `"key" in obj`            | `"age" in user`                   | `true`        |
|                       | `instanceof`| Checks object type                    | `obj instanceof Type`     | `arr instanceof Array`            | `true`        |
| **Comma**             | `,`      | Evaluates multiple expressions             | `(x = 1, y = 2)`          | `let z = (1, 2)`                  | `2`           |

---

📝 **Tip**: Use `===` instead of `==` to avoid unexpected type coercion.


```js

b=`hello world`

console.log(b.slice(-2))
console.log(b.substring(-1))
console.log(b.includes('h'))

let str = "hello world";

str.toUpperCase();     // "HELLO WORLD"
str.toLowerCase();     // "hello world"
str.trim();            // Removes spaces from both ends
str.trimStart();       // Trims from start
str.trimEnd();         // Trims from end
str.replace("world", "JS");     // "hello JS"
str.replaceAll("l", "-");       // "he--o wor-d"
str.concat(" JS");     // "hello world JS"
str.repeat(3);         // "hello worldhello worldhello world"


// let str = "apple,banana,kiwi";

// str.split(",");   // ["apple", "banana", "kiwi"]



let a=[2,4,5,6]
a[2]=56
a.unshift(4545)
console.log(a)

a.shift()
a.pop()
console.log(a)

arr=[4,5,6,7]
console.log(arr.includes(7)) 
console.log(arr.indexOf(4))

console.log(arr)
console.log(a.length)



let ar={
    
    a:34,
    age:56,
    address:{
        city:"gg"
    }
};

ar['a']=456
console.log(ar.address.city)

delete ar.age
console.log(ar)
```



## Even or Odd


```python
<!DOCTYPE html>
<html>
<head>
  <title>Even or Odd</title>
</head>
<body>

  <h2>Check Even or Odd</h2>

  <input type="number" id="num" />
  <button onclick="checkEvenOdd()">Check</button>

  <p id="output"></p>

  <script>
    function checkEvenOdd() {
      var number = document.getElementById("num").value;
      if (number % 2 === 0) {
        document.getElementById("output").innerText = "It's Even!";
      } else {
        document.getElementById("output").innerText = "It's Odd!";
      }
    }
  </script>

</body>
</html>


```

## Alert

```js
<!DOCTYPE html>
<html>
<head>
  <title>Alert Box</title>
</head>
<body>

  <h2>Click the Button</h2>

  <button onclick="showAlert()">Click Me!</button>

  <script>
    function showAlert() {
      alert("Hello! This is an alert box.");
    }
  </script>

</body>
</html>


```
## Calculator
```
<!DOCTYPE html>
<html>
<head>
  <title>Simple Calculator</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <h2>Simple Calculator</h2>
  <input type="text" id="display" readonly>

  <div class="buttons">
    <button class="btn" onclick="add('7')">7</button>
    <button class="btn" onclick="add('8')">8</button>
    <button class="btn" onclick="add('9')">9</button>
    <button class="btn" onclick="add('/')">/</button>

    <button class="btn" onclick="add('4')">4</button>
    <button class="btn" onclick="add('5')">5</button>
    <button class="btn" onclick="add('6')">6</button>
    <button class="btn" onclick="add('*')">*</button>

    <button class="btn" onclick="add('1')">1</button>
    <button class="btn" onclick="add('2')">2</button>
    <button class="btn" onclick="add('3')">3</button>
    <button class="btn" onclick="add('-')">-</button>

    <button class="btn" onclick="add('0')">0</button>
    <button class="btn" onclick="add('.')">.</button>
    <button class="btn" onclick="calculate()">=</button>
    <button class="btn" onclick="add('+')">+</button>

    <button class="btn" onclick="clearDisplay()">C</button>
  </div>

  <script src="script.js"></script>
</body>
</html>

```

## styles.html
```
body {
  text-align: center;
  font-family: sans-serif;
}

#display {
  width: 200px;
  height: 30px;
  font-size: 18px;
  margin: 10px;
}

.btn {
  width: 45px;
  height: 45px;
  margin: 5px;
  font-size: 16px;
  background: #4CAF50;
  color: white;
  border: none;
}
```
## Js
```python
const d = document.getElementById("display");

const add = v => d.value += v;
const clearDisplay = () => d.value = "";
const calculate = () => d.value = eval(d.value) || "";


```

## up
```python
function add(value) {
  display.value += value;
}

function clearDisplay() {
  display.value = "";
}

function calculate() {

    display.value = eval(display.value);
  
}
```

## Port contact

```python
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Mounesh Goud - Portfolio</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <header>
    <h1>Mounesh Goud</h1>
    <nav>
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section id="hero">
    <h2>Hello, I’m Mounesh 👋</h2>
    <p>I’m a Full-Stack Developer and Educator.</p>
  </section>

  <section id="about">
    <h2>About Me</h2>
    <p>I teach Python, Flask, Data Science, and Full-Stack Web Development. I love building things and teaching what I learn!</p>
  </section>

  <section id="projects">
    <h2>Projects</h2>
    <ul>
      <li>📝 Note Saver App (React + useState)</li>
      <li>📊 Data Visualizer (Python + Matplotlib)</li>
      <li>💻 Flask Fitness Web App</li>
    </ul>
  </section>

  <section id="contact">
    <h2>Contact Me</h2>
    <form onsubmit="handleSubmit(event)">
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
  </section>

  <footer>
    <p>© 2025 Mounesh Goud | Bengaluru, India</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>


```

## css
```python
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  line-height: 1.6;
  background: #f9f9f9;
  color: #333;
}

header {
  background: #333;
  color: #fff;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav a {
  color: #fff;
  margin-left: 15px;
  text-decoration: none;
}

#hero {
  background: #e3f2fd;
  padding: 40px;
  text-align: center;
}

section {
  padding: 30px;
  max-width: 800px;
  margin: auto;
}

form input, form textarea {
  display: block;
  width: 100%;
  margin-bottom: 15px;
  padding: 10px;
}

button {
  padding: 10px 20px;
  background: #1976d2;
  color: white;
  border: none;
  cursor: pointer;
}

footer {
  text-align: center;
  padding: 20px;
  background: #333;
  color: white;
  margin-top: 40px;
}


```

## Js
```python
function handleSubmit(event) {
  event.preventDefault();
  alert("Thank you! Your message has been sent ✅");
}


```

## Change text
```js
<!DOCTYPE html>
<html>
<head>
  <title>Change Text</title>
</head>
<body>

  <h2 id="text">Hello, World!</h2>

  <button onclick="changeText()">Change Text</button>

  <script>
    function changeText() {
      document.getElementById("text").innerText = "You clicked the button!";
    }
  </script>

</body>
</html>
```

```js

<!DOCTYPE html>
<html>
<head>
  <title>Click Counter</title>
</head>
<body>

  <h2>Button Click Counter</h2>

  <button onclick="countClicks()">Click me</button>

  <p id="clickCount">Clicked 0 times</p>

  <script>
    let clicks = 0;

    function countClicks() {
      clicks++;
      document.getElementById("clickCount").innerText = "Clicked " + clicks + " times";
    }
  </script>

</body>
</html>

```


## React
### App.jsx
```react

import React from 'react';
import Header from './Header';

function App() {
  return (
    <div>
      <Header />
      <h1>Hello from App Component</h1>
    </div>
  );
}

export default App;

```

## Header.jsx
```react
import React from 'react';

function Header() {
  return <h2>This is the Header</h2>;
}

export default Header;


```

## Change name

### App.jsx
```react
import React, { useState } from "react"; // ✅ import useState
import Header from "./Header";

function App() {
  const [name, setName] = useState("Mounesh"); // ✅ create state variable

  return (
    <div>
      <Header />
      <h1>Hello from App Component</h1>
      <p>Welcome, {name} 👋</p>

      {/* Button to change the name */}
      <button onClick={() => setName("Guru")}>Change Name</button>
    </div>
  );
}

export default App;

```

## Counter.jsx

```react
import React, { useState } from "react";
import Header from "./Header";

function App() {
  const [count, setCount] = useState(0); // count starts at 0

  return (
    <div>
      <Header />
      <h1>React Counter</h1>

      <p>You clicked {count} times</p>

      {/* Button to increase the count */}
      <button onClick={() => setCount(count + 1)}>Click Me</button>
    </div>
  );
}

export default App;


```

## E-commerce


## App.jsx
```python
// src/App.jsx
import React from 'react';
import './App.css'; // for styles

function App() {
  return (
    <div className="container">
      <h1>ShopEasy 🛒</h1>

      <section className="products">
        <div className="card">
          <img src="/OIP.jpeg" alt="Local Product" />
          <h2>Smart Watch</h2>
          <p>Track your steps, heart rate, and more.</p>
          <p className="price">₹1,999</p>
          <button>Add to Cart</button>
        </div>

        <div className="card">
          <img src="/OIP.jpeg" alt="Local Product" />
          <h2>Bluetooth Speaker</h2>
          <p>Deep bass, portable, long battery life.</p>
          <p className="price">₹1,499</p>
          <button>Add to Cart</button>
        </div>

        <div className="card">
          <img src="/OIP.jpeg" alt="Local Product" />

          <h2>Wireless Headphones</h2>
          <p>Noise cancellation, high-quality sound.</p>
          <p className="price">₹2,499</p>
          <button>Add to Cart</button>
        </div>
      </section>

      <footer>
        <p>© 2025 ShopEasy. All rights reserved.</p>
      </footer>
    </div>
  );
}

export default App;


```

## Main.jsx
```
// src/main.jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

## Data.js


```python
const products = [
  {
    id: 1,
    name: "Wireless Headphones",
    price: 2499,
    description: "High-quality wireless headphones with noise cancellation.",
    image: ""
  },
  {
    id: 2,
    name: "Smart Watch",
    price: 1999,
    description: "Track your fitness with this smart wearable.",
    image: ""
  },
  {
    id: 3,
    name: "Bluetooth Speaker",
    price: 1499,
    description: "Portable speaker with deep bass and long battery life.",
    image: ""
  }
];

export default products;


```

## App.css
```react
/* src/App.css */
body {
  font-family: sans-serif;
  background: #f8f8f8;
  margin: 0;
  padding: 0;
}

.container {
  padding: 20px;
  text-align: center;
}

.products {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-top: 20px;
}

.card {
  background: white;
  padding: 16px;
  border-radius: 8px;
  width: 220px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.card img {
  width: 100%;
  border-radius: 4px;
}

.card h2 {
  font-size: 18px;
  margin: 10px 0 5px;
}

.card p {
  font-size: 14px;
  color: #555;
}

.price {
  color: #000;
  font-weight: bold;
  margin: 8px 0;
}

button {
  background-color: #007bff;
  border: none;
  color: white;
  padding: 8px 12px;
  border-radius: 4px;
  cursor: pointer;
}

footer {
  margin-top: 30px;
  color: #777;
}


```


```react
// src/App.jsx
import React, { useState } from 'react';
import './App.css';

function App() {
  const [cartCount, setCartCount] = useState(0);
  const [showCart, setShowCart] = useState(false);

  const handleAddToCart = () => {
    setCartCount(cartCount + 1);
  };

  return (
    <div className="container">
      {/* Header */}
      <header className="header">
        <h1>ShopEasy 🛍️</h1>
        <div>
          <button className="cart-toggle" onClick={() => setShowCart(!showCart)}>
            🛒 View Cart ({cartCount})
          </button>
        </div>
      </header>

      {/* Products */}
      <section className="products">
        <div className="card">
          <img src="/OIP.jpeg" alt="Smart Watch" />
          <h2>Smart Watch</h2>
          <p>Track your steps, heart rate, and more.</p>
          <p className="price">₹1,999</p>
          <button onClick={handleAddToCart}>Add to Cart</button>
        </div>

        <div className="card">
          <img src="/OIP.jpeg" alt="Bluetooth Speaker" />
          <h2>Bluetooth Speaker</h2>
          <p>Deep bass, portable, long battery life.</p>
          <p className="price">₹1,499</p>
          <button onClick={handleAddToCart}>Add to Cart</button>
        </div>

        <div className="card">
          <img src="/OIP.jpeg" alt="Wireless Headphones" />
          <h2>Wireless Headphones</h2>
          <p>Noise cancellation, high-quality sound.</p>
          <p className="price">₹2,499</p>
          <button onClick={handleAddToCart}>Add to Cart</button>
        </div>
      </section>

      {/* Sidebar Cart */}
      {showCart && (
        <div className="cart-sidebar">
          <h2>🛒 Cart</h2>
          <p>You have {cartCount} item(s) in your cart.</p>
          <button onClick={() => setShowCart(false)}>Close</button>
        </div>
      )}

      {/* Footer */}
      <footer>
        <p>© 2025 ShopEasy. All rights reserved.</p>
      </footer>
    </div>
  );
}

export default App;


```


```react

// src/App.jsx
import React, { useState } from 'react';
import './App.css';
import products from './data';

function App() {
  const [cart, setCart] = useState([]);
  const [showCart, setShowCart] = useState(false);

  const addToCart = (product) => {
    setCart([...cart, product]);
  };

  return (
    <div className="container">
      <h1>ShopEasy 🛒</h1>
      
      <button className="view-cart-btn" onClick={() => setShowCart(!showCart)}>
        🛒 View Cart ({cart.length})
      </button>

      {showCart && (
        <div className="cart-box">
          <h2>🛍️ Your Cart</h2>
          {cart.length === 0 ? (
            <p>No items yet!</p>
          ) : (
            <ul>
              {cart.map((item, index) => (
                <li key={index}>{item.name} - {item.price}</li>
              ))}
            </ul>
          )}
        </div>
      )}

      <section className="products">
        {products.map((product) => (
          <div key={product.id} className="card">
            <img src={product.image} alt={product.name} />
            <h2>{product.name}</h2>
            <p>{product.description}</p>
            <p className="price">{product.price}</p>
            <button onClick={() => addToCart(product)}>Add to Cart</button>
          </div>
        ))}
      </section>

      <footer>
        <p>© 2025 ShopEasy. All rights reserved.</p>
      </footer>
    </div>
  );
}

export default App;


```

```react
// src/App.jsx
import React, { useState } from 'react';
import './App.css';
import products from './data';

function App() {
  const [cart, setCart] = useState([]);

  const handleAddToCart = (product) => {
    setCart((prevCart) => [...prevCart, product]);
  };

  return (
    <div className="container">
      <h1>ShopEasy 🛒</h1>

      <section className="products">
        {products.map((product) => (
          <div className="card" key={product.id}>
            <img src={product.img} alt={product.name} />
            <h2>{product.name}</h2>
            <p>{product.desc}</p>
            <p className="price">₹{product.price}</p>
            <button onClick={() => handleAddToCart(product)}>Add to Cart</button>
          </div>
        ))}
      </section>

      {/* Cart Section */}
      <section className="cart">
        <h2>Your Cart 🛍️</h2>
        {cart.length === 0 ? (
          <p>Cart is empty</p>
        ) : (
          <ul>
            {cart.map((item, index) => (
              <li key={index}>
                {item.name} - ₹{item.price}
              </li>
            ))}
          </ul>
        )}
      </section>

      <footer>
        <p>© 2025 ShopEasy. All rights reserved.</p>
      </footer>
    </div>
  );
}

export default App;


```

# With image
```react

import React, { useState } from 'react';
import './App.css';
import products from './data';

function App() {
  const [cart, setCart] = useState([]);

  const handleAddToCart = (product) => {
    setCart((prevCart) => [...prevCart, product]);
  };

  return (
    <div className="container">
      <h1>ShopEasy 🛒</h1>

      {/* Product Section */}
      <section className="products">
        {products.map((product) => (
          <div className="card" key={product.id}>
            <img src={product.image} alt={product.name} />
            <h2>{product.name}</h2>
            <p>{product.description}</p>
            <p className="price">₹{product.price}</p>
            <button onClick={() => handleAddToCart(product)}>Add to Cart</button>
          </div>
        ))}
      </section>

      {/* Cart Section */}
      <section className="cart">
        <h2>Your Cart 🛍️</h2>
        {cart.length === 0 ? (
          <p>Cart is empty</p>
        ) : (
          <ul>
            {cart.map((item, index) => (
              <li key={index}>
                {item.name} - ₹{item.price}
              </li>
            ))}
          </ul>
        )}
      </section>

      <footer>
        <p>© 2025 ShopEasy. All rights reserved.</p>
      </footer>
    </div>
  );
}

export default App;


```





