---
title: Dual Channel H-Bridge Motor Shield
---

## Description
-----------

The Dual Channel H-Bridge Motor Shield is composed of 2 discrete MOSFET H-bridge, designed to drive two DC motor with max current 8A. It is made up of 8 N-channel MOSFET IRF3205S and 4 pcs of half bridge motor controller IR2104, to build 2 H-bridge. With this shield and the Arduino board, users can control and drive motors with a max current 8A@ 22V. The universal 7.4~11.1V lipo battery that are popular used in the remote car and model airplane can be applied as well.

The H-Bridge Motor Shield can be controlled by simply applying logic 0 or 1 to the direction pins for that motor and a PWM signal to the speed pin. In this way, speed and direction of two separate motors can be controlled independently. Note that the PWM signal on the P\_1 and P\_2 can be 0~99%, but 100% high signal (logic 1) not works because of the motor controller IR2104 boost circuit.

**Model: [ACS70028DH](http://www.elecrow.com/dual-channel-hbridge-motor-shield-8a-22v-p-841.html)**

![H-bridge shield.jpg](https://wiki.elecrow.com/images/thumb/3/34/H-bridge_shield.jpg/500px-H-bridge_shield.jpg){ loading=lazy }
![H-bridge shield2.jpg](https://wiki.elecrow.com/images/thumb/8/83/H-bridge_shield2.jpg/500px-H-bridge_shield2.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/dual-channel-hbridge-motor-shield-8a-22v-p-841.html?wiki "Title text")

## Features
--------

- Uses the IRF3205S MOSFET, which support max current up to 110A
- Uses Half bridge motor controller IR2104, to avoid H-bridge shortage.
- 2 Channels

## Specifications
--------------

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
      <th scope="row">Logic Control Voltage</th>
      <td align="center">4.5</td>
      <td align="center">5</td>
      <td align="center">5.5</td>
      <td align="center">V</td>
    </tr>
    <tr>
      <th scope="row">Motor Supply Voltage</th>
      <td align="center">6</td>
      <td align="center">/</td>
      <td align="center">22</td>
      <td align="center">V</td>
    </tr>
    <tr>
      <th scope="row">Output Voltage</th>
      <td align="center">0</td>
      <td align="center">/</td>
      <td align="center">Vinput -1</td>
      <td align="center">V</td>
    </tr>
    <tr>
      <th scope="row">Output Current( For Each Channel)</th>
      <td align="center">/</td>
      <td align="center">/</td>
      <td align="center">8000</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row">Output Duty range</th>
      <td align="center" colspan="3">0%~99%</td>
      <td align="center">/</td>
    </tr>
    <tr>
      <th scope="row">Dimension</th>
      <td align="center" colspan="3">77.0(L)x55.0(W)x23.5(H)</td>
      <td align="center">mm</td>
    </tr>
  </tbody>
</table>

## H-Bridge Introduction
---------------------

### **What is H-Bridge?**

H Bridge configuration is commonly used in electrical applications where the load needs to be driven in either direction. Sometimes it is called a "full bridge", the H-bridge is so named because it has four switching elements at the "corners" of the H and the motor forms the cross bar. The basic bridge is shown in the figure to the right. A typical H-Bridge structure is shown below:  
![H-bridge-1326216112 352 216.png](https://wiki.elecrow.com/images/6/65/H-bridge-1326216112_352_216.png){ loading=lazy }  
The current flows through the load M – Motor in one direction when S1 and S4 switches are closed and current flows in the other direction when S2 and S3 switches are closed. Controller these switches on/off would be surly control the current directly, thus to control the motor rotation. As you see, 4 switches would be needed for a H-bridge, that is way you can see 8 Mosfet on the elecrow dual channel h-bridge motor shield.

### **Why H-Bridge Shield But Not Driver IC Solution Such As L298?**

Actually, there are many Integrated motor driver IC such L298 that maybe easy to use and cheaper, but if your application need larger drive current, for example, 5A current to drive quad-rotor, using discrete device to build H-bridge would be a better solution, they support larger current with lower heat dissipation and higher switching speed. The popular used motor driver IC L298P or L298N can only support a max current of 2A, with terrible heat dissipation that may burn you, but this Elecrow Dual Channel h-bridge Motor Shield would support a minimum of current 8A, with a little heat dissipation, the peak current can be even to 15A.

Actually, if i have a more powerful power resource to test this shield, i believe it would supply a larger driver current.

## Interface Function
------------------

![Motor shield-hard3.jpg](https://wiki.elecrow.com/images/thumb/a/a3/Motor_shield-hard3.jpg/800px-Motor_shield-hard3.jpg){ loading=lazy }

**Motor Supply Voltage:** ------&gt; External Power supply for the Motor Shield, Could be 6~22V depending on the motor you used   
**Power Indicator:** ------&gt; LED indicator for the external power supply.  
**H-Bridge Driver:** ------&gt; 8 High-power MOSFET to build H-Bridge.  
**Motor\_1&amp;2 Connector:** ------&gt; Connect your motors here, the H-Bridge motor shield can drive 2 motors simultaneously, of course it can also drive a 4-wire stepper.  
**Motor Control Pins:** ------&gt; Arduino pins used to control the motor direction&amp;speed as belows:  

<table  border="1" cellspacing="0">
  <tbody>
    <tr>
      <td scope="col" align="center"><b>Motor</b></td>
      <td scope="col" align="center"><b>Pin Name</b></td>
      <td scope="col" align="center"><b>Arduino pin</b></td>
      <td scope="col" align="center"><b>Description</b></td>
    </tr>
    <tr>
      <td rowspan="3" align="center"><b>Motor_1</b></td>
      <td align="center">1A</td>
      <td align="center">D4</td>
      <td rowspan="2">D4=0,D5=1 -&gt; clockwise;<p>D4=1,D5=0 -&gt; anticlockwise;</p></td>
    </tr>
    <tr>
      <td align="center">1B</td>
      <td align="center">D5</td>
    </tr>
    <tr>
      <td align="center">P_1</td>
      <td align="center">D9</td>
      <td>Motor_1 speed control, duty can be 0%~99%</td>
    </tr>
    <tr>
      <td rowspan="3" align="center"><b>Motor_2</b></td>
      <td align="center">2A</td>
      <td align="center">D7</td>
      <td rowspan="2">D7=0,D8=1 -&gt; clockwise;
      <p>D7=1,D8=0 -&gt; anticlockwise;</p></td>
    </tr>
    <tr>
      <td align="center">2B</td>
      <td align="center">D8</td>
    </tr>
    <tr>
      <td align="center">P_2</td>
      <td align="center">D10</td>
      <td>Motor_2 speed control, duty can be 0%~99%</td>
    </tr>
    <tr>
      <td align="center"><b>Motor_1 and Motor_2</b></td>
      <td align="center">EN</td>
      <td align="center">D6</td>
      <td>Motor Shield Output Enable, Should be set to "1" while working</td>
    </tr>
  </tbody>
</table>

## Usage
-----

The Dual-Channel H-Bridge Motor Shield is easy to use, plug on the motor shield onto Croduino, connect your motors to motor shield via the motor\_1 and motor\_2 connect, and then connect the Crowduino to PC via USB.  
![Hbridge connection1.jpg](https://wiki.elecrow.com/images/thumb/d/d8/Hbridge_connection1.jpg/400px-Hbridge_connection1.jpg){ loading=lazy }  
And then, connect the the power supply for motors, via the power supply screws.  
![Hbridge connection3.jpg](https://wiki.elecrow.com/images/thumb/d/df/Hbridge_connection3.jpg/400px-Hbridge_connection3.jpg){ loading=lazy }  
<font color="red">*Important, be careful about the polarity of the power supply as the wrong connection may destroy the motor controller especilly when using high voltage power supply.*  </font>
![Hbridge connection2.jpg](https://wiki.elecrow.com/images/thumb/c/ca/Hbridge_connection2.jpg/400px-Hbridge_connection2.jpg){ loading=lazy }  
The Arduino control the 2 motors as belows:

```
void setup() {                
 // Motor_1 controll pin initiate;
 pinMode(4, OUTPUT);     
 pinMode(5, OUTPUT);    
 pinMode(9, OUTPUT); // Speed control
 
 // Motor_2 controll pin initiate;
 pinMode(7, OUTPUT);     
 pinMode(8, OUTPUT);    
 pinMode(10, OUTPUT);  // Speed control
 
 //Enable the Motor Shield output;  
 pinMode(6, OUTPUT); 
 digitalWrite(6, HIGH);  
}
void loop() {
    
   analogWrite(9,230);    // set the motor_1 speed ;
   digitalWrite(4, HIGH);   
   digitalWrite(5, LOW);  // Set the rotation of motor_1
   
   analogWrite(10,50);    // set the motor_2 speed ;
   digitalWrite(7, HIGH);  
   digitalWrite(8, LOW);  // Set the rotation of motor_2
 
  delay(5000);               // wait for a 5 seconds
  // And we change the motor speed and  rotation direction
    analogWrite(9,100);    // set the motor_1 speed to 100 ;
   digitalWrite(4, LOW);   
   digitalWrite(5, HIGH);  // Set the rotation of motor_1
   
   analogWrite(10,150);    // set the motor_2 speed to 150
   digitalWrite(7, LOW);  
   digitalWrite(8, HIGH);  // Set the rotation of motor_2
   delay(5000) ;              // wait for a 5 seconds
}
```

## Resources
---------

- [Dual Channel H-Bridge Motor Shield in PDF ](https://wiki.elecrow.com/images/5/51/H-bridge_Shield.pdf)
- [Purchase link Dual Channel H-Bridge Motor Shield (8A 22V)](http://www.elecrow.com/dual-channel-hbridge-motor-shield-8a-22v-p-841.html)