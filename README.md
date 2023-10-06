# DeliveryPlaceCalc
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Калькулятор стоимости доставки</title>
  <style>
    body {
      background-color: #eaf2f8;
    }
    
    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    
    .form {
      width: 400px;
      background-color: #fff;
      border-radius: 10px;
      padding: 20px;
      margin: 10px;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    }
    
    .form label {
      display: block;
      font-size: 18px;
      margin-bottom: 10px;
    }
    
    .form input[type="number"] {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
      margin-bottom: 20px;
    }
    
    .form button {
      background-color: #4caf50;
      color: #fff;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }
    
    .form button:hover {
      background-color: #45a049;
    }
    
    .form .result {
      margin-top: 20px;
      font-size: 20px;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="form">
      <h2>Форма 1</h2>
      <label for="field1">Поле 1</label>
      <input type="number" id="field1">
      <label for="field2">Поле 2</label>
      <input type="number" id="field2">
      <label for="field3">Поле 3</label>
      <input type="number" id="field3">
      <label for="field4">Поле 4</label>
      <input type="number" id="field4">
      <label for="field5">Поле 5</label>
      <input type="number" id="field5">
    </div>
    <div class="form">
      <h2>Форма 2</h2>
      <label for="field6">Поле 6</label>
      <input type="number" id="field6">
      <label for="field7">Поле 7</label>
      <input type="number" id="field7">
      <label for="field8">Поле 8</label>
      <input type="number" id="field8">
      <label for="field9">Поле 9</label>
      <input type="number" id="field9">
      <label for="field10">Поле 10</label>
      <input type="number" id="field10">
    </div>
  </div>
  <div class="container">
    <div class="form">
      <button onclick="calculate()">Рассчитать</button>
      <div class="result" id="result"></div>
    </div>
  </div>

  <script>
    function calculate() {
      var field1 = parseInt(document.getElementById('field1').value);
      var field2 = parseInt(document.getElementById('field2').value);
      var field3 = parseInt(document.getElementById('field3').value);
      var field4 = parseInt(document.getElementById('field4').value);
      var field5 = parseInt(document.getElementById('field5').value);
      var field6 = parseInt(document.getElementById('field6').value);
      var field7 = parseInt(document.getElementById('field7').value);
      var field8 = parseInt(document.getElementById('field8').value);
      var field9 = parseInt(document.getElementById('field9').value);
      var field10 = parseInt(document.getElementById('field10').value);

      var result = Math.ceil((field3 + field4) * 2 * (field4 + field5) * field7 / 10000) * 30 + (Math.ceil(Math.max(field3 * field4 * field5 * field7 * 1.2 / 96000, field6 * field7 / 24), 0)) * 120 + (Math.ceil(Math.max(field3 * field4 * field5 * field7 * 1.2 / 96000, field6 * field7 / 24), 0)) / 1000 * 750 + field7 * 5 * field9 + field7 * 5 * field10 + (field3 + field4 + field5) < 80 ? 15 : 35 * field7;

      document.getElementById('result').textContent = "Результат: " + result;
    }
  </script>
</body>
</html>
