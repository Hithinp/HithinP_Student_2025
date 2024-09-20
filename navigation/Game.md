---
layout: page
title: Game
permalink: /Game/
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cookie Clicker</title>
    <style>
        .game-container {
            text-align: center;
            margin-top: 50px;
        }
        button {
            padding: 10px 20px;
            font-size: 20px;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <h1>Cookie Clicker</h1>
        <p>Cookies: <span id="cookieCount">0</span></p>
        <button id="cookieButton">🍪 Click me!</button>
        <p id="upgradeInfo">Upgrade Cost: 50 (x2 cookies per click)</p>
        <button id="upgradeButton">Buy Upgrade</button>
    </div>

    <!-- Add audio element for the cookie sound -->
    <audio id="clickSound" src="audio/cookie.mp3"></audio>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            let cookies = 0;
            let cookiesPerClick = 1;
            let upgradeCost = 50;
            const clickSound = document.getElementById('clickSound');

            function clickCookie() {
                // Play the sound on cookie click
                clickSound.play();
                
                cookies += cookiesPerClick;
                document.getElementById('cookieCount').textContent = cookies;
            }

            function buyUpgrade() {
                if (cookies >= upgradeCost) {
                    cookies -= upgradeCost;
                    cookiesPerClick *= 2;
                    upgradeCost *= 2;
                    document.getElementById('cookieCount').textContent = cookies;
                    document.getElementById('upgradeInfo').textContent = `Upgrade Cost: ${upgradeCost} (x${cookiesPerClick} cookies per click)`;
                }
            }

            // Attach functions to buttons
            document.getElementById('cookieButton').onclick = clickCookie;
            document.getElementById('upgradeButton').onclick = buyUpgrade;
        });
    </script>
</body>
</html>

---
layout: page
title: Snake Game
permalink: /SnakeGame/
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Snake Game</title>
    <style>
        .game-container {
            text-align: center;
            margin-top: 50px;
        }
        button {
            padding: 10px 20px;
            font-size: 20px;
        }
        /* Snake Game Styles */
        #snakeGame {
            margin: 20px auto;
            border: 2px solid #000;
            background-color: #f0f0f0;
        }
        #snakeGameCanvas {
            background-color: #333;
        }
    </style>
</head>
<body>
    <!-- Snake Game -->
    <div class="game-container">
        <h1>Snake Game</h1>
        <button id="startSnakeButton">Start Snake Game</button>
        <div id="snakeGame" style="display:none;">
            <canvas id="snakeGameCanvas" width="400" height="400"></canvas>
        </div>
    </div>

    <script>
        // Snake Game Logic
        document.getElementById('startSnakeButton').addEventListener('click', function () {
            document.getElementById('snakeGame').style.display = 'block';
            startSnakeGame();
        });

        function startSnakeGame() {
            const canvas = document.getElementById('snakeGameCanvas');
            const ctx = canvas.getContext('2d');

            const gridSize = 20;
            let snake = [{ x: 200, y: 200 }];
            let direction = { x: gridSize, y: 0 };
            let nextDirection = direction;
            let fruit = { x: getRandomGridPosition(), y: getRandomGridPosition() };
            let score = 0;

            // Smooth movement with continuous updating
            document.addEventListener('keydown', function (e) {
                switch (e.key) {
                    case 'w':
                        if (direction.y === 0) nextDirection = { x: 0, y: -gridSize };
                        break;
                    case 'a':
                        if (direction.x === 0) nextDirection = { x: -gridSize, y: 0 };
                        break;
                    case 's':
                        if (direction.y === 0) nextDirection = { x: 0, y: gridSize };
                        break;
                    case 'd':
                        if (direction.x === 0) nextDirection = { x: gridSize, y: 0 };
                        break;
                }
            });

            function getRandomGridPosition() {
                return Math.floor(Math.random() * (canvas.width / gridSize)) * gridSize;
            }

            function drawSnake() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);

                ctx.fillStyle = 'lime';
                snake.forEach(part => {
                    ctx.fillRect(part.x, part.y, gridSize, gridSize);
                });

                ctx.fillStyle = 'red';
                ctx.fillRect(fruit.x, fruit.y, gridSize, gridSize);

                ctx.fillStyle = 'white';
                ctx.font = '20px Arial';
                ctx.fillText('Score: ' + score, 10, 20);
            }

            function updateSnake() {
                const newHead = { x: snake[0].x + nextDirection.x, y: snake[0].y + nextDirection.y };

                // Check if the snake eats the fruit
                if (newHead.x === fruit.x && newHead.y === fruit.y) {
                    score++;
                    fruit = { x: getRandomGridPosition(), y: getRandomGridPosition() };
                } else {
                    snake.pop(); // Remove the last segment if no fruit is eaten
                }

                // Check if the snake hits the walls or itself
                if (
                    newHead.x < 0 || newHead.x >= canvas.width ||
                    newHead.y < 0 || newHead.y >= canvas.height ||
                    snake.some(part => part.x === newHead.x && part.y === newHead.y)
                ) {
                    resetGame();
                    return;
                }

                direction = nextDirection;  // Smooth transition of direction
                snake.unshift(newHead);     // Add new head to the front of the snake
            }

            function resetGame() {
                snake = [{ x: 200, y: 200 }];
                direction = { x: gridSize, y: 0 };
                nextDirection = direction;
                fruit = { x: getRandomGridPosition(), y: getRandomGridPosition() };
                score = 0;
                alert('Game Over! Your score: ' + score);
            }

            function gameLoop() {
                updateSnake();
                drawSnake();
                setTimeout(gameLoop, 100); // 100ms interval for smooth movement
            }

            gameLoop();
        }
    </script>
</body>
</html>

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>RGB Color Creator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }
    .color-box {
      width: 200px;
      height: 200px;
      margin: 20px auto;
      border: 2px solid #000;
      background-color: rgb(0, 0, 0);
    }
    .slider-container {
      width: 300px;
      margin: 10px auto;
    }
    .slider {
      width: 100%;
    }
    .value-display {
      margin-top: 20px;
      font-size: 20px;
    }
  </style>
</head>
<body>

  <h1>RGB Color Creator</h1>

  <div class="color-box" id="colorBox"></div>

  <div class="slider-container">
    <label for="red">Red: <span id="redValue">0</span></label>
    <input type="range" id="red" class="slider" min="0" max="255" value="0" oninput="updateColor()">
  </div>

  <div class="slider-container">
    <label for="green">Green: <span id="greenValue">0</span></label>
    <input type="range" id="green" class="slider" min="0" max="255" value="0" oninput="updateColor()">
  </div>

  <div class="slider-container">
    <label for="blue">Blue: <span id="blueValue">0</span></label>
    <input type="range" id="blue" class="slider" min="0" max="255" value="0" oninput="updateColor()">
  </div>

  <div class="value-display">
    RGB Color Code: <span id="rgbValue">rgb(0, 0, 0)</span>
  </div>

  <script>
    function updateColor() {
      // Get RGB values from sliders
      let red = document.getElementById('red').value;
      let green = document.getElementById('green').value;
      let blue = document.getElementById('blue').value;

      // Update the color box background
      let rgbColor = `rgb(${red}, ${green}, ${blue})`;
      document.getElementById('colorBox').style.backgroundColor = rgbColor;

      // Display the RGB values
      document.getElementById('redValue').textContent = red;
      document.getElementById('greenValue').textContent = green;
      document.getElementById('blueValue').textContent = blue;
      document.getElementById('rgbValue').textContent = rgbColor;
    }
  </script>

</body>
</html>

