# HampsterWheel
## Goal
Make a car drive in a wheel, and possibly make it faster, and or make it so when you push the button it keeps going and then you press it again it stops.
## link to CAD
[hampster wheel](https://cvilleschools.onshape.com/documents/19dc710f95885de48e050788/w/5ada67a2b91b82b563d96b96/e/759dc6aaf90706040678159a)
## Psudo code
/*
Servo library stuff
Stuff for one button and one potentiometer
*/

void setup() {
    // turn on button servo and potentiometer
}

void loop() {
    // read the button
    
    // button toggle code
   // https://www.arduino.cc/en/tutorial/switch
    // first time the button is pressed spin the wheel
    // potentiometer control servo speed
    
    // second time the button is pressed stop spin
}
## Final Code
#include <Servo.h>;
 
 // pushbutton pin
 const int buttonPin = 8;
 // servo pin
 const int servoPin = 3;
 Servo servo;
//create a variable to store a counter and set it to 0
int counter = 0;
void setup()
{
  servo.attach (servoPin);
  
  // Set up the pushbutton pins to be an input:
  pinMode(buttonPin, INPUT);
}
void loop()
{
 // local variable to hold the pushbutton states
  int buttonState;  
  //read the digital state of buttonPin with digitalRead() function and store the           //value in buttonState variable
  buttonState = digitalRead(buttonPin);
  //if the button is pressed increment counter and wait a tiny bit to give us some          //time to release the button
  if (buttonState == LOW) // light the LED
  {
    counter++;
    delay(150);
  }
  if(counter == 0)
    servo.write (20);  // zero degrees
  else if(counter == 1)
    servo.write(90);
  else if(counter == 2)
    servo.write (150); 
  else if(counter == 3)  
    servo.write (180);
  //else reset the counter to 0 which resets thr servo to 0 degrees
  else
   counter = 0;
}
