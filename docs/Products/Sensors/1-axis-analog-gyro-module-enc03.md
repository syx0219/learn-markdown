---
title: 1-Axis Analog Gyro Module-ENC03
---

## Description
-----------

This angular velocity sensor utilizes a Coriolis force that act on a vibrating object when an angular velocity is applied to it. The use of this unit simplifies equipment structure and circuit configuration, thus making it possible to provide outstanding performance. This module can be used for positional control and posture control of a moving object requiring precision and quick-response measurements. There is one ENC-03r senor on this module, provides 1-axis velocity with high speed, which outputs as analog voltage.

**Model:[SENC031G](http://www.elecrow.com/1axis-analog-gyro-moduleenc03-p-711.html)**

![1-Axis Analog Gyro Module-ENC03.jpg](https://wiki.elecrow.com/images/thumb/8/85/1-Axis_Analog_Gyro_Module-ENC03.jpg/400px-1-Axis_Analog_Gyro_Module-ENC03.jpg){ loading=lazy }

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
OUT--A0

![1-Axis Analog Gyro Module-ENC03 hardware.jpg](https://wiki.elecrow.com/images/thumb/d/d1/1-Axis_Analog_Gyro_Module-ENC03_hardware.jpg/600px-1-Axis_Analog_Gyro_Module-ENC03_hardware.jpg){ loading=lazy }

2.Upload the below code.

```
int sensorPin = A0;             // select the input pin for the sensor

float reference_Value=0;

int sensorValue = 0;            // variable to store the value coming from the sensor

void setup() {

   int i;
   float sum=0;
   pinMode(sensorPin, INPUT);
   Serial.begin(9600);
   Serial.println("Please do not rotate it before calibrate!");
   Serial.println("Get the reference value:");
    
   for(i=0;i<1000;i++)
   {
       // read the value from the sensor:
       sensorValue = analogRead(sensorPin);
       sum += sensorValue;
       delay(5);
   }
   reference_Value = sum/1000.0;
   Serial.println(reference_Value);
   Serial.println("Now you can begain your test!");
}

void loop() 
{

   double angularVelocity;
   sensorValue = analogRead(sensorPin);
   angularVelocity =((double)(sensorValue-reference_Value)*4930.0)/1023.0/0.67; //get the angular velocity
   Serial.print(angularVelocity);
   Serial.println("deg/s");
   Serial.println(" ");
   delay(500);
}
```

3.Now, it is time to the calibration. Put the sensor on your desk horizontally, and then press the Reset button on the Crowduino, and then Open the serial tool:

![1-Axis Analog Gyro Module-ENC03 reslut.jpg](https://wiki.elecrow.com/images/thumb/f/fc/1-Axis_Analog_Gyro_Module-ENC03_reslut.jpg/400px-1-Axis_Analog_Gyro_Module-ENC03_reslut.jpg){ loading=lazy }

4.As you see the "Now you can begin your test", that means the calibration done. You can use the sensor now. Rotating direction can reference the following picture:

![Analogrotat.jpg](https://wiki.elecrow.com/images/thumb/f/fe/Analogrotat.jpg/400px-Analogrotat.jpg){ loading=lazy }

## Resource
--------

- [Analog\_Gyro Program](../../files/Analog-Gyro-zip.md)
- [ENC-03 Datasheet ](../../files/ENC-03-pdf.md)