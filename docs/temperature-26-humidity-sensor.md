---
title: Temperature & Humidity Sensor
---

## Introduction
------------

This temperature &amp; Humidity sensor is a wired version of the DHT21, in a large plastic body. It is a basic, low-cost digital temperature and humidity sensor. It uses a capacitive humidity sensor and a thermistor to measure the surrounding air, and spits out a digital signal on the data pin (no analog input pins needed). Its fairly simple to use, but requires careful timing to grab data. The only real downside of this sensor is you can only get new data from it once every 2 seconds, so when using our library, sensor readings can be up to 2 seconds old.

**Model: [STH02101S](http://www.elecrow.com/sensor-c-111/temperature-humidity-c-111_112/capacitive-digital-temperature-humidity-sensoram2301-p-312.html)**  
[![AM2301](https://wiki.elecrow.com/images/thumb/a/ae/AM222.jpg.jpg/400px-AM222.jpg.jpg){ loading=lazy }]("AM2301")

## Specification
-------------

- Dimension: 59 \* 27 \* 13mm  
    ![Example.jpg](https://wiki.elecrow.com/images/a/a9/Example.jpg){ loading=lazy }
- 3.5-5.5V Input
- 1-1.5mA measuring current
- Humidity from 0-100% RH
- -40 - 80 degrees C temperature range
- +-3% RH accuracy
- +-0.5 degrees C
- Model: AM2301
- Wire length: 25cm

## Usage
-----

### **Hardware**

This Sensor has 3 wires, connect these wires to your Arduino/Crowduino Project as following:

| **Sensor** | Arduino/Crowduino |
|:-:|:-:|
| Red | +5V |
| Black | GND |
| Yellow | Digital I/O |


![Temperature Humidity Sensor hardware connect.jpg](https://wiki.elecrow.com/images/thumb/9/9e/Temperature_Humidity_Sensor_hardware_connect.jpg/500px-Temperature_Humidity_Sensor_hardware_connect.jpg){ loading=lazy }

### **Programming**

First intall the [Temperature&amp;Hunidity Sensor Library](#resources), please refer to [here](./how-to-install-the-librarys-and-upload-programs-to-arduino.md) to learn how to install the library. and then open the sketch in ...\\examples\\DHTtester, modify the code as belows:

```
#include "DHT.h"
#define DHTPIN 2    // modify to the pin we connected
// Uncomment whatever type you're using!
//#define DHTTYPE DHT11   // DHT 11 
//#define DHTTYPE DHT22   // DHT 22  (AM2302)
#define DHTTYPE DHT21   // DHT 21 (AM2301)
// Connect pin 1 (on the left) of the sensor to +5V
// Connect pin 2 of the sensor to whatever your DHTPIN is
// Connect pin 4 (on the right) of the sensor to GROUND
// Connect a 10K resistor from pin 2 (data) to pin 1 (power) of the sensor
DHT dht(DHTPIN, DHTTYPE);
void setup() {
 Serial.begin(9600); 
 Serial.println("DHTxx test!");
 dht.begin();
}
void loop() {
 // Reading temperature or humidity takes about 250 milliseconds!
 // Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
 float h = dht.readHumidity();
 float t = dht.readTemperature();
 // check if returns are valid, if they are NaN (not a number) then something went wrong!
 if (isnan(t) || isnan(h)) {
   Serial.println("Failed to read from DHT");
 } else {
   Serial.print("Humidity: "); 
   Serial.print(h);
   Serial.print(" %\t");
   Serial.print("Temperature: "); 
   Serial.print(t);
   Serial.println(" *C");
 }
}
```


Upload the code,then open the serial monitor, you can see the signal outputs.  
![Temperature Humidity Sensor test.jpg](https://wiki.elecrow.com/images/0/0d/Temperature_Humidity_Sensor_test.jpg){ loading=lazy }

## Resources
---------

- [File:AM2301 Datasheet.pdf](https://wiki.elecrow.com/images/4/44/AM2301_Datasheet.pdf "File:AM2301 Datasheet.pdf")
- [File:Temperature&amp;Hunidity Sensor Library.zip](https://wiki.elecrow.com/images/e/e9/Temperature%26Hunidity_Sensor_Library.zip "File:Temperature&Hunidity Sensor Library.zip")

## Related link
------------

Click [Capacitive Digital Temperature &amp; Humidity Sensor(AM2301)](http://www.elecrow.com/sensor-c-111/temperature-humidity-c-111_112/capacitive-digital-temperature-humidity-sensoram2301-p-312.html) to buy