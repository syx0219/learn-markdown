---
title: Crowtail- thermocouple Sensor
---

## Description
-----------

Thermocouples are very sensitive, requiring a good amplifier with a cold - compensation reference. The Crowtail- thermocouple Sensor USES a K type thermocouple Temperature detection, with a Thermistor to detect The ambient Temperature as Temperature compensation. The detectable range of this Sensor is -50-600℃ , and The accuracy is ±(2.0% + 2℃)

**Model: [CT009559T](http://www.elecrow.com/crowtail-thermocouple-sensor-p-1661.html)**

![Crowtail- thermocouple Sensor.jpg](https://wiki.elecrow.com/images/thumb/1/11/Crowtail-_thermocouple_Sensor.jpg/600px-Crowtail-_thermocouple_Sensor.jpg){ loading=lazy }

## Specifications
--------------

- Voltage：3.3 ~ 5V
- Max power rating at 25℃ ：300mW
- Operating temperature range：-40 ~ +125 ℃
- he temperature measurement range is (-50 ~ +600℃)
- Amplifier output voltage range (0 ~ 3.3 V) mv
- Cold junction compensation (environment temperature measurement)
- Thermocouple temperature measurement accuracy of + / - 2.0% (+ 2 ℃)
- Dimensions(mm):40.0(L)x20.0(W)x10.3(H)

## Usage
-----

Here is an example to show you how to read temperature information from the sensor.

We need a Crowduino UNO and a Crowtail- thermocouple Sensor.

### **Hardware Installation**

There's a I2C Port on Crowduino, actually it's connect to A4 and A5 else. So we can use this port to read data from the sensor.

Let's plug this sensor to I2C port of Crowduino.

![261425001.jpg](https://wiki.elecrow.com/images/thumb/7/7d/261425001.jpg/500px-261425001.jpg){ loading=lazy }

### **Download Code and Upload**

You can download the library [High\_Temp](https://wiki.elecrow.com/images/1/19/High_Temp.zip)

Then extract the library the Library folder of Arduino, open the demo in examples folder.

Then upload it to your Crowduino.

Then, open your Serial Monitor, you can find the temperature in Celsius here.

![40748.png](https://wiki.elecrow.com/images/thumb/7/70/40748.png/500px-40748.png){ loading=lazy }

### **K type thermocouple indexing table**

As a reference, the following is K type thermocouple indexing table.

![K-type.png](https://wiki.elecrow.com/images/thumb/9/9e/K-type.png/600px-K-type.png){ loading=lazy }

## Resource
--------

- [Crowtail- thermocouple Sensor eagle file](https://wiki.elecrow.com/images/0/0e/Crowtail-_thermocouple_Sensor_eagle_files.zip)
- [Crowtail- thermocouple Sensor demo code](https://wiki.elecrow.com/images/1/19/High_Temp.zip)