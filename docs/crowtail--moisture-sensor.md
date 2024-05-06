---
title: Crowtail- Moisture Sensor
---

## Description
-----------

This Moisture Sensor can be used to detect the moisture of soil or your pet plant's water level, let the plants in your garden reach out for human help. It is connected to Analog I/O port.

**Model: [CT0007MS](http://www.elecrow.com/crowtail-moisture-sensor-p-1228.html)**

![Crowtail- Moisture Sensor.JPG](https://wiki.elecrow.com/images/thumb/a/a1/Crowtail-_Moisture_Sensor.JPG/600px-Crowtail-_Moisture_Sensor.JPG){ loading=lazy }

## Features
--------

- Soil moisture sensor based on soil resistivity measurement
- Easy to use

## Specification
-------------

Dimensions(mm):80.0(L)x20.0(W)x6.8(H)

| Item | Min | Typical | Max | Unit |
|:-:|:-:|:-:|:-:|:-:|
| Voltage | 3.3 | / | 5 | V |
| Current | 0 | ~ | 35 | mA |
| Sensor in dry soil | 0 | ~ | 300 | / |
| Sensor in humid soil | 300 | ~ | 500 | / |
| Sensor in water | 500 | ~ | 750 | / |

## Application Ideas
-----------------

- Botanical gardening
- Moisture sensoring

## Usage
-----

The following sketch demonstrates a simple application of sensing the moisture of the soil.

1.Connect this module to one of analog port A0 of Crowtail - Base Shield with the 3 pin Crowtail cable, and then insert the Sensor into the soil or place it anywhere you want.

2.Plug Crowtail - Base Shield into the Arduino/Crowduino and connnect Arduino to PC via a USB cable.

3.The hardware installation as shown below:

![Mositure11.jpg](https://wiki.elecrow.com/images/thumb/d/de/Mositure11.jpg/400px-Mositure11.jpg){ loading=lazy }
![Mositure12.jpg](https://wiki.elecrow.com/images/thumb/4/4b/Mositure12.jpg/600px-Mositure12.jpg){ loading=lazy }

4.Copy and paste code below to a new Arduino sketch.

```
int sensorPin = A0;    // select the input pin for the moisture Sensor
int sensorValue = 0;  // variable to store the value coming from the sensor

void setup() {
 // declare the ledPin as an OUTPUT:
  Serial.begin(9600);  
}

void loop() {
 // read the value from the sensor:
 sensorValue = analogRead(sensorPin);    
 delay(1000);          
 Serial.print("sensor = " );                       
 Serial.println(sensorValue);                   
}
```

5.The Result in different condition after open the serial monitor:

![Mositureresult1.jpg](https://wiki.elecrow.com/images/6/6d/Mositureresult1.jpg){ loading=lazy } 
![Mositureresult2.jpg](https://wiki.elecrow.com/images/5/53/Mositureresult2.jpg){ loading=lazy }
![Mositureresult3.jpg](https://wiki.elecrow.com/images/2/2b/Mositureresult3.jpg){ loading=lazy }
![Mositureresult4.jpg](https://wiki.elecrow.com/images/e/e3/Mositureresult4.jpg){ loading=lazy }

## Resource
--------

- [Moisture Sensor Program](./files/Moisturesensor-zip.md)
- [Crowtail-Moisture Sensor eagle files](./files/Crowtail-Moisture-Sensor-zip.md)