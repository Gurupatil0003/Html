##🚀 Day 3 – JavaScript Essentials

## 🧠 1. Variables in JavaScript
Type	Keyword	Can Change Value?	Scope
var	✔ Yes	function/global	
let	✔ Yes	block scoped	
const	❌ No	block scoped	
```c
✨ Example:
var name = "Mounesh";
let age = 22;
const country = "India";

age = 23; // allowed
// country = "USA"; ❌ error (const cannot be changed)

console.log(name, age, country);
```
#3🔥 2. Functions
```c
✔ Function Declaration
function greet() {
  console.log("Hello, Welcome!");
}
greet();
```
## ✔ Function with Parameters & Return
```js
function add(a, b) {
  return a + b;
}
console.log(add(10, 20)); // 30
```
## 🔄 3. Loops (for, while)
```js
For Loop
for(let i=1; i<=5; i++){
  console.log("Number:", i);
}
```
```js
While Loop
let x = 1;
while(x <= 5){
  console.log("Count:", x);
  x++;
}
```

## 🖱 4. Events in JavaScript
```c
<button onclick="displayMessage()">Click Me</button>
```
```c
<script>
function displayMessage(){
  alert("Button Clicked!");
}
</script>
```

## 🌳 5. DOM Manipulation (Very Important)

Selecting Elements:
```c
document.getElementById("title").style.color = "red";
document.querySelector(".box").innerText = "Updated Text!";
```
## Example HTML + JS
```c
<h2 id="title">JavaScript learning</h2>
<div class="box">Original</div>
<button onclick="change()">Change Text</button>
```
```js
<script>
function change(){
  document.querySelector(".box").innerText = "Changed Successfully!";
}
</script>
```

🌍 6. Fetch API Basics (Calling API)
```c
fetch("https://jsonplaceholder.typicode.com/users")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(err => console.log("Error:", err));

```
✔ Used to call APIs and get data
✔ Works using Promises

## 🧪 7. Hands-On: Form Validation + Dynamic Webpage
```HTML
<form onsubmit="return validateForm()">
  <input type="text" id="username" placeholder="Enter username">
  <input type="password" id="password" placeholder="Enter password">
  <button type="submit">Submit</button>
</form>
<p id="msg"></p>
```
## JS (Validation + Dynamic Message)
```js
function validateForm(){
  let user = document.getElementById("username").value;
  let pass = document.getElementById("password").value;
  let msg = document.getElementById("msg");

  if(user =="" || pass ==""){
    msg.innerHTML = "❌ All fields are required!";
    msg.style.color="red";
    return false;
  } else {
    msg.innerHTML = "✔ Successfully submitted!";
    msg.style.color="green";
    return false;
  }
}
```


```js
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Character Counter</title>
</head>
<body>
  <style>
    body {
  font-family: sans-serif;
  padding: 30px;
  text-align: center;
}

textarea {
  width: 300px;
  padding: 10px;
  border: 2px solid #aaa;
  border-radius: 5px;
}

textarea:focus {
  border-color: #4a90e2;
}

#count {
  font-weight: bold;
  color: #4a90e2;
}

  </style>

  <h2>Type Something:</h2>
  <textarea id="text" oninput="countChars()" rows="4" cols="40"></textarea>

  <p>Characters: <span id="count">0</span></p>

  <script>
    function countChars() {
  let text = document.getElementById("text").value;
  document.getElementById("count").innerText = text.length;
}
  </script>
  
  
</body>
</html>

```

```js
<!DOCTYPE html>
<html>
<body style="font-family:sans-serif;padding:20px;max-width:600px;margin:auto">

<style>
  body { background:#f7f7f7; }
  #text {
    background:#fff;
    padding:15px;
    border-radius:8px;
    border-left:4px solid #4CAF50;
    margin-bottom:15px;
    font-size:18px;
  }
  #box {
    width:100%;
    padding:12px;
    border:2px solid #ccc;
    border-radius:8px;
    font-size:18px;
    outline:none;
  }
#box:focus {
    border-color:#4CAF50;
  }
  .stats {
    margin-top:15px;
    padding:10px;
    background:#fff;
    border-radius:8px;
    display:flex;
    justify-content:space-between;
    font-size:18px;
  }
</style>

<p id="text">The quick brown fox jumps over the lazy dog.</p>

<input id="box" placeholder="Start typing...">

<div class="stats">
  <div>⏱ Time: <span id="t">0</span>s</div>
  <div>⌨ WPM: <span id="w">0</span></div>
  <div>🎯 Accuracy: <span id="a">100</span>%</div>
</div>
<script>
let sec = 0, started = false;
let target = text.innerText;

box.oninput = () => {

  if (!started) {
    started = true;
    setInterval(() => { sec++; t.innerText = sec }, 1000);
  }

  let typed = box.value;
  let correct = 0;

  for (let i = 0; i < typed.length; i++)
    if (typed[i] == target[i]) correct++;

  a.innerText = ((correct / typed.length) * 100 || 100).toFixed(0);

  let words = typed.trim().split(" ").length;
  w.innerText = Math.round((words / sec) * 60) || 0;
  if (typed === target)
    alert("Done! WPM: " + w.innerText);
};
</script>

</body>
</html>
```
