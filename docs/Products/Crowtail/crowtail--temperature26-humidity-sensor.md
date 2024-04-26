---
title: Crowtail- IR Reflective Sensor
---

## Description
-----------

This module can help you detect the temperature and humidity of the environment of your house. The module contains a DHT11 temperature &amp; humidity senorthat is a complex sensor with a calibrated digital signal out.It use digital module acquisition technology and the temperature&amp;humidity sensor technology.Sensor consists of a resistance type moisture element and a NTC temperature measuring element. Because of single wire serial interface, it is easy to use the module.

**Model: [CT0010TH](http://www.elecrow.com/crowtail-temperature-humidity-sensor-p-1229.html)**

![Crowtail-Temperature& Humidity Sensor.JPG](https://wiki.elecrow.com/images/thumb/3/39/Crowtail-Temperature%26_Humidity_Sensor.JPG/600px-Crowtail-Temperature%26_Humidity_Sensor.JPG){ loading=lazy }

## Specification
-------------

- Work Voltage: 3.3V ~ 5V
- Measuring Range:

```
  Humidity: 20% - 90% RH
  Temperature: 0 ~ 50 °C
```

- Accuracy:

```
  Humidity: ±5% RH
  Temperature: ±2°C
```

- Sensitivity:

```
  Humidity: ±1% RH
  Temperature: 1°C
```

- Signal Collecting Period: 2S
- Dimensions(mm):40.0(L)x20.0(W)x7.6(H)

## Usage
-----

This demo is going to show you how to read temperature and humidity information from this Crowtail - Temperature and Humidity Sensor.

1.Hardware Connection
The Temperature and Humidity sensor is connecting to digital port D5 of Crowtail - Base Shield.

![Temperature and Humidity Sensor11.jpg](https://wiki.elecrow.com/images/thumb/1/17/Temperature_and_Humidity_Sensor11.jpg/600px-Temperature_and_Humidity_Sensor11.jpg){ loading=lazy }

2.Download [Temperature\_humidity\_sensor library](../../files/Temperature-humidity-sensor-zip.md) for Arduino boards with 16MHz XTAL; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;

3.Open “DHTtester” example via the path: File --&gt; Examples --&gt; Humidity\_Temperature\_Sensor --&gt; DHTtester.

```
// Example testing sketch for various DHT humidity/temperature sensors

#include "DHT.h"
 
#define DHTPIN 5     // what pin we're connected to
 
// Uncomment whatever type you're using!
#define DHTTYPE DHT11   // DHT 11 
//#define DHTTYPE DHT22   // DHT 22  (AM2302)
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

## Resource
--------

- [Temperature&amp; Humidity Sensor Program](../../files/Temperature.md)  
- [Crowtail- Temperature&amp; Humidity Sensor eagle files](../../files/Crowtail-Temperature.md)