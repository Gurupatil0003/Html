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







