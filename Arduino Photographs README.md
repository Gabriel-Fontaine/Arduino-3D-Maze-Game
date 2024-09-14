# Arduino-3D-Maze-Game

![Arduino Maze project photo 2](https://github.com/user-attachments/assets/a6f233e8-2cee-4f3c-b052-22506723ec15)
![Arduino Maze project photo 1](https://github.com/user-attachments/assets/58b2945d-2176-4daa-a2d5-c2c466c6266f)



Code which the arduinos used:

#include <Servo.h>
Servo XAxis;
Servo YAxis;

int joyY = 1;
int joyX = 0;

int joyVal;
int joyVal2;

int sensorValue = 0;
int sensorValue2 = 0;

void setup(){
 XAxis.attach(8);
 YAxis.attach(9);

 Serial.begin(9600);
}
void loop(){
 joyVal = analogRead(joyY);
 joyVal = map(joyVal, 0, 1023, 0, 45);
 XAxis.write(joyVal);

 joyVal2 = analogRead(joyX);
 joyVal2 = map(joyVal2, 0, 1023, 0, 45);
 YAxis.write(joyVal2);

//Data Print
sensorValue = analogRead(joyVal);
sensorValue2 = analogRead(joyVal2);
 Serial.print(joyVal);
 Serial.print(" ");
 Serial.println(joyVal2);
}
