---
title: 2-Axis Analog Gyro Module-ENC03
---

## Description
-----------

This angular velocity sensor utilizes a Coriolis force that act on a vibrating object when an angular velocity is applied to it. The use of this unit simplifies equipment structure and circuit configuration, thus making it possible to provide outstanding performance. 
This module can be used for positional control and posture control of a moving object requiring precision and quick-response measurements. There is two ENC-03r senor on this module, provides 2-axis velocity with high speed, which outputs as analog voltage.

**Model:[SENC032G](http://www.elecrow.com/2axis-analog-gyro-moduleenc03-p-712.html)**

![2-Axis Analog Gyro Module-ENC03.jpg](https://wiki.elecrow.com/images/thumb/f/f4/2-Axis_Analog_Gyro_Module-ENC03.jpg/400px-2-Axis_Analog_Gyro_Module-ENC03.jpg){ loading=lazy }

## Features
--------

- Supply Voltage: 2.7V~5.25V DC
- Resonance Frequency: 30.8 kHz
- Max Angular Velocity: +/-300 Degree
- Output (at Angular Velocity=0): 1.35 V DC
- Scale Factor: 0.67 mV/deg/sec.
- Linearity: +/-5%;

## Usage
-----

The module detects one-axis rotation with analog signal.

1.Hardware Connection
5V+--5V
GND--GND
X--A0
Y--A1

![2-Axis Analog Gyro Module-ENC03 hardware.jpg](https://wiki.elecrow.com/images/thumb/2/24/2-Axis_Analog_Gyro_Module-ENC03_hardware.jpg/600px-2-Axis_Analog_Gyro_Module-ENC03_hardware.jpg){ loading=lazy }

2.Copy the below code to you new skecth,then upload it.

```
int X_Axis = A0;             // select the input pin for the sensor
int Y_Axis = A1; 
float X_reference_Value=0;
float Y_reference_Value=0;

int X_Axis_Value = 0;            // variable to store the value coming from the sensor
int Y_Axis_Value = 0;

void setup() {

   int i;
   float X_sum=0,Y_sum=0;
   pinMode(X_Axis, INPUT);
   pinMode(Y_Axis, INPUT);
   Serial.begin(9600);
   Serial.println("Please do not rotate it before calibrate!");
   Serial.println("Get the reference value:");
    
   for(i=0;i<1000;i++)
   {
       // read the value from the sensor:
       X_Axis_Value = analogRead(X_Axis);
       Y_Axis_Value = analogRead(Y_Axis);
       X_sum += X_Axis_Value;
       Y_sum += Y_Axis_Value;
       delay(5);
   }
   X_reference_Value = X_sum/1000.0;
   Y_reference_Value = Y_sum/1000.0;
   Serial.print("reference_Value:   ");
   Serial.print("X:");
   Serial.print(X_reference_Value);
   Serial.print("  Y:");
   Serial.println(Y_reference_Value);
   Serial.println("Now you can begain your test!");
}

void loop() 
{
   double X_angularVelocity,Y_angularVelocity;
   X_Axis_Value = analogRead(X_Axis);
   Y_Axis_Value = analogRead(Y_Axis);
   X_angularVelocity =((double)(X_Axis_Value-X_reference_Value)*4930.0)/1023.0/0.67; //get the angular velocity
   Y_angularVelocity =((double)(Y_Axis_Value-Y_reference_Value)*4930.0)/1023.0/0.67;
   Serial.print("angularVelocity:  ");
   Serial.print("X:");
   Serial.print(X_angularVelocity);
   Serial.print("deg/s");
   Serial.print("   Y:");
   Serial.print(Y_angularVelocity);
   Serial.print("deg/s");
   Serial.println(" ");
   delay(500);
}
```

3.Now, it is time to the calibration. Put the sensor on your desk horizontally, and then press the Reset button on the Crowduino, and then Open the serial tool:

![2-Axis Analog Gyro Module-ENC03 reslut.jpg](https://wiki.elecrow.com/images/thumb/c/c7/2-Axis_Analog_Gyro_Module-ENC03_reslut.jpg/400px-2-Axis_Analog_Gyro_Module-ENC03_reslut.jpg){ loading=lazy }

4.As you see the "Now you can begin your test", that means the calibration done. You can use the sensor now. Rotating direction can reference the following picture:

![Analogrotat.jpg](https://wiki.elecrow.com/images/thumb/f/fe/Analogrotat.jpg/400px-Analogrotat.jpg){ loading=lazy }

## Resource
--------

- [Demo code](../../files/Analog-Gyro-Axis-zip.md)
- [ENC-03 Datasheet ](../../files/ENC-03-pdf.md)