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
