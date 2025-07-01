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







