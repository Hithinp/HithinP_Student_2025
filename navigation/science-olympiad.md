---
layout: base
title: science olympiad
permalink: /science-olympiad
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Science Olympiad - Fluid Dynamics Simulation</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.0/p5.js"></script>
  <style>
    body { margin: 0; font-family: Arial, sans-serif; }
    canvas { display: block; margin: 20px auto; border: 2px solid #333; }
    .content { max-width: 800px; margin: 0 auto; padding: 20px; text-align: center; }
    h1 { color: #2c3e50; }
    p { color: #34495e; line-height: 1.6; }
  </style>
</head>
<body>
  <div class="content">
    <h1>Science Olympiad</h1>
    <p>
      Welcome to the Science Olympiad page! Below is an interactive fluid dynamics simulation.
      Click and drag to add fluid to the simulation and watch it spread out.
    </p>
  </div>

  <script>
    let grid;
    let nextGrid;
    const rows = 50;
    const cols = 50;
    const resolution = 10;

    function setup() {
      createCanvas(cols * resolution, rows * resolution);
      grid = createGrid(rows, cols);
      nextGrid = createGrid(rows, cols);
    }

    function draw() {
      background(0);

      // Update the grid
      for (let i = 1; i < rows - 1; i++) {
        for (let j = 1; j < cols - 1; j++) {
          // Simple diffusion (spreading out)
          nextGrid[i][j] = (
            grid[i - 1][j] +
            grid[i + 1][j] +
            grid[i][j - 1] +
            grid[i][j + 1]
          ) / 4;
        }
      }

      // Swap grids
      let temp = grid;
      grid = nextGrid;
      nextGrid = temp;

      // Draw the grid
      for (let i = 0; i < rows; i++) {
        for (let j = 0; j < cols; j++) {
          let val = grid[i][j];
          fill(val * 255);
          noStroke();
          rect(j * resolution, i * resolution, resolution, resolution);
        }
      }

      // Add a source of fluid on mouse drag
      if (mouseIsPressed) {
        let i = floor(mouseY / resolution);
        let j = floor(mouseX / resolution);
        if (i >= 0 && i < rows && j >= 0 && j < cols) {
          grid[i][j] = 1.0;
        }
      }
    }

    function createGrid(rows, cols) {
      let grid = new Array(rows);
      for (let i = 0; i < rows; i++) {
        grid[i] = new Array(cols).fill(0);
      }
      return grid;
    }
  </script>
</body>
</html>