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
