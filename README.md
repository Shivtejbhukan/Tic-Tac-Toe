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
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin-top: 40px;
    background: #f0f0f0;
  }
  
  #game {
    display: grid;
    grid-template-columns: repeat(3, 100px);
    grid-gap: 10px;
    justify-content: center;
    margin: 20px auto;
  }
  
  .cell {
    width: 100px;
    height: 100px;
    font-size: 2.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #fff;
    border: 2px solid #333;
    cursor: pointer;
  }
  
  .cell:hover {
    background-color: #e0e0e0;
  }
  
  #status {
    font-size: 1.5rem;
    margin-top: 20px;
  }
  
  #reset {
    padding: 10px 20px;
    font-size: 1rem;
    margin-top: 10px;
  }
  
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

  <script>const cells = document.querySelectorAll('.cell');
const statusText = document.getElementById('status');
const resetBtn = document.getElementById('reset');

let currentPlayer = 'X';
let board = Array(9).fill('');
let isGameActive = true;

const winConditions = [
  [0,1,2], [3,4,5], [6,7,8], // rows
  [0,3,6], [1,4,7], [2,5,8], // cols
  [0,4,8], [2,4,6]           // diagonals
];

function handleCellClick(e) {
  const index = e.target.dataset.index;
  if (board[index] !== '' || !isGameActive) return;

  board[index] = currentPlayer;
  e.target.textContent = currentPlayer;

  if (checkWin()) {
    statusText.textContent = `Player ${currentPlayer} wins!`;
    isGameActive = false;
  } else if (board.every(cell => cell !== '')) {
    statusText.textContent = "It's a draw!";
    isGameActive = false;
  } else {
    currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
    statusText.textContent = `Player ${currentPlayer}'s turn`;
  }
}

function checkWin() {
  return winConditions.some(condition => {
    const [a, b, c] = condition;
    return board[a] && board[a] === board[b] && board[a] === board[c];
  });
}

function resetGame() {
  board.fill('');
  cells.forEach(cell => cell.textContent = '');
  currentPlayer = 'X';
  isGameActive = true;
  statusText.textContent = `Player ${currentPlayer}'s turn`;
}

cells.forEach(cell => cell.addEventListener('click', handleCellClick));
resetBtn.addEventListener('click', resetGame);

statusText.textContent = `Player ${currentPlayer}'s turn`;
</script>
</body>
</html>
