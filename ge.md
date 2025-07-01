# Home

```
<!DOCTYPE html>
<html>
<head>
  <title>Home Page</title>
  <link rel="stylesheet" href="style.css">

</head>
<body>

  <h1>Welcome to the Home Page</h1>
  <p>Please choose an option:</p>

  <a href="login.html">Login</a><br>
  <a href="register.html">Register</a>

</body>
</html>


```


# Login
```python

<!DOCTYPE html>
<html>
<head>
  <title>Login Page</title>
  <link rel="stylesheet" href="style.css">

</head>
<body>

  <h2>Login Page</h2>

  <form action="/login" method="post">
    <label for="username">Username:</label><br>
    <input type="text" id="username" name="username"><br><br>

    <label for="password">Password:</label><br>
    <input type="password" id="password" name="password"><br><br>

    <input type="submit" value="Login">
  </form>

  <p>Don't have an account? <a href="register.html">Register here</a></p>
  <p><a href="home.html">Back to Home</a></p>

</body>
</html>


```


```Register
<!DOCTYPE html>
<html>
<head>
  <title>Register Page</title>
  <link rel="stylesheet" href="style.css">

</head>
<body>

  <h2>Register Page</h2>

  <form action="/register" method="post">
    <label for="fullname">Full Name:</label><br>
    <input type="text" id="fullname" name="fullname"><br><br>

    <label for="email">Email:</label><br>
    <input type="email" id="email" name="email"><br><br>

    <label for="username">Username:</label><br>
    <input type="text" id="username" name="username"><br><br>

    <label for="password">Password:</label><br>
    <input type="password" id="password" name="password"><br><br>

    <label for="confirm">Confirm Password:</label><br>
    <input type="password" id="confirm" name="confirm"><br><br>

    <input type="submit" value="Register">
  </form>

  <p>Already have an account? <a href="login.html">Login here</a></p>
  <p><a href="home.html">Back to Home</a></p>

</body>
</html>



```
# Portfolio

```python

<!DOCTYPE html>
<html>
<head>
  <title>My Portfolio</title>
  <link rel="stylesheet" href="portfolio.css">
</head>
<body>

  <div class="container">
    <header>
      <h1>Mounesh Goud</h1>
      <p>Full Stack Developer | AI Enthusiast</p>
    </header>

    <section class="about">
      <h2>About Me</h2>
      <p>I am a passionate developer with 4+ years of experience in building web applications, AI tools, and teaching tech. I love coding, mentoring, and building products from scratch.</p>
    </section>

    <section class="projects">
      <h2>Projects</h2>
      <ul>
        <li><strong>Fitness Web App</strong> – Built using Flask and Bootstrap</li>
        <li><strong>Breakup Recovery App</strong> – Built with Streamlit & AI Agents</li>
        <li><strong>No-Code AI Platform</strong> – Built during Soothsayer Analytics</li>
      </ul>
    </section>

    <section class="contact">
      <h2>Contact</h2>
      <p>Email: mounesh@example.com</p>
      <p>LinkedIn: <a href="https://linkedin.com/in/mouneshgoud" target="_blank">mouneshgoud</a></p>
      <p>GitHub: <a href="https://github.com/mounesh" target="_blank">mounesh</a></p>
    </section>

  </div>

</body>
</html>


```


```python
/* portfolio.css */
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f8f9fa;
  margin: 0;
  padding: 0;
  color: #333;
}

.container {
  max-width: 800px;
  margin: 50px auto;
  padding: 30px;
  background-color: #fff;
  border-radius: 12px;
  box-shadow: 0 10px 20px rgba(0,0,0,0.1);
}

header {
  text-align: center;
  margin-bottom: 40px;
}

header h1 {
  font-size: 2.5em;
  margin-bottom: 5px;
  color: #007bff;
}

header p {
  font-size: 1.1em;
  color: #555;
}

section {
  margin-bottom: 30px;
}

h2 {
  color: #007bff;
  margin-bottom: 15px;
}

ul {
  list-style: square;
  padding-left: 20px;
}

a {
  color: #007bff;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}


```
