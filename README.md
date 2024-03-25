# rockpaperscissors.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rock Paper Scissors</title>
<style>
  body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f0;
  }
  .container {
    text-align: center;
  }
  img {
    width: 150px;
  }
</style>
</head>
<body>
<div class="container">
  <h1>Rock, Paper, Scissors</h1>
  <input type="text" id="userInput" placeholder="Enter your choice (rock, paper, scissors)">
  <button onclick="playGame()">Play</button>
  <div id="result"></div>
</div>

<script>
function playGame() {
  var userInput = document.getElementById("userInput").value.toLowerCase();
  var options = ["rock", "paper", "scissors"];
  var randomIndex = Math.floor(Math.random() * 3);
  var computerChoice = options[randomIndex];

  document.getElementById("result").innerHTML = "<p>You have picked " + userInput + "</p>";

  if (userInput === "rock") {
    document.getElementById("result").innerHTML += "<pre>    _______\n---'   ____)\n      (_____)\n      (_____)\n      (____)\n---.__(___)</pre>";
  } else if (userInput === "paper") {
    document.getElementById("result").innerHTML += "<pre>     _______\n---'    ____)____\n               ______)\n              _______)\n             _______)\n    ---.__________)</pre>";
  } else if (userInput === "scissors") {
    document.getElementById("result").innerHTML += "<pre>        _______\n---'   ____)____\n              ______)\n           __________)\n          (____)\n    ---.__(___)</pre>";
  } else {
    document.getElementById("result").innerHTML += "<p>Invalid input, please choose rock, paper, or scissors.</p>";
    return;
  }

  document.getElementById("result").innerHTML += "<p>Computer picked " + computerChoice + "</p>";

  if (computerChoice === "rock") {
    document.getElementById("result").innerHTML += "<pre>    _______\n---'   ____)\n      (_____)\n      (_____)\n      (____)\n---.__(___)</pre>";
  } else if (computerChoice === "paper") {
    document.getElementById("result").innerHTML += "<pre>     _______\n---'    ____)____\n               ______)\n              _______)\n             _______)\n    ---.__________)</pre>";
  } else if (computerChoice === "scissors") {
    document.getElementById("result").innerHTML += "<pre>        _______\n---'   ____)____\n              ______)\n           __________)\n          (____)\n    ---.__(___)</pre>";
  }

  if ((userInput === "rock" && computerChoice === "scissors") || 
      (userInput === "paper" && computerChoice === "rock") ||
      (userInput === "scissors" && computerChoice === "paper")) {
    document.getElementById("result").innerHTML += "<p>You WIN!</p>";
  } else if (userInput === computerChoice) {
    document.getElementById("result").innerHTML += "<p>It's a draw!</p>";
  } else {
    document.getElementById("result").innerHTML += "<p>You LOSE!</p>";
  }
}
</script>
</body>
</html>
