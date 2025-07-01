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







