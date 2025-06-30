```python
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple CSS Animation</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <h1>Basic CSS Animation</h1>

  <div class="box"></div>

</body>
</html>


```


```python

body {
  text-align: center;
  font-family: sans-serif;
  margin-top: 50px;
}

/* The animated box */
.box {
  width: 100px;
  height: 100px;
  background-color: dodgerblue;
  position: relative;

  /* Animation property */
  animation: moveRight 3s infinite alternate;
}

/* Keyframes define the animation steps */
@keyframes moveRight {
  from {
    left: 0px;
  }
  to {
    left: 300px;
  }
}

```


```python
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Glowing Bouncing Ball</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <h1>Glowing Bouncing Ball Animation</h1>
  <div class="ball"></div>

</body>
</html>


```

```python
body {
  background: #111;
  color: white;
  text-align: center;
  padding-top: 50px;
  font-family: sans-serif;
}

/* The ball */
.ball {
  width: 80px;
  height: 80px;
  background: #00f0ff;
  border-radius: 50%;
  box-shadow: 0 0 30px #00f0ff, 0 0 60px #00f0ff;
  margin: 0 auto;

  /* Animation */
  animation: bounce 1.2s ease-in-out infinite, glow 1.2s ease-in-out infinite;
}

/* Bounce effect */
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-150px);
  }
}

/* Glow pulsing effect */
@keyframes glow {
  0%, 100% {
    box-shadow: 0 0 30px #00f0ff, 0 0 60px #00f0ff;
  }
  50% {
    box-shadow: 0 0 50px #00ffea, 0 0 100px #00ffea;
    background: #00ffea;
  }
}


```




```python

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Focus Example</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <h2>Focus Demo</h2>
  <input type="text" placeholder="Click or Tab into me!" />

</body>
</html>


```

```python
input {
  padding: 10px;
  font-size: 16px;
  border: 2px solid gray;
  border-radius: 5px;
  outline: none;
}

input:focus {
  border-color: dodgerblue;
  background-color: #e0f0ff;
  box-shadow: 0 0 5px dodgerblue;
}


```



```python
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>::before and ::after Example</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <h2 class="title">Welcome</h2>

</body>
</html>

```
```python
.title::before {
  content: "👋 ";
  color: green;
}

.title::after {
  content: " 🌟";
  color: gold;
}
