# IDD-Fa19-Lab5

[Video of Box in a Box](https://youtu.be/lfqHp2G4mcA)


```
#include <Servo.h>

Servo myservo;  // create servo object to control a servo
// twelve servo objects can be created on most boards

int pos = 0;    // variable to store the servo position
int buttonState = 0;
void jack() {
  for (pos = 0; pos <= 110; pos += 1) { // goes from 0 degrees to 180 degrees
    // in steps of 1 degree
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
  delay(1100);
  for (pos = 110; pos >= 0; pos -= 1) { // goes from 180 degrees to 0 degrees
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
}

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
  pinMode(2,INPUT);
}

void loop() {
  buttonState = digitalRead(2);
  if (buttonState == HIGH) {
    // jack!
    jack();
  }
}
```
