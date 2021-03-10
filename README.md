var colorPicker = {
    x: 20,
    y: 370,
    size: 30,
};

var weight = {
    x: 20,
    y: 30,
    size: 30
};

var paint = {
    size: 20,
    textX: 250,
    textY: 18
};

var textY = 399;
var fillColor = color(255, 255, 255);
strokeWeight(5);
line(0, 50, 400, 50);//top divider line
line(0, 350, 400, 350);//bottom divider line

noStroke();

textSize(9);

fill(255, 0, 0);//red
ellipse(colorPicker.x, colorPicker.y, colorPicker.size, colorPicker.size);//red circle
text("RED", 10, textY);

fill(255, 102, 0);//orange color
ellipse(colorPicker.x*3, colorPicker.y, colorPicker.size, colorPicker.size);//orange circle
text("ORANGE", 40, textY);

fill(247, 255, 0);//yellow color
ellipse(colorPicker.x*5, colorPicker.y, colorPicker.size, colorPicker.size);//yellow circle
text("YELLOW", 82, textY);

fill(0, 255, 17);//green color
ellipse(colorPicker.x*7, colorPicker.y, colorPicker.size, colorPicker.size);//green circle
text("GREEN", 124, textY);

fill(30, 0, 255);//blue color
ellipse(colorPicker.x*9, colorPicker.y, colorPicker.size, colorPicker.size);//blue circle
text("BLUE", 169, textY);

fill(170, 0, 255);//puple color
ellipse(colorPicker.x*11, colorPicker.y, colorPicker.size, colorPicker.size);//purple circle
text("PURPLE", 202, textY);

fill(255, 0, 255);//pink color
ellipse(colorPicker.x*13, colorPicker.y, colorPicker.size, colorPicker.size);//pink circle
text("PINK", 250, textY);

fill(163, 65, 0);//brown color
ellipse(colorPicker.x*15, colorPicker.y, colorPicker.size, colorPicker.size);//brown circle
text("BROWN", 283, textY);

fill(0, 0, 0);//black color
ellipse(colorPicker.x*17, colorPicker.y, colorPicker.size, colorPicker.size);//black circle
text("BLACK", 325, textY);

stroke(0, 0, 0);
strokeWeight(1);
fill(255, 255, 255);//eraser color
ellipse(colorPicker.x*19, colorPicker.y, colorPicker.size, colorPicker.size);//white circle
fill(0, 0, 0);//text color
text("Eraser", 365, textY);

ellipse(weight.x, weight.y, 10, 10);//weight 10px
text("10", weight.x - 5, weight.y/3);

ellipse(weight.x*2, weight.y, 15, 15);//weight 15px
text("15", weight.x*2 - 5, weight.y/3);

ellipse(weight.x*3.25, weight.y, 20, 20);//weight 20px
text("20", weight.x*3.25 - 5, weight.y/3);

ellipse(weight.x*4.75, weight.y, 25, 25);//weight 25px
text("25", weight.x*4.75 - 5, weight.y/3);

ellipse(weight.x*6.5, weight.y,30,30);//weight 30px
text("30", weight.x*6.5 - 5, weight.y/3);

textSize(15);
text("Color chosen:", paint.textX, paint.textY);
text("Paint weight:", paint.textX + 7, 40);

noStroke();
draw = function() {
    //these if statements conrtrol the paint size and the text, "Paint weight:"
    if (mouseIsPressed && mouseX >= weight.x - 5 && mouseX <= weight.x + 5 && mouseY >= weight.y - 5 && mouseY <= weight.y + 5) {
        paint.size = 10;
        fill(255, 255, 255);
        rect(paint.textX + 107, 28, 17, 12);
        fill(0, 0, 0);
        text(paint.size, paint.textX + 107, 40);
    
    }else if (mouseIsPressed && mouseX >= weight.x*2 - 7.5 && mouseX <= weight.x*2 + 7.5 && mouseY >= weight.y - 7.5 && mouseY <= weight.y + 7.5) {
        paint.size = 15;
        fill(255, 255, 255);
        rect(paint.textX + 107, 28, 17, 12);
        fill(0, 0, 0);
        text(paint.size, paint.textX + 107, 40);
    
    }else if (mouseIsPressed && mouseX >= weight.x*3.25 - 10 && mouseX <= weight.x*3.25 + 10 && mouseY >= weight.y - 10 && mouseY <= weight.y + 10) {
        paint.size = 20;
        fill(255, 255, 255);
        rect(paint.textX + 107, 28, 17, 12);
        fill(0, 0, 0);
        text(paint.size, paint.textX + 107, 40);
    
    }else if (mouseIsPressed && mouseX >= weight.x*4.75 - 12.5 && mouseX <= weight.x*4.75 + 12.5 && mouseY >= weight.y - 12.5 && mouseY <= weight.y + 12.5) {
        paint.size = 25;
        fill(255, 255, 255);
        rect(paint.textX + 107, 28, 17, 12);
        fill(0, 0, 0);
        text(paint.size, paint.textX + 107, 40);
        
    }else if (mouseIsPressed && mouseX >= weight.x*6.5 - 15 && mouseX <= weight.x*6.5 + 15 && mouseY >= weight.y - 15 && mouseY <= weight.y + 15) {
        paint.size = 30;
        fill(255, 255, 255);
        rect(paint.textX + 107, 28, 17, 12);
        fill(0, 0, 0);
        text(paint.size, paint.textX + 107, 40);
    
    }
    
    //these if statements control when the paint stops on the canvas so that the paint doesn't go over the divider lines.
    if (paint.size === 10 && mouseIsPressed && mouseY > 56 && mouseY < 345) {
        fill(fillColor);
        ellipse(mouseX, mouseY, paint.size, paint.size);
    
    }else if (paint.size === 15 && mouseIsPressed && mouseY > 59 && mouseY < 342) {
        fill(fillColor);
        ellipse(mouseX, mouseY, paint.size, paint.size);
    
    }else if (paint.size === 20 && mouseIsPressed && mouseY > 61 && mouseY < 340) {
        fill(fillColor);
        ellipse(mouseX, mouseY, paint.size, paint.size);
    
    }else if (paint.size === 25 && mouseIsPressed && mouseY > 64 && mouseY < 337) {
        fill(fillColor);
        ellipse(mouseX, mouseY, paint.size, paint.size);
    
    }else if (paint.size === 30 && mouseIsPressed && mouseY > 66 && mouseY < 335) {
        fill(fillColor);
        ellipse(mouseX, mouseY, paint.size, paint.size);
    
    }
    
    //these if statements control the color of the paint and the text, "Color chosen:"
    if(mouseX > 5 && mouseX < 35 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(255, 0, 0);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 45 && mouseX < 75 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(255, 102, 0);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 85 && mouseX < 115 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(247, 255, 0);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 125 && mouseX < 155 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(0, 255, 17);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 165 && mouseX < 195 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(30, 0, 255);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 205 && mouseX < 235 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(170, 0, 255);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 245 && mouseX < 275 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(255, 0, 255);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 285 && mouseX < 315 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(163, 65, 0);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 325 && mouseX < 355 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(0, 0, 0);
        fill(fillColor);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }else if(mouseX > 365 && mouseX < 395 && mouseY > colorPicker.y - 15 && mouseY < colorPicker.y + 15 && mouseIsPressed) {
        fillColor = color(255, 255, 255);
        fill(fillColor);
        strokeWeight(10);
        ellipse(paint.textX + 115, paint.textY - 4, 20, 20);
    
    }
};
