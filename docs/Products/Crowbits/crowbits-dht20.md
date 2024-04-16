---
title: Crowbits-DHT20
---

## Description
-----------

DHT20 is an intelligent temperature and humidity sensor module that can convert temperature and humidity into electrical signals to easily measure temperature and humidity. The module is equipped with a newly designed ASIC dedicated chip, an improved MEMS semiconductor capacitive humidity sensor element and a standard temperature sensor element. After comprehensive improvement, DHT20 reduces power consumption and cost, while greatly improving measurement accuracy, power supply voltage, measurement range, response time, stability, etc.; it has the characteristics of no calibration, low power consumption, high accuracy, and high stability. Using fully calibrated digital I2C communication interface, it has fast response, strong anti-interference ability and high cost performance.

![Crowbits-dht20-1.png](https://wiki.elecrow.com/images/thumb/0/0e/Crowbits-dht20-1.png/300px-Crowbits-dht20-1.png){ loading=lazy }  

## Technical specifications
------------------------

Working voltage: DC2.2V+5.5V

Measuring range

- Humidity: 0%-100% RH
- Temperature: -40~80°C

Error range

- Humidity: ±3% RH
- Temperature: ±0.5°C

Resolution

- Humidity: ±0.024% RH
- Temperature: 0.01°C

Response time

- Humidity: τ63% condition is less than 8 seconds
- Temperature: τ63% condition mini5 seconds, max30 seconds

Interface type: I2C  
Size: 31.5 (L)\*24.5(W)\*13(H)mm

## Application scenarios
---------------------

Test environment temperature and humidity information

## Usage
-----

The following sketch demonstrates a simple application

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the A4 and A5 interface on the Crowbits-UNO board, as shown in the figure below:

![Crowbits-dht20-2.png](https://wiki.elecrow.com/images/thumb/e/e8/Crowbits-dht20-2.png/400px-Crowbits-dht20-2.png){ loading=lazy }  

3\. Download the Crowbit-DHT20 software file and unzip it and place it in the libraries folder of the Arduino IDE. Run Arduino.exe, Open path: Crowtail-DHT20 --&gt; examples --&gt; DHT20 --&gt; DHT20.ino

```
#include <DHT20.h>
/*!
 * @brief Construct the function
 * @param pWire IC bus pointer object and construction device, can both pass or not pass parameters, Wire in default.
 * @param address Chip IIC address, 0x38 in default.
 */
DHT20  dht20;
void setup()
{
  Serial.begin(115200);
  //Initialize sensor
  while(dht20.begin())
{
    Serial.println("Initialize sensor failed");
    delay(1000);
   }
}

void loop()
{
  //Get ambient temperature
  Serial.print("temperature:"); Serial.print(dht20.getTemperature());Serial.print("℃");
  //Get relative humidity
  Serial.print("  humidity:"); Serial.print(dht20.getHumidity()*100);Serial.println(" %RH");
    delay(1000);
}
```


4\. Upload it to your Crowbits-UNO board, open the COM serial port, select 115200 for the baud rate at the bottom right, and the monitor displays the current environmental temperature and relative humidity information.

![Crowbits-dht20-3.png](https://wiki.elecrow.com/images/thumb/5/5f/Crowbits-dht20-3.png/600px-Crowbits-dht20-3.png){ loading=lazy }