# creative-coding-mothersday
A Creative Introduction to Coding - Mother's Day

## Learning Objectives

In this workshop, we will cover the following:

 - We'll talk about what programming is and cover some essentials concepts including variables, loops, data structures (arrays), ‘if’ statements and functions.
 - Learn the what an Arduino is and how it differs from a laptop computer.
 - Set up and programming of the Arduino, which will include basic functions to draw shapes, display text and work with touch.

 ## Setting Up

1. Head to this webpage to get set up for the Arduino workshop:  https://www.arduino.cc/en/Main/Software
2. ![alt text](/images/Screen1.png)
3. ![alt text](/images/Screen2.png)
4. ![alt text](/images/Screen3.png)
5. ![alt text](/images/Screen4.png)
6. ![alt text](/images/Screen5.png)
7. ![alt text](/images/Screen6.png)
8. ![alt text](/images/Screen7.png)

***

 ## Activity 1: What is programming?
Programming is when you write out instructions and then give them to a machine.
The machine then knows what to do based on what you’ve written.

Let's have a look inside:

 #### Hardware:
Electrical/mechanical parts.

 #### Software:
Instructions/ programs.

 #### CPU:
Extremely fast at calculating things but has a hard time remembering anything.

 #### Mass Storage:
For remembering things long term (ie: photos/game levels etc.)
Bad thing is that it’s extremely slow.

 #### GPU:
Renders images, animations and video for the computer's screen.

 #### RAM:
Works between mass storage and CPU delivering immediate information between the two. But when you turn off the computer it forgets everything.

 #### ROM:
Includes all of the info you don’t want to ever delete from the computer. (ie: how to start the computer).

***

 ## Activity 2: What is an Arduino?

Arduinos are used for building electronic projects. An Arduino consists of a physical programmable circuit board (microcontroller) and a piece of software that runs on your computer.
You write the code on your computer and upload it onto the Arduino which can then interact with many things like: TVs, cameras, buttons,  speakers, phones, lights and much more...

***

 ## Activity 3: What's the Difference between a Laptop and an Arduino?

 Computers are pretty limited to the types inputs receive and to how they can output the code. Arduinos are much more flexible.

***

 ## Activity 4: Basic Programming Concepts

 #### Variables:
 A variable is essentially a container that holds some kind of information.\
 ```var favouriteColour = “green”```\
 ```var somePlanets = [“mercury”, “venus”, “earth”, “mars”]```

 #### Strings:
 Used to represent text/words. They are always captured in quotes.\
 ```"Code Like a Girl"```\
 ```“I love peanut butter and jam sandwiches.”```\
 ```"Elephant"```

 #### Control Structures:
 These are blocks of code that make decisions based on variables or other conditions.

 ##### IF statement:
 ```
if (some condition is true) {
 then do this
}
```
```
var day = “monday”
if (day == “monday”) {
    print “It’s the start of the week!”
}
```

 ##### IF/ELSE statement:
 ```
if (condition is true) {
  then do this
} else {
  do this instead
}
```
```
var day = “friday”
if (day == “monday”) {
    print “It’s the start of the week!”
} else {
    print “At least it’s not monday!”
}
```
 #### Data Structures:
 Store and organise your information/data so that the computer can easily access it.

 ##### Arrays:
 These are like lists with a way of identifying what item is in which position. These positions are referred to as the ‘index’ & the first position is always 0.

```
 var amazingProgrammers: [“Ada Lovelace”, “Grace Hopper”, “Jean Bartik”, “Mary Jackson”, “YOU!”]
                index:          0               1               2               3           4
```
 #### Compiling:
 Takes the code that we wrote and turns it into a language that the computer can understand.

 #### Include:
 Allows you to reuse chunks of code. You save them in a different file and then ‘include’ it in whichever project you’re working on.

 #### Functions:
 Sort of like an include but are specific to your project. They are blocks of code that can take in some information and often ‘do something’ like give/return a result.

***

 ## Activity 5: Getting Started with Programming Arduino

 ### Setup:
 ![alt text](/images/Arduino1.png)
 ![alt text](/images/Arduino2.png)

 ### Shapes

 #### Lines
 ```
 void drawLine(Xstart, Ystart, Xend, Yend, color);
 ```

 #### Squares and rectangles
 ```
 void drawRect(Xstart, Ystart, width, height, color);
 void fillRect(Xstart, Ystart, width, height, color);
 ```

 #### Circles
 ```
 void drawCircle(Xstart, Ystart, radius, color);
 void fillCircle(Xstart, Ystart, radius, color);
 ```

 #### Triangles
 ```
 void drawTriangle(X1, Y1, X2, Y2, X2, Y2, color);
 void fillTriangle(X1, Y1, X2, Y2, X2, Y2, color);
 ```

 #### Extras:

 **Fill background:** ```void fillScreen(color);```

 **Colors:**
  - ILI9341_BLACK
  - ILI9341_WHITE
  - ILI9341_PURPLE
  - ILI9341_BLUE
  - ILI9341_GREEN
  - ILI9341_ORANGE
  - ILI9341_YELLOW
  - ILI9341_RED
  - ILI9341_PINK
  - ILI9341_NAVY
  - ILI9341_DARKGREEN
  - ILI9341_DARKCYAN
  - ILI9341_MAROON
  - ILI9341_OLIVE
  - ILI9341_LIGHTGREY
  - ILI9341_DARKGREY
  - ILI9341_CYAN
  - ILI9341_MAGENTA
  - ILI9341_GREENYELLOW

 **Using the touchscreen:**
```
 if (ts.touched()) {
   blink(robotColour);
 }
 ```

 > ts is a library that we included to be able to use the `touched` method.

***

 ## Activity 6: Get Creative with Arduino

 You have been shown how to program an Arduino using different shapes and touch. Now, let's get creative and crazy and create your very own robot!!!
 If you need a frame of reference why not check out the code for our Code Like a Girl Robot:

  ```#include <Adafruit_GFX.h>
#include <SPI.h>
#include <Wire.h>
#include <Adafruit_ILI9341.h>
#include <Adafruit_FT6206.h>

Adafruit_FT6206 ts = Adafruit_FT6206();

// For the Adafruit shield, these are the default.
#define TFT_CS 10
#define TFT_DC 9

// Use hardware SPI (on Uno, #13, #12, #11) and the above for CS/DC
Adafruit_ILI9341 tft = Adafruit_ILI9341(TFT_CS, TFT_DC);

// Colour for robot
#define RobotColour ILI9341_PINK

// If using the breakout, change pins as desired
//Adafruit_ILI9341 tft = Adafruit_ILI9341(TFT_CS, TFT_DC, TFT_MOSI, TFT_CLK, TFT_RST, TFT_MISO);
void setup() {
  //initialise libraries

  Serial.begin(9600);
  tft.begin();
  ts.begin(40);

  if (!ts.begin(40)) {
    Serial.println("Unable to start touchscreen.");
  }
  else {
    Serial.println("Touchscreen started.");
  }

  tft.fillScreen(ILI9341_BLACK);
  tft.setRotation(1);
  drawRobot(RobotColour);
  drawLoveHeart(ILI9341_RED);
  writeText();
}

void writeText() {
  tft.setTextSize(2);
  tft.setCursor(200,40);
  tft.setTextColor(ILI9341_WHITE);
  tft.println("Hi!");
  tft.setCursor(200,55);
  tft.println("my name");
  tft.setCursor(200,70);
  tft.println("is Milly");
}

void drawRobotBackground(uint16_t colour) {
   // Head
  tft.fillRoundRect(50,50,140,80, 10, colour);

  // Neck
  tft.fillRect(115,130,20,30, colour);

  // Body
  tft.fillRoundRect(60,150,120,100, 16, colour);
}

void drawMouth() {
  // Mouth
  tft.drawLine(110,115,135,118, ILI9341_BLACK);
  tft.drawLine(110,116,135,119, ILI9341_BLACK);
  tft.drawLine(110,117,135,120, ILI9341_BLACK);
}

void drawLeftEye() {
  // Left eye
  tft.fillCircle(88,87,18,ILI9341_BLACK);
  tft.fillCircle(90,90,15,ILI9341_WHITE);

  // Pupils
  tft.fillCircle(90,90,8,ILI9341_BLACK);
  tft.fillCircle(92,92,2,ILI9341_WHITE);
}

void drawRightEye() {
   // Right eye
  tft.fillCircle(157,87,18,ILI9341_BLACK);
  tft.fillCircle(155,90,15,ILI9341_WHITE);

  // Pupils
  tft.fillCircle(155,90,8,ILI9341_BLACK);
  tft.fillCircle(153,92,2,ILI9341_WHITE);
}

void drawRobot(uint16_t colour) {
  drawRobotBackground(colour);
  drawLeftEye();
  drawRightEye();
  drawMouth();
}

uint16_t robotColour = ILI9341_DARKCYAN;

void loop() {

 // Wait for a touch
 if (ts.touched()) {
   Serial.println("touchy");

   // Make the eyes close
   blink(robotColour);

   // Make the heart beat
   drawLoveHeart(ILI9341_MAROON);

   // After a beat, redraw the eyes so they open again!
   delay(500);
   drawLeftEye();
   delay(100);
   drawRightEye();
   delay(100);

   // Make the screen black
   tft.fillScreen(ILI9341_BLACK);

   // Write a message!
   tft.setCursor(200,200);
   tft.println("Oh hi!!");

   // Redraw robot
   drawRobot(ILI9341_PINK);

   // And make the heart red.
   drawLoveHeart(ILI9341_RED);
 }

  // put your main code here, to run repeatedly:
  // delay(1000);
  // loveHeart(ILI9341_MAROON);
  // delay(1000);
  // loveHeart(ILI9341_RED);

}

// Interactions
void blink(uint16_t closedColour) {

  // Left eye
  tft.fillCircle(90,90,15,closedColour);
  Serial.println("Left eye blink");

  // Right eye
  tft.fillCircle(155,90,15,closedColour);
  Serial.println("Right eye blink");
}

void drawLoveHeart(uint16_t colour) {
  int x0 = 115;
  int x1 = 135;
  int y = 185;
  int r = 10;

  tft.fillCircle(x0,y,r,colour);
  tft.fillCircle(x1,y,r,colour);
  tft.fillTriangle(x0-r-1,y,x1+r,y,x0+r+1,y+(r*3), colour);
  Serial.println("Heartbeat");
}
```

***

 ## Wrap Up

 - We've covered a lot today! As a refresher have a peak at the **[Learning Objectives](#learning-objectives)** up top.
 - What are the various high level parts of a computer that you can remember?
 - Would you be able to explain to a friend how Arduinos differ from Laptops and why they're so awesome?
 - See if you can list of all the different programming concepts we learned today. There were about 7.

***

 ## What's Next?

 - If you're interested in learning more about the Arduino, check out their [website](https://www.arduino.cc/). It's full of great info. What we've done today is only the tip of the iceberg. They are capable of so many cool things - really only limited to you and what amazing stuff you can imagine and create!

 - You could also check out the [Adafruit website](https://learn.adafruit.com/) for some inspiration.

 - If the coding side of things sparked an interest in learning more, there are many free online tools for learning different languages. Here are few to get your started:
   - [Codeschool](https://www.codeschool.com/)
   - [CodeAcademy](https://www.codecademy.com/)
   - [A new learn to code app from Google](https://9to5google.com/2018/04/19/google-area-120-grasshopper/)

 - Code Like a Girl always has great workshops running. [Keep in touch](https://codelikeagirl.org/events-workshops/) and we can send you the newsletter so you'll be one of the first to know about them!
