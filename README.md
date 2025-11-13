# Clash-Royal-V1.23
<!DOCTYPE html>
<html>
<head>
  <title>My First Game</title>
  <style>
    canvas { 
      background: #eee; 
      display: block; 
      margin: 0 auto; 
    }
  </style>
</head>
<body>
  <h2 style="text-align:center;">Use arrow keys to move the blue square!</h2>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
  <script src="script.js"></script>
</body>
</html>

const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');

let x = 175; // starting X position
let y = 175; // starting Y position
const size = 50; // square size

function draw() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  ctx.fillStyle = 'blue';
  ctx.fillRect(x, y, size, size);
}

document.addEventListener('keydown', (e) => {
  const step = 10;
  if (e.key === 'ArrowUp' && y > 0) y -= step;
  if (e.key === 'ArrowDown' && y < canvas.height - size) y += step;
  if (e.key === 'ArrowLeft' && x > 0) x -= step;
  if (e.key === 'ArrowRight' && x < canvas.width - size) x += step;
  draw();
});

draw();

