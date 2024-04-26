---
title: Crowtail- AM2302 Humidity&Temperature Sensor
---

## Description
-----------

The module contains a AM2302 temperature &amp; humidity sensor that is a complex sensor with a calibrated digital signal out.It use digital module acquisition technology and the temperature&amp;humidity sensor technology.Sensor consists of a resistance type moisture element and a NTC temperature measuring element. Because of single wire serial interface, it is easy to use the module.

**Model: [CT009180A](http://www.elecrow.com/crowtail-am2302-humiditytemperature-sensor-p-1651.html)**

![Crowtail- AM2302 Humidity&Temperature Sensor.jpg](https://wiki.elecrow.com/images/thumb/e/eb/Crowtail-_AM2302_Humidity%26Temperature_Sensor.jpg/600px-Crowtail-_AM2302_Humidity%26Temperature_Sensor.jpg){ loading=lazy }

## Specification
-------------

Dimensions(mm):43.2(L)x20.0(W)x9.5(H)

![Crowtail- AM2302 specification.png](https://wiki.elecrow.com/images/thumb/8/86/Crowtail-_AM2302_specification.png/900px-Crowtail-_AM2302_specification.png){ loading=lazy }

## Usage
-----

This demo is going to show you how to read temperature and humidity information from this Crowtail- AM2302 Humidity&amp;Temperature Sensor.

1.Hardware Connection
The Temperature and Humidity sensor is connecting to digital port A0 of Crowtail- Base Shield.

![20160531 1110091.jpg](https://wiki.elecrow.com/images/thumb/e/e6/20160531_1110091.jpg/500px-20160531_1110091.jpg){ loading=lazy }

2.Download [AM2302 Humidity&amp;Temperature Sensor library](../../files/DHT-zip.md) for Arduino boards with 16MHz XTAL; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;

3.Open “DHTtester” example via the path: File --&gt; Examples --&gt; DHT --&gt; DHTtester.

```
// Example testing sketch for various DHT humidity/temperature sensors

#include "DHT.h"
 
#define DHTPIN A0     // what pin we're connected to
 
// Uncomment whatever type you're using!
// #define DHTTYPE DHT11   // DHT 11 
 #define DHTTYPE DHT22   // DHT 22  (AM2302)
//#define DHTTYPE DHT21   // DHT 21 (AM2301)

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

4.Upload it into your Arduino board and open the serial monitor to observe the temperature and relative humidity information of the environment.

![Thresult.png](https://wiki.elecrow.com/images/thumb/2/2a/Thresult.png/400px-Thresult.png){ loading=lazy }

## Resource
--------

- [Crowtail- AM2302 Humidity&amp;Temperature Sensor eagle files](../../files/Crowtail-AM2302-Humidity%26Temperature-Sensor-V2.0-zip.md)
- [AM2302 Humidity&amp;Temperature Sensor library](../../files/DHT-zip.md)