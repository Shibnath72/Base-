<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Base Quiz</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: #0f1724;
      color: #fff;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      flex-direction: column;
    }
    img {
      width: 180px;
      cursor: pointer;
      transition: transform 0.3s;
    }
    img:hover {
      transform: scale(1.05);
    }
    #quiz {
      display: none;
      max-width: 600px;
      width: 90%;
    }
    .question {
      margin-bottom: 20px;
      background: #162338;
      padding: 15px;
      border-radius: 10px;
    }
    button {
      background: #3b82f6;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
      margin-top: 10px;
    }
    button:hover {
      background: #2563eb;
    }
    #result {
      margin-top: 15px;
      font-weight: bold;
      font-size: 18px;
    }
  </style>
</head>
<body>

  <!-- Base Logo -->
  <img id="baseLogo" src="https://base.org/static/base-logo-white.svg" alt="Base Logo" onclick="startQuiz()" />

  <!-- Quiz Section -->
  <div id="quiz">
    <h2>Base Quiz — 5 Questions</h2>

    <div class="question">
      <p>1. What reward rate (APY) is offered in the Base App for holding USDC?</p>
      <input type="radio" name="q1" value="0"> 2.0%<br>
      <input type="radio" name="q1" value="1"> 3.0%<br>
      <input type="radio" name="q1" value="2"> 4.1%<br>
      <input type="radio" name="q1" value="3"> 5.0%<br>
    </div>

    <div class="question">
      <p>2. Which of the following is not a listed feature of the Base App?</p>
      <input type="radio" name="q2" value="0"> Messaging meets money<br>
      <input type="radio" name="q2" value="1"> Trade millions of coins<br>
      <input type="radio" name="q2" value="2"> Virtual reality social spaces<br>
      <input type="radio" name="q2" value="3"> Create and earn from content<br>
    </div>

    <div class="question">
      <p>3. On the “Ecosystem” page, which of these is listed as a component under the Base Ecosystem?</p>
      <input type="radio" name="q3" value="0"> Base Insurance<br>
      <input type="radio" name="q3" value="1"> Gas credits<br>
      <input type="radio" name="q3" value="2"> NFT Marketplace<br>
      <input type="radio" name="q3" value="3"> Game engine<br>
    </div>

    <div class="question">
      <p>4. Which tool is not explicitly mentioned under “Tools for builders”?</p>
      <input type="radio" name="q4" value="0"> Base Account<br>
      <input type="radio" name="q4" value="1"> OnchainKit<br>
      <input type="radio" name="q4" value="2"> Mini Apps<br>
      <input type="radio" name="q4" value="3"> Virtual Machines<br>
    </div>

    <div class="question">
      <p>5. What capability does “Base Appchains” allow builders to do?</p>
      <input type="radio" name="q5" value="0"> Launch an independent chain with dedicated blockspace<br>
      <input type="radio" name="q5" value="1"> Create smart contracts without Solidity<br>
      <input type="radio" name="q5" value="2"> Automatically convert fiat to crypto<br>
      <input type="radio" name="q5" value="3"> Host centralized databases<br>
    </div>

    <button onclick="checkAnswers()">Submit Answers</button>
    <div id="result"></div>
  </div>

  <script>
    function startQuiz() {
      document.getElementById("baseLogo").style.display = "none";
      document.getElementById("quiz").style.display = "block";
    }

    function checkAnswers() {
      const correctAnswers = [2, 2, 1, 3, 0];
      let score = 0;
      for (let i = 1; i <= 5; i++) {
        const ans = document.querySelector(`input[name="q${i}"]:checked`);
        if (ans && parseInt(ans.value) === correctAnswers[i - 1]) {
          score++;
        }
      }
      document.getElementById("result").innerHTML = `✅ You scored ${score} / 5`;
    }
  </script>
</body>
</html>
