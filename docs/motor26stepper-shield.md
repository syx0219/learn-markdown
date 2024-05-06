---
title: Motor&Stepper SDshield
---

## Description
-----------

It would always a problem to drive motors for Arduino beginners. If you DIY your mobile platform, you will 2 DC motors at least, and control their speed&amp; direction of rotaton, because you will want your platform forward, turn back, turn left or right. Besides, motors always needs large current, so, you will need some modules to help you control the large current, with microtrller sucha Arduino.  
So, what you need in such application is a motor driver board. Elecrow has prepard such a Shield board for you. It is Arduino compatible, you can just plug it onto your Arduino or Crowduino to start your mobile application. Actually, We had release the Motor Shield one years ago, but today, i will introduce you the Motor$ Stepper Shield, which is the upgrade version of the previous Motor Shield.

**Model: (Discontinued)**  
![Motor& Stepper shield1.png](https://wiki.elecrow.com/images/thumb/9/90/Motor%26_Stepper_shield1.png/500px-Motor%26_Stepper_shield1.png){ loading=lazy }
![Motor& Stepper shield2.jpg](https://wiki.elecrow.com/images/thumb/5/57/Motor%26_Stepper_shield2.jpg/500px-Motor%26_Stepper_shield2.jpg){ loading=lazy }

As the same as the Motor Shield, this Motor&amp; Stepper shield can be used to drive 2 DC motors or a 4-wire stepper, the max driver can be upto 2A. Contrast to the motor shield, the new generation Motor&amp; Stepper Shield has the follow advantage:    
**Stackable Design:** The Motor&amp; Stepper Shield uses the L298P and lower heatsink, to make the Motor&amp; Stepper Shield stackable.  
**Smaller Current Resistance:** The Motor&amp; Stepper Shield uses smaller current resistance, which is 0.5 ohm, 5W. It can support 3A current at max, which meets the shield’s specifications.  
**Switch to power on/off:** The switch helps to power on/off the Motor&amp; Stepper Shield, which make it more convenient in using, especially in your building&amp; debugging.  
**Control Selector Removed:** To avoid any confusion, especially for beginner, the control selector removed, need 3 Arduino Pins to control each motor.  
**More Reliable layouts:** To ensure the L298P works in best status, the PCB layout meets the max current 2A requirments.  
**More LED Indicators:** There are 8 LEDs to indicate the Power, RST, Speed, Directions, to help user get the detailed information of working status.

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

<table border="1" cellspacing="0" width="100%">
  <tbody>
    <tr>
      <th scope="col" align="center">Item</th>
      <th scope="col" align="center">Min</th>
      <th scope="col" align="center">Typical</th>
      <th scope="col" align="center">Max</th>
      <th scope="col" align="center">Unit</th>
    </tr>
    <tr>
      <th scope="row">Operating Voltage</th>
      <td align="center">4.5</td>
      <td align="center">5.0</td>
      <td align="center">5.5</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row">Drive Voltage</th>
      <td align="center">6</td>
      <td align="center">12</td>
      <td align="center">15</td>
      <td align="center">V</td>
    </tr>
    <tr>
      <th scope="row">Output Current</th>
      <td align="center">/</td>
      <td align="center">/</td>
      <td align="center">2</td>
      <td align="center">A</td>
    </tr>
    <tr>
      <th scope="row">Dimension</th>
      <td align="center" colspan="3">68.5(L)x55.0(W)x23.5(H)</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row">Weight</th>
      <td align="center" colspan="3"> </td>
      <td align="center">g</td>
    </tr>
  </tbody>
</table>

## Interface Function
------------------

![Motor& Stepper Shield.jpg](https://wiki.elecrow.com/images/thumb/9/9a/Motor%26_Stepper_Shield.jpg/800px-Motor%26_Stepper_Shield.jpg){ loading=lazy }  
**Motor Supply Voltage:** ------&gt; External Power supply for the Motor Shield, Could be 6~22V depending on the motor you used   
**Power Indicator:** ------&gt; LED indicator for the external power supply.  
**H-Bridge Driver:** ------&gt; 8 High-power MOSFET to build H-Bridge.  
**Motor\_1&amp;2 Connector:** ------&gt; Connect your motors here, the H-Bridge motor shield can drive 2 motors simultaneously, of course it can also drive a 4-wire stepper.  
**Motor Control Pins:** ------&gt; Arduino pins used to control the motor direction&amp;speed as belows:  

## Usage
-----

### **Pin Routing**

Plug the motor shield onto Arduino or Crowduino, the motor shield pins connects Arduino pins as below:

<table border="1" cellspacing="0">
  <tbody>
    <tr>
      <td style="width: 30%" scope="col" align="center"><b>Motor</b></td>
      <td scope="col" align="center"><b>Pin Name</b></td>
      <td scope="col" align="center"><b>Arduino pin</b></td>
      <td scope="col" align="center"><b>Description</b></td>
    </tr>
    <tr>
      <td rowspan="3" align="center"><b>Motor_1</b></td>
      <td align="center">IN1</td>
      <td align="center">D8</td>
      <td rowspan="2">D8=0,D11=1 -&gt; clockwise;<p>D8=1,D11=0 -&gt; anticlockwise;</p></td>
    </tr>
    <tr>
      <td align="center">IN2</td>
      <td align="center">D11</td>
    </tr>
    <tr>
      <td align="center">ENA</td>
      <td align="center">D9</td>
      <td>Motor_1 speed control, duty can be 0%~100%</td>
    </tr>
    <tr>
      <td rowspan="3" align="center"><b>Motor_2</b></td>
      <td align="center">IN3</td>
      <td align="center">D12</td>
      <td rowspan="2">D12=0,D13=1 -&gt; clockwise;<p>D12=1,D13=0 -&gt; anticlockwise;</p></td>
    </tr>
    <tr>
      <td align="center">IN4</td>
      <td align="center">D13</td>
    </tr>
    <tr>
      <td align="center">ENB</td>
      <td align="center">D10</td>
      <td>Motor_2 speed control, duty can be 0%~100%</td>
    </tr>
  </tbody>
</table>

### **Heatsink**

There is a heatsink in the pack, if your drive current larger than 1A, you can adhere the heatsink on to the dirver IC L298P easily with the 3M glue at the bottom.  
![Motor&Stepper Shield heatsink.jpg](https://wiki.elecrow.com/images/thumb/b/be/Motor%26Stepper_Shield_heatsink.jpg/400px-Motor%26Stepper_Shield_heatsink.jpg){ loading=lazy }

### **Control 2DC motors**

With this Motor&amp;Stepper Shield, you can control 2 DC motors simultaneously. 6 Arduino pins are needed to control the 2 DC motors. D8/D9/D11 are for motor\_1 controlling, and D10/D12/D13 are for the motor\_2 controlling.  
![Motor&Stepper Shield DC Connection.jpg](https://wiki.elecrow.com/images/thumb/b/bb/Motor%26Stepper_Shield_DC_Connection.jpg/400px-Motor%26Stepper_Shield_DC_Connection.jpg){ loading=lazy }  
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

### **Drive Current Measurement**

When using the shield to drive motors, sometimes you will want to get the actual drive current, for example, if the DC motors get locked by something, the drive current will get very large, maybe destroy the platform and DC motors. There are 2 current sample resistor on the motor shield, with resistance 0.5 ohm, with these resistor you can easily get the driver curernt.

```
void setup() {                
  // initialize the direction control pins as an output.
  pinMode(8, OUTPUT);    
  pinMode(11, OUTPUT); 
  pinMode(12, OUTPUT); 
  pinMode(13, OUTPUT);  
  // initialize the speed control pins as an output.
  pinMode(9, OUTPUT);     
  pinMode(10, OUTPUT);  
   
  Serial.begin(9600); //initilize the serial port;
}

void loop() {
  
    // Define the motor_1 direction;
    digitalWrite(8, HIGH);   
    digitalWrite(11, LOW); 
   //  Define the motor_1 speed;
    //analogWrite(9,100);
    digitalWrite(9, HIGH); 
    
    // Define the motor_1 direction;    
    digitalWrite(12, HIGH); 
    digitalWrite(13, LOW); 
    //  Define the motor_1 speed;
    //analogWrite(10,150);
    digitalWrite(10, HIGH); 
    
    delay(1000); //wait for one second;
    //Detect the drive current;
    
    int sensor1= analogRead(A4);
    int sensor2= analogRead(A5);
    float motor1_current=(float)sensor1/1024*5/0.5;
    float motor2_current=(float)sensor2/1024*5/0.5;
    Serial.print("Drive current of motor_1 is: ");
    Serial.println(motor1_current);
    Serial.print("Drive current of motor_2 is: ");
    Serial.println(motor2_current);
    delay(4000);               // wait for 4 seconds
}
```


![Motor&Stepper Shield Current sample1.jpg](https://wiki.elecrow.com/images/thumb/2/22/Motor%26Stepper_Shield_Current_sample1.jpg/400px-Motor%26Stepper_Shield_Current_sample1.jpg){ loading=lazy }  
![Motor&Stepper Shield Current sample2.jpg](https://wiki.elecrow.com/images/thumb/e/e4/Motor%26Stepper_Shield_Current_sample2.jpg/400px-Motor%26Stepper_Shield_Current_sample2.jpg){ loading=lazy }  
In this program, Arduino get the voltage on Resistors for each channel. And then convert the voltage to current with Ohm's law. The Drive Current measurement would be useful in applications such as tire locking monitoring.  
As you see, the Arduino measured current with the sample resistor is very close to the multimeter measured current.