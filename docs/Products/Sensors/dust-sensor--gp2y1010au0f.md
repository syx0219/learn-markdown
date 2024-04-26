---
title: Dust Sensor- GP2Y1010AU0F
---

## Description
-----------

Sharp's GP2Y1010AU0F is an optical air quality sensor, designed to sense dust particles. An infrared emitting diode and a phototransistor are diagonally arranged into this device, to allow it to detect the reflected light of dust in air. It is especially effective in detecting very fine particles like cigarette smoke, and is commonly used in air purifier systems. The sensor has a very low current consumption (20mA max, 11mA typical), and can be powered with up to 7VDC. The output of the sensor is an analog voltage proportional to the measured dust density, with a sensitivity of 0.5V/0.1mg/m3. This sensor is packaged with a 6-pin wires with JST connector to help connect it with your system.  
**Model:[SGP2Y1010AU](http://www.elecrow.com/dust-sensor-gp2y1010au0f-p-861.html)**  

![Dust Sensor- GP2Y1010AU0F.jpg](https://wiki.elecrow.com/images/thumb/4/40/Dust_Sensor-_GP2Y1010AU0F.jpg/400px-Dust_Sensor-_GP2Y1010AU0F.jpg){ loading=lazy }

## Dimensions and Interface
------------------------

![GP2Y1010AU0F.jpg](https://wiki.elecrow.com/images/thumb/2/24/GP2Y1010AU0F.jpg/500px-GP2Y1010AU0F.jpg){ loading=lazy }

## Usage
-----

1.Hardware connection

![GP2Y1010AU0F1.jpg](https://wiki.elecrow.com/images/thumb/3/3d/GP2Y1010AU0F1.jpg/500px-GP2Y1010AU0F1.jpg){ loading=lazy } 
![GP2Y1010AU0F2.jpg](https://wiki.elecrow.com/images/thumb/1/15/GP2Y1010AU0F2.jpg/500px-GP2Y1010AU0F2.jpg){ loading=lazy }

2.Copy and paste code below to a new Arduino sketch:

```
/*
 Standalone Sketch to use with a Arduino UNO and a
 Sharp Optical Dust Sensor GP2Y1010AU0F
*/
  
int measurePin = 0; //Connect dust sensor to Arduino A0 pin
int ledPower = 2;   //Connect 3 led driver pins of dust sensor to Arduino D2
  
int samplingTime = 280;
int deltaTime = 40;
int sleepTime = 9680;
  
float voMeasured = 0;
float calcVoltage = 0;
float dustDensity = 0;
  
void setup(){
  Serial.begin(9600);
  pinMode(ledPower,OUTPUT);
}
  
void loop(){
  digitalWrite(ledPower,LOW); // power on the LED
  delayMicroseconds(samplingTime);
  
  voMeasured = analogRead(measurePin); // read the dust value
  
  delayMicroseconds(deltaTime);
  digitalWrite(ledPower,HIGH); // turn the LED off
  delayMicroseconds(sleepTime);
  
  // 0 - 5V mapped to 0 - 1023 integer values
  // recover voltage
  calcVoltage = voMeasured * (5.0 / 1024.0);
  
  // linear eqaution taken from http://www.howmuchsnow.com/arduino/airquality/
  // Chris Nafis (c) 2012
  dustDensity = 0.17 * calcVoltage - 0.1;
  
  Serial.print("Raw Signal Value (0-1023): ");
  Serial.print(voMeasured);
  
  Serial.print(" - Voltage: ");
  Serial.print(calcVoltage);
  
  Serial.print(" - Dust Density: ");
  Serial.println(dustDensity); // unit: mg/m3
  
  delay(1000);
}
```

4.Open the serial monitor. You should the test result.

![GP2Y1010AU0F result.jpg](https://wiki.elecrow.com/images/thumb/8/8f/GP2Y1010AU0F_result.jpg/400px-GP2Y1010AU0F_result.jpg){ loading=lazy }

### **Resource**

- [GP2Y1010AU0F Demo code](https://wiki.elecrow.com/images/a/ae/Dust_Sensor_GP2Y1010AU0F.zip)
- [DSM501 GP2Y1010AU0F Datasheet](https://wiki.elecrow.com/images/1/14/Gp2y1010au_e.pdf)
- [DSM501 Application Note](https://wiki.elecrow.com/images/4/48/Gp2y1010au_appl_e.pdf)