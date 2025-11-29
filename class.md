## ✅ PART 1 — Basic Structure + Headings
```c
HTML
<!DOCTYPE html>
<html>
<head>
  <title>My Page</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <h1>Main Heading</h1>
  <h2>Sub Heading</h2>
  <h3>Small Heading</h3>

</body>
</html>
```
CSS
```c
h1 {
  color: darkblue;
}

h2 {
  color: darkgreen;
}

h3 {
  color: gray;
}
```

## ✅ PART 2 — Paragraph, Links, Images
```HTML
<p>This is a paragraph. HTML is easy!</p>

<a href="#">This is a link</a>

<img src="image.jpg" alt="Sample Image">
```

```c
CSS
p {
  font-size: 16px;
  line-height: 1.5;
}

a {
  color: blue;
  text-decoration: none;
}

img {
  width: 200px;
  border-radius: 5px;
}
```

✅ PART 3 — Lists (ul, ol, li)
```HTML
<ul>
  <li>Apple</li>
  <li>Banana</li>
</ul>

<ol>
  <li>First Step</li>
  <li>Second Step</li>
</ol>
```
```CSS
ul {
  list-style-type: square;
}

ol {
  list-style-type: decimal;
}

li {
  margin-bottom: 5px;
}
```
✅ PART 4 — Table
```HTML
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Alex</td>
    <td>20</td>
  </tr>
</table>
```
```CSS
table {
  border-collapse: collapse;
  width: 50%;
}

th, td {
  border: 1px solid black;
  padding: 8px;
}
```
✅ PART 5 — Forms (input, label, textarea, button)
```HTML
<form>
  <label>Name:</label>
  <input type="text">

  <label>Message:</label>
  <textarea></textarea>

  <button>Submit</button>
</form>
```
```CSS
input, textarea {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
}

button {
  padding: 8px 15px;
  background: black;
  color: white;
  border: none;
}
```


✅ PART 6 — div & span (very important tags)
```HTML
<div class="box">
  This is a div container.
  <span class="highlight">This is span text.</span>
</div>
```
```CSS
.box {
  background: #f2f2f2;
  padding: 20px;
  border-radius: 6px;
}

.highlight {
  color: red;
  font-weight: bold;
}
```
✅ PART 7 — Semantic Tags (header, nav, section, article, footer)
```HTML
<header>
  <h1>My Website Header</h1>
</header>

<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
</nav>

<section>
  <article>
    <h2>Article Title</h2>
    <p>This is an article paragraph.</p>
  </article>
</section>

<footer>
  © 2025 My Website
</footer>
```
```CSS
header {
  background: #333;
  color: white;
  padding: 15px;
}

nav a {
  margin-right: 10px;
  color: blue;
}

section {
  margin-top: 20px;
}

footer {
  background: #222;
  color: white;
  text-align: center;
  padding: 10px;
  margin-top: 30px;
}
```
✅ PART 8 — Buttons
```HTML
<button class="btn">Click Me</button>
```
```CSS
.btn {
  padding: 10px 20px;
  background: purple;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.btn:hover {
  background: darkviolet;
}
```
✅ PART 9 — Card UI Box
```HTML
<div class="card">
  <h3>Card Title</h3>
  <p>This is card content.</p>
</div>
```
```CSS
.card {
  width: 250px;
  padding: 15px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}
```
✅ PART 10 — Flexbox (very useful for layouts)
```HTML
<div class="flexbox">
  <div class="item">One</div>
  <div class="item">Two</div>
  <div class="item">Three</div>
</div>
```
```CSS
.flexbox {
  display: flex;
  gap: 10px;
}

.item {
  background: lightblue;
  padding: 15px;
  border-radius: 6px;
}
```


✅ PART 11 — CSS Grid Layout
```HTML
<div class="grid-container">
  <div class="box">1</div>
  <div class="box">2</div>
  <div class="box">3</div>
  <div class="box">4</div>
</div>
```
```CSS
.grid-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
}

.box {
  background: lightcoral;
  padding: 20px;
  text-align: center;
  border-radius: 6px;
  color: white;
  font-size: 20px;
}
```
✅ PART 12 — Simple Animation
```HTML
<div class="animate-box">Hello!</div>
```
```CSS
.animate-box {
  width: 100px;
  height: 100px;
  background: teal;
  animation: move 2s infinite alternate;
}

@keyframes move {
  from { transform: translateX(0); }
  to   { transform: translateX(100px); }
}
```
✅ PART 13 — Responsive Design (Media Query)
```HTML
<div class="responsive-box">Resize the screen</div>
```
```CSS
.responsive-box {
  background: orange;
  padding: 20px;
  font-size: 20px;
}

@media (max-width: 600px) {
  .responsive-box {
    background: red;
    font-size: 14px;
  }
}
```
✅ PART 14 — Navigation Bar
```HTML
<nav class="navbar">
  <a href="#">Home</a>
  <a href="#">Services</a>
  <a href="#">Contact</a>
</nav>
```
```CSS
.navbar {
  background: black;
  padding: 10px;
}

.navbar a {
  color: white;
  margin-right: 15px;
  text-decoration: none;
}

.navbar a:hover {
  text-decoration: underline;
}
```
✅ PART 15 — Full Simple Layout
```HTML
<header>Header</header>

<section class="content">
  <aside>Sidebar</aside>
  <main>Main Content</main>
</section>

<footer>Footer</footer>
```
```CSS
header, footer {
  background: #333;
  color: white;
  padding: 15px;
  text-align: center;
}

.content {
  display: flex;
  margin: 20px 0;
}

aside {
  width: 30%;
  background: #eee;
  padding: 15px;
}

main {
  width: 70%;
  padding: 15px;
  background: #f9f9f9;
}
```
