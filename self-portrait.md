/*
Yupu Chen
First assignment, self-portrait
Intro to IM, Fall 2023
*/

function setup() {
  createCanvas(600, 600);
  background(220);
}

let move = 0;
let speed = 1;

function draw() {
  print(mouseX + "," + mouseY);

  background(220);

  // the sky
  stroke(135, 206, 250);
  fill(135, 206, 250);
  rect(0, 0, width, 250);

  // the sea
  stroke(65, 105, 225);
  fill(65, 105, 225);
  rect(0, 250, width, 120);

  // the beach
  stroke(194, 178, 128);
  fill(1984, 178, 128);
  rect(0, 370, width, 230);

  fill(255);
  stroke(255);

  rect(100, 420, 185, 25); // draw the table

  // draw three clouds
  noStroke();
  fill(255);

  ellipse(173 + move, 88, 100, 30);
  ellipse(173 + move, 80, 40, 45);
  ellipse(300 - move, 180, 100, 30);
  ellipse(300 - move, 172, 40, 45);
  ellipse(500 + move, 120, 100, 30);
  ellipse(500 + move, 112, 40, 45);
  move += speed;
  if (move > 50 || move < -40) {
    speed *= -1;
  }

  //draw the table's legs
  stroke(255);
  strokeWeight(4);
  line(120, 448, 165, 544);
  line(165, 448, 120, 544);
  line(220, 448, 265, 544);
  line(265, 448, 220, 544);
  stroke(0);
  strokeWeight(1);

  let tray = 10;
  // draw the coffee tray
  stroke(255);

  if (246 < mouseX && mouseX < 266 && 400 < mouseY && mouseY < 414) {
    beginShape();
    curveVertex(220, 414);
    curveVertex(220 - tray, 414);
    curveVertex(228 - tray, 418);
    curveVertex(247 - tray, 418);
    curveVertex(257 - tray, 418);
    curveVertex(265 - tray, 414);
    curveVertex(265 - tray, 414);
    endShape();
    stroke(0);

    stroke(255);
    rect(224, 400, 20, 14);

    heat(230);
    heat(240);
    heat(250);
  } else {
    beginShape();
    curveVertex(233, 414);
    curveVertex(233, 414);
    curveVertex(241, 418);
    curveVertex(260, 418);
    curveVertex(270, 418);
    curveVertex(278, 414);
    curveVertex(278, 414);
    endShape();
    stroke(0);

    stroke(255);
    rect(246, 400, 20, 14);

    heat(250);
    heat(260);
    heat(270);
  }

  stroke(0);

  //draw the chair
  line(450, 350, 440, 480);
  line(350, 480, 440, 480);
  line(375, 480, 360, 544);
  line(420, 480, 435, 544);

  // draw the body
  fill(232, 190, 172);
  ellipse(395, 400, 60, 150);
  circle(395, 314, 50);
  rect(330, 450, 70, 20, 10);
  rect(330, 450, 20, 80, 10);
  rect(320, 390, 70, 20, 10);

  fill(255);
}

function heat(xcoord) {
  noFill();
  beginShape();
  curveVertex(xcoord, 370);
  curveVertex(xcoord, 370);
  curveVertex(xcoord - 5, 380);
  curveVertex(xcoord, 390);
  curveVertex(xcoord - 5, 395);
  curveVertex(xcoord - 5, 395);
  endShape();
}
