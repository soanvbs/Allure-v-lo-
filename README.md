# Allure-v-lo-
Solo VS Peloton 
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comparaison Allure Vélo</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: #f0f2f5;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 40px;
    }

    .container {
      background: white;
      border-radius: 10px;
      padding: 30px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      max-width: 450px;
      width: 90%;
      text-align: center;
    }

    h1 {
      color: #2c3e50;
      margin-bottom: 20px;
    }

    label {
      font-weight: bold;
      display: block;
      margin-top: 20px;
    }

    input[type="range"] {
      width: 100%;
      margin: 10px 0;
    }

    .value-display {
      margin-bottom: 10px;
      font-size: 1.1em;
    }

    .result {
      margin-top: 25px;
      font-size: 1.4em;
      color: #2c7be5;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h1>Comparaison Solo vs Peloton</h1>

  <div class="container">
    <label for="soloSpeed">Allure solo (km/h)</label>
    <input type="range" id="soloSpeed" min="20" max="50" value="30" step="1" oninput="updateSpeed()">
    <div class="value-display">Allure solo : <span id="soloVal">30</span> km/h</div>

    <label for="gain">Gain en peloton (%)</label>
    <input type="range" id="gain" min="0" max="30" value="15" step="1" oninput="updateSpeed()">
    <div class="value-display">Gain : <span id="gainVal">15</span> %</div>

    <div class="result">
      Allure en peloton : <span id="groupVal">34.5</span> km/h
    </div>
  </div>

  <script>
    function updateSpeed() {
      const solo = parseFloat(document.getElementById("soloSpeed").value);
      const gain = parseFloat(document.getElementById("gain").value);

      const peloton = (solo * (1 + gain / 100)).toFixed(1);

      document.getElementById("soloVal").innerText = solo;
      document.getElementById("gainVal").innerText = gain;
      document.getElementById("groupVal").innerText = peloton;
    }

    // Mise à jour initiale
    updateSpeed();
  </script>

</body>
</html>
