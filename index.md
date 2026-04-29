# Hello World

This is my home page! My name is Jeremy Garcia and I am a student at [Cal State Fullerton](http://www.fullerton.edu/). My major is Computer Science.

## Computer Science Projects

My GitHub page is https://github.com/JG-Fullerton.

### CPSC 120

* Lab 6

    Lab 6 was one of my favorite labs because it helped me understand how functions can make a program easier to organize. I liked working on the Blackjack part because it connected programming to a real card game. I learned how to break a larger problem into smaller functions and test each part carefully.

* Lab 10

    Lab 10 was one of my favorite labs because it helped me practice using loops and organized problem solving. I liked seeing how small pieces of code could work together to create a complete program. I learned how to debug errors more carefully and improve my code step by step.

* Lab 12

    Lab 12 was one of my favorite labs because it gave me a chance to be more creative with programming. I liked that the final result could be shown visually on my portfolio page. I learned how programming can be used to create images and demonstrate my work online.

## Mini Paint

Use your mouse to draw in the box below.

<canvas id="paintCanvas" width="600" height="400" style="border:2px solid black; background:white;"></canvas>

<br>

<button onclick="clearCanvas()">Clear</button>

<script>
const canvas = document.getElementById("paintCanvas");
const ctx = canvas.getContext("2d");

let painting = false;

canvas.addEventListener("mousedown", startDraw);
canvas.addEventListener("mouseup", stopDraw);
canvas.addEventListener("mousemove", draw);
canvas.addEventListener("mouseleave", stopDraw);

function startDraw(event) {
  painting = true;
  draw(event);
}

function stopDraw() {
  painting = false;
  ctx.beginPath();
}

function draw(event) {
  if (!painting) return;

  const rect = canvas.getBoundingClientRect();

  ctx.lineWidth = 4;
  ctx.lineCap = "round";
  ctx.strokeStyle = "black";

  ctx.lineTo(event.clientX - rect.left, event.clientY - rect.top);
  ctx.stroke();
  ctx.beginPath();
  ctx.moveTo(event.clientX - rect.left, event.clientY - rect.top);
}

function clearCanvas() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
}
</script>
