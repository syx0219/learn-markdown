---
title: Crowtail- Analog Gyro
---

## Description
-----------

Crowtail- Analog Gyro is based on an angular velocity sensor(Murata-ENC-03R) that uses the phenomenon of Coriolis force.which is generated when a rotational angular velocity is applied to thevibrator.One sensor detects rotation on one axis.

**Model: [CT0015AG](http://www.elecrow.com/crowtail-analog-gyro-p-1247.html)**

![Crowtail- Analog Gyro.JPG](https://wiki.elecrow.com/images/thumb/d/d4/Crowtail-_Analog_Gyro.JPG/600px-Crowtail-_Analog_Gyro.JPG){ loading=lazy }

## Feature
-------

- Standard Crowtail Interface
- Input Voltage:5V
- Light Weight
- High Speed
- Measure X-axis Angular Velocity
- Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

## Usage
-----

The module detects one-axis rotation with analog signal.

1.Hardware Connection

Connect it to A0 port of Crowtail - Base Shield,Plug the Grove - Base Shield into Arduino/Crowduino and connect them to PC using a USB cable.

![Analoghardware11.jpg](https://wiki.elecrow.com/images/thumb/7/7f/Analoghardware11.jpg/600px-Analoghardware11.jpg){ loading=lazy }

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

![Annalogreslut.jpg](https://wiki.elecrow.com/images/c/c7/Annalogreslut.jpg){ loading=lazy }

4.As you see the "Now you can begin your test", that means the calibration done. You can use the sensor now. Rotating direction can reference the following picture:

![Analogrotat.jpg](https://wiki.elecrow.com/images/thumb/f/fe/Analogrotat.jpg/400px-Analogrotat.jpg){ loading=lazy }

## Resource
--------

- [Analog\_Gyro Program](../../files/Analog-Gyro-zip.md)
- [Crowtail- Analog Gyro eagle files eagle files](../../files/Crowtail-Analog-Gyro-zip.md)