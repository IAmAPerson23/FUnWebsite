<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Random Cool Website</title>
<style>
  /* Global styles */
  body {
    font-family: 'Arial', sans-serif;
    background-color: #1a1a1a;
    color: #ffffff;
    margin: 0;
    padding: 0;
  }
  h1 {
    font-size: 36px;
    margin: 0;
    padding: 20px;
    text-align: center;
  }
  main {
    padding: 20px;
    text-align: center;
  }
  p {
    font-size: 18px;
    line-height: 1.6;
    margin-bottom: 20px;
  }
  .cta-button {
    background-color: #3498db;
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .cta-button:hover {
    background-color: #2980b9;
  }
  .fun-section {
    background-color: #f39c12;
    padding: 40px 0;
    text-align: center;
  }
  .emoji {
    font-size: 48px;
  }
  .quote {
    font-size: 24px;
    margin-top: 10px;
  }

  /* Snake game styles */
  #snake-game-container {
    background-color: #333;
    width: 200px;
    height: 200px;
    border: 2px solid #222;
    overflow: hidden;
    text-align: center;
    margin: 20px;
  }
  #snake-game canvas {
    display: block;
    margin: 0 auto;
  }
  #snake-game-label {
    color: #ffffff;
    font-size: 16px;
    margin-top: 10px;
  }
</style>
</head>
<body>
  <h1>Welcome to the Random Cool Website</h1>
  <main>
    <p>This is a place of creativity and inspiration. Explore the possibilities!</p>
    <button class="cta-button">Learn More</button>
  </main>
  <div class="fun-section">
    <div class="emoji">🚀</div>
    <div class="quote">"Life is too short to be ordinary."</div>
  </div>
  <!-- Snake game container -->
  <div id="snake-game-container">
    <canvas id="snake-canvas" width="200" height="200"></canvas>
    <div id="snake-game-label">Click to Start Snake Game</div>
  </div>
  <script>
    // Snake game code
    const canvas = document.getElementById('snake-canvas');
    const context = canvas.getContext('2d');
    const canvasSize = 200;
    canvas.style.backgroundColor = '#333';

    let snake = [{ x: 10, y: 10 }];
    let food = { x: 15, y: 15 };
    let dx = 1;
    let dy = 0;
    let interval;

    let gameStarted = false;

    function drawSnake() {
      context.clearRect(0, 0, canvasSize, canvasSize);
      for (let i = 0; i < snake.length; i++) {
        context.fillStyle = '#ffffff';
        context.fillRect(snake[i].x * 10, snake[i].y * 10, 10, 10);
      }
      context.fillStyle = '#ff0000';
      context.fillRect(food.x * 10, food.y * 10, 10, 10);
    }

    function updateSnake() {
      const newHead = { x: snake[0].x + dx, y: snake[0].y + dy };
      snake.unshift(newHead);

      if (newHead.x === food.x && newHead.y === food.y) {
        food = {
          x: Math.floor(Math.random() * (canvasSize / 10)),
          y: Math.floor(Math.random() * (canvasSize / 10)),
        };
      } else {
        snake.pop();
      }

      if (newHead.x < 0 || newHead.x >= canvasSize / 10 || newHead.y < 0 || newHead.y >= canvasSize / 10) {
        clearInterval(interval);
      }

      for (let i = 1; i < snake.length; i++) {
        if (snake[i].x === newHead.x && snake[i].y === newHead.y) {
          clearInterval(interval);
        }
      }

      drawSnake();
    }

    canvas.addEventListener('click', () => {
      if (!gameStarted) {
        interval = setInterval(updateSnake, 150); // Slower speed
        gameStarted = true;
        document.getElementById('snake-game-label').style.display = 'none';
      }
    });

    document.addEventListener('keydown', (event) => {
      if (gameStarted) {
        if (event.key === 'ArrowUp' && dy !== 1) {
          dx = 0;
          dy = -1;
        } else if (event.key === 'ArrowDown' && dy !== -1) {
          dx = 0;
          dy = 1;
        } else if (event.key === 'ArrowLeft' && dx !== 1) {
          dx = -1;
          dy = 0;
        } else if (event.key === 'ArrowRight' && dx !== -1) {
          dx = 1;
          dy = 0;
        }
      }
    });
  </script>
</body>
</html>
