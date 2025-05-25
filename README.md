# 🎮 Tic Tac Toe Game

This is a simple **Tic Tac Toe** game built with [html,css, JavaScript]. It allows two players to play the classic game in a terminal or graphical interface.

## 📌 Features

- Two-player mode
- Clean and simple UI
- Win and draw detection
- Easy to understand code

## 🖥️ How to Run
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tic Tac Toe</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>Tic Tac Toe</h1>
  <div id="game">
    <div class="cell" data-index="0"></div>
    <div class="cell" data-index="1"></div>
    <div class="cell" data-index="2"></div>
    <div class="cell" data-index="3"></div>
    <div class="cell" data-index="4"></div>
    <div class="cell" data-index="5"></div>
    <div class="cell" data-index="6"></div>
    <div class="cell" data-index="7"></div>
    <div class="cell" data-index="8"></div>
  </div>
  <p id="status"></p>
  <button id="reset">Reset</button>

  <script src="script.js"></script>
</body>
</html>
