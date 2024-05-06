---
title: Crowtail- Motor Base Shield
---

## Description
-----------

It would always a problem to drive motors for Arduino beginners. If you DIY your mobile platform, you will 2 DC motors at least, and control their speed&amp; direction of rotaton, because you will want your platform forward, turn back, turn left or right. Besides, motors always needs large current, so, you will need some modules to help you control the large current, with microtrller sucha Arduino.  
So, what you need in such application is a motor driver board. Elecrow has prepard such a Shield board for you. It is Arduino compatible, you can just plug it onto your Arduino or Crowduino to start your mobile application. Actually, We had release the Motor Shield one years ago, but today, i will introduce you the Motor$ Stepper Shield, which is the upgrade version of the previous Motor Shield.  
**Model: [CT0069MBS](http://www.elecrow.com/crowtail-motor-base-shield-p-1533.html)**  
![Crowtail- Motor Base Shield.jpg](https://wiki.elecrow.com/images/thumb/3/32/Crowtail-_Motor_Base_Shield.jpg/500px-Crowtail-_Motor_Base_Shield.jpg){ loading=lazy }

## Features
--------

- The logic control voltage: 4.5~5.5V
- Motor Supply Voltage: 6~ 15V
- Measurement for driver current
- Drive part of the operating current Io: 2A
- Maximum power dissipation: 25W (T = 75 degree Celsius)
- Operating temperature: -25 degree Celsius ~ +130 degree Celsius
- Drive Type: Dual high-power H-bridge driver

## Specification
-------------

| Item | Min | Typical | Max | Unit |
|:-:|:-:|:-:|:-:|:-:|
| Operating Voltage | 4.5 | 5.0 | 5.5 | VDC |
| Drive Voltage | 6 | 12 | 15 | V |
| Output Current | / | / | 2 | A |
| Dimensions | 68.6(L)x54.6(W)x23.5(H) | cm |
| Weight |  | g |

## Interface Function
------------------

![123177.png](https://wiki.elecrow.com/images/thumb/f/f3/123177.png/600px-123177.png){ loading=lazy }  
**Motor Supply Voltage:** ------&gt; External Power supply for the Motor Shield, Could be 6~22V depending on the motor you used  
**Power Indicator:** ------&gt; LED indicator for the external power supply.   
**H-Bridge Driver:** ------&gt; 8 High-power MOSFET to build H-Bridge.  
**Motor\_1&amp;2 Connector:** ------&gt; Connect your motors here, the H-Bridge motor shield can drive 2 motors simultaneously, of course it can also drive a 4-wire stepper.  
**Motor Control Pins:** ------&gt; Arduino pins used to control the motor direction&amp;speed as belows:  

## Usage
-----

### **Pin Routing**

Plug the motor shield onto Arduino or Crowduino, the motor shield pins connects Arduino pins as below:

| **Motor** | **Pin Name** | **Arduino pin** | **Description** |
|:-:|:-:|:-:|:-:|
| **Motor\_1** | IN1 | D8 | D8=0,D11=1 -&gt; clockwise; D8=1,D11=0 -&gt; anticlockwise; |
| IN2 | D11 |
| ENA | D9 | Motor\_1 speed control, duty can be 0%~100% |
| **Motor\_2** | IN3 | D12 | D12=0,D13=1 -&gt; clockwise; D12=1,D13=0 -&gt; anticlockwise; |
| IN4 | D13 |
| ENB | D10 | Motor\_2 speed control, duty can be 0%~100% |

### **Heatsink**

There is a heatsink in the pack, if your drive current larger than 1A, you can adhere the heatsink on to the dirver IC L298P easily with the 3M glue at the bottom.

### **Control 2DC motors**

With this Motor Base Shield, you can control 2 DC motors simultaneously. 6 Arduino pins are needed to control the 2 DC motors. D8/D9/D11 are for motor\_1 controlling, and D10/D12/D13 are for the motor\_2 controlling.  
![Crowtail- Motor Base Shield DC Connection1.jpg](https://wiki.elecrow.com/images/thumb/1/15/Crowtail-_Motor_Base_Shield_DC_Connection1.jpg/500px-Crowtail-_Motor_Base_Shield_DC_Connection1.jpg){ loading=lazy }  
In this mode, 3 pins will be need to control each motor. 2 for rotate derection, and 1 for speed controlling.

```
const int pinI1=8;//I1
const int pinI2=11;//I2
const int speedpinA=9;//EA(PWM)to control the motor_1 speed
const int pinI3=12;//I3
const int pinI4=13;//I4
const int speedpinB=10;//EB(PWM]) to control the motor_2 speed
void setup()
{
    for(int i=0;i<20;i++)
    pinMode(i,OUTPUT); //set to output
}
void loop()
{
    Test_Load_Left();
    delay(3000);
    clean_Output();
    delay(1000);
    Test_Load_Right();
    delay(3000);
}
/*Set the motor1 clockwise and motor2 anticlockwise, with speed 150*/
void Test_Load_Left()
{
  analogWrite(speedpinA,150);
  analogWrite(speedpinB,150);
  digitalWrite(pinI4,HIGH);
  digitalWrite(pinI3,LOW);
  digitalWrite(pinI2,HIGH);
  digitalWrite(pinI1,LOW);
}
/*Set the motor1 clockwise and motor2 anticlockwise, with speed 100 */
void Test_Load_Right()
{
  analogWrite(speedpinA,100);
  analogWrite(speedpinB,100);
  digitalWrite(pinI1,HIGH);
  digitalWrite(pinI2,LOW);
  digitalWrite(pinI3,HIGH);
  digitalWrite(pinI4,LOW);
  }

/*Stop the motors */
void clean_Output()
{
  digitalWrite(speedpinA,LOW);// full PWM 255
  digitalWrite(speedpinB,LOW);
}
```

### **Stepper Control**

Connect a 4-wire stepper motor to motor shield refer to \[[ULN2003](./uln2003-stepper-motor-driver.md)\]  
There is a lib： Stepper.h in Arduino IDE, users can use this library to control 4-wire stepper as below program:

```
#include <Stepper.h>
const int stepsPerRevolution = 200;  // change this to fit the number of steps per revolution
                                    // for your motor
// initialize the stepper library on pins 8 through 13:
Stepper myStepper(stepsPerRevolution, 8,11,12,13);            
void setup() {
 // set the speed at 60 rpm:
 myStepper.setSpeed(60);
 // initialize the serial port:
 Serial.begin(9600);
 pinMode(9,OUTPUT);
 pinMode(10,OUTPUT);
 digitalWrite(9,HIGH);
 digitalWrite(10,HIGH);
}
void loop() {
 // step one revolution  in one direction:
  Serial.println("clockwise");
 myStepper.step(stepsPerRevolution);
 delay(500);
  // step one revolution in the other direction:
 Serial.println("counterclockwise");
 myStepper.step(-stepsPerRevolution);
 delay(500); 
}
```

The connected stepper would rotate with a changing direction for this progam.

## Resources
---------

- [Eagle files ](https://wiki.elecrow.comhttps://wiki.elecrow.com/images/0/03/Crowtail-Motor_Base_Shield_v1.0.zip)