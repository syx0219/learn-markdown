---
title: Crowtail-DHT20
---

## **Introduction**
----------------

DHT20 is an intelligent temperature and humidity sensor module, which is a new upgraded product of DHT11. The module is equipped with a newly designed ASIC dedicated chip, an improved MEMS semiconductor capacitive humidity sensor element and a standard temperature sensor element. After comprehensive improvement, DHT20 reduces power consumption and costs while greatly improving its performance parameters in terms of measurement accuracy, power supply voltage, measurement range, response time, stability, etc. , far exceeding the reliability of the previous generation of sensors level. DHT20 has the characteristics of calibration-free, low power consumption, high precision, high stability, etc. It adopts a fully calibrated digital I2C interface, which has fast response, strong anti-interference ability and higher cost performance.

**Model: [CRT10251D](https://www.elecrow.com/crowtail-dht20.html)**

![DHT20-1.png](https://wiki.elecrow.com/images/b/bf/DHT20-1.png){ loading=lazy }

## **Specification**
-----------------

Working Voltage: 2.2V~5.5V

Measuring Range

- Humidity: 0%-100% RH
- Temperature: -40~80°C

Accuracy:

- Humidity: ±3% RH
- Temperature: ±0.5°C

Sensitivity:

- Humidity: ±0.024% RH
- Temperature: 0.01°C

Dimensions (mm): 40.0 (length) x 20.0 (width) x 7.6 (height)

## **Usage**
---------

This demo will show you how to read temperature and humidity information from this Crowtail-temperature and humidity sensor.
1\. Hardware connection
The temperature and humidity sensor is connected to the I2C port (A4, A5) of the Crowtail-Base Shield.

![DHT20-2.png](https://wiki.elecrow.com/images/thumb/6/6b/DHT20-2.png/300px-DHT20-2.png){ loading=lazy }

2\. Download the temperature sensor library of the Crowtail-DHT20 board, unzip it and put it into the library file of the Arduino IDE according to the path: ..\\arduino-1.0\\libraries;  
3\. Open the "DHT20" example through the following path: Crowtail-DHT20 --&gt; examples --&gt; DHT20 --&gt; DHT20.ino.

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
  Serial.print("temperature:"); Serial.print(dht20.getTemperature());Serial.print("C");
  //Get relative humidity
  Serial.print("  humidity:"); Serial.print(dht20.getHumidity()*100);Serial.println(" %RH");
  
  delay(1000);
}
```

4\. Upload it to your Arduino board and open the serial port monitor to observe the temperature and relative humidity information of the environment.

![DHT20-3.png](https://wiki.elecrow.com/images/thumb/8/89/DHT20-3.png/600px-DHT20-3.png){ loading=lazy }

## **Resource**
------------

- [Crowtail-DHT20.zip](./files/Crowtail-DHT20-zip.md)
- [Eagle\_files.zip](./files/Eagle-files-zip.md)