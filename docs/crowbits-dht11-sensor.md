---
title: Crowbits-DHT11 Sensor
---

## Description
-----------

Temperature and humidity sensors refer to devices or devices that can convert temperature and humidity into electrical signals that can be easily measured and processed.

![Crowbits-DHT11-Sensor-1.jpg](https://wiki.elecrow.com/images/thumb/a/a5/Crowbits-DHT11-Sensor-1.jpg/600px-Crowbits-DHT11-Sensor-1.jpg){ loading=lazy }

## Features
--------

- Digital reading accuracy

## Specification
-------------

- Interface Type：GPIO
- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Application Ideas
-----------------

Display test information

## Usage
-----

The following sketch demonstrates a simple application.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the A0 interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-DHT11 Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/3/30/Crowbits-DHT11_Sensor-Wiki_1.JPG/600px-Crowbits-DHT11_Sensor-Wiki_1.JPG){ loading=lazy }

3\. Download the library Crowbits-DHT11 Sensor library. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
// Example testing sketch for various DHT humidity/temperature sensors
// Written by ladyada, public domain

#include "DHT.h"

#define DHTPIN A0     // what pin we're connected to

// Uncomment whatever type you're using!
#define DHTTYPE DHT11   // DHT 11 
//#define DHTTYPE DHT22   // DHT 22  (AM2302)
//#define DHTTYPE DHT21   // DHT 21 (AM2301)

// Connect pin 1 (on the left) of the sensor to +5V
// Connect pin 2 of the sensor to whatever your DHTPIN is
// Connect pin 4 (on the right) of the sensor to GROUND
// Connect a 10K resistor from pin 2 (data) to pin 1 (power) of the sensor

DHT dht(DHTPIN, DHTTYPE);

void setup() 
{
    Serial.begin(9600); 
    Serial.println("DHTxx test!");

    dht.begin();
}

void loop() 
{
    // Reading temperature or humidity takes about 250 milliseconds!
    // Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
    float h = dht.readHumidity();
    float t = dht.readTemperature();

    // check if returns are valid, if they are NaN (not a number) then something went wrong!
    if (isnan(t) || isnan(h)) 
    {
        Serial.println("Failed to read from DHT");
    } 
    else 
    {
        Serial.print("Humidity: "); 
        Serial.print(h);
        Serial.print(" %\t");
        Serial.print("Temperature: "); 
        Serial.print(t);
        Serial.println(" *C");
    }
}
```

5.After the code is uploaded successfully, Open the debug window and observe the displayed humidity and temperature.

![Crowbits-DHT11 Sensor-Wiki.jpg](https://wiki.elecrow.com/images/thumb/d/de/Crowbits-DHT11_Sensor-Wiki.jpg/600px-Crowbits-DHT11_Sensor-Wiki.jpg){ loading=lazy }