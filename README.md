
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Gautam Gaming Zone</title>

<style>
body {
  background:#090919;
  color:white;
  font-family:Arial;
  text-align:center;
  margin:0;
}
header {
  background:#171735;
  padding:25px 10px;
}
h1 {color:#00eaff;}
.container {padding:20px;}
.card {
  background:#202044;
  padding:25px;
  margin:20px auto;
  border-radius:15px;
  max-width:380px;
}
button {
  background:#00eaff;
  border:0;
  padding:13px 22px;
  border-radius:10px;
  font-weight:bold;
  margin:8px;
}
input {
  padding:12px;
  width:100px;
  border-radius:8px;
}
.result {
  color:#00ff99;
  font-size:20px;
}
</style>
</head>

<body>

<header>
<h1>🎮 GAUTAM GAMING ZONE</h1>
<p>Welcome to Gaming World</p>
</header>

<div class="container">

<h2>🔥 Our Mini Games</h2>

<div class="card">
<h2>⚡ Tap Challenge</h2>
<h1 id="score">0</h1>
<button onclick="tap()">TAP HERE</button>
<p>Increase your score!</p>
</div>

<div class="card">
<h2>🎯 Number Guess</h2>
<p>Guess a number between 1 and 10</p>

<input id="guess"
type="number" min="1" max="10"
placeholder="Number">

<br>

<button onclick="checkGuess()">GUESS</button>
<button onclick="resetGame()">RESET</button>

<p class="result" id="result">
Good Luck!
</p>
</div>

</div>

<footer>
<p>© 2026 Gautam Gaming Zone</p>
</footer>

<script>
let score = 0;

function tap() {
  score++;
  document.getElementById("score").innerText = score;
}

let answer = Math.floor(Math.random()*10)+1;

function checkGuess() {
  let value = Number(
    document.getElementById("guess").value
  );

  let result = document.getElementById("result");

  if (!Number.isInteger(value) || value < 1 || value > 10) {
    result.innerText = "Enter 1 to 10!";
  }
  else if (value === answer) {
    result.innerText = "🎉 YOU WIN!";
  }
  else if (value < answer) {
    result.innerText = "Try Higher Number!";
  }
  else {
    result.innerText = "Try Lower Number!";
  }
}

function resetGame() {
  answer = Math.floor(Math.random()*10)+1;
  document.getElementById("guess").value = "";
  document.getElementById("result").innerText = "New Game Started!";
}
</script>

</body>
</html>
