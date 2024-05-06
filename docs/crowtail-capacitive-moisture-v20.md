---
title: Crowtail-Capacitive Moisture V2.0
---

## Description
-----------

This is a capacitive soil moisture sensor with corrosion resistance characteristics. The moisture sensor can be used to detect the moisture of soil or your pet plant's water level, let the plants in your garden reach out for human help. It is connected to Analog I/O port.

Model: [CMS00810C](https://www.elecrow.com/crowtail-capacitive-soil-moisture-sensor.html)

![Crowtail-Capacitive Moisture V2.0 1.png](https://wiki.elecrow.com/images/thumb/e/ea/Crowtail-Capacitive_Moisture_V2.0_1.png/500px-Crowtail-Capacitive_Moisture_V2.0_1.png){ loading=lazy }

## Features
--------

- Corrosion resistant
- Soil moisture sensor based on soil capacitive measurement
- Easy to use
- High sensitivity

## Specification
-------------

Board demensions(mm):102(L)x23(W)x8.2(H)

| Item | Description |
|:-:|:-:|
| Operating voltage | 3.3V~5V |
| Interface | Crowtail compatible interface |

## Usage
-----

The following sketch demonstrates a simple application of sensing the moisture of the soil.

1\. Connect this module to one of analog port A0 of Crowtail - Base Shield with the 4 pin Crowtail cable

2\. Plug Crowtail - Base Shield into the Arduino/Crowduino and connnect Arduino to PC via a USB cable.

3.The hardware installation as shown below

![Crowtail-Capacitive Moisture V2.0 2.png](https://wiki.elecrow.com/images/thumb/0/0b/Crowtail-Capacitive_Moisture_V2.0_2.png/500px-Crowtail-Capacitive_Moisture_V2.0_2.png){ loading=lazy }

4.A calibration process is required prior to the formal testing of soil moisture; (Calibration instructions: limit a range of measurements by reading the sensor values separately in air and water, Open the serial monitor and set the baud rate to 9600 per program.) ① Burn the calibration code into the Arduino main control board ② Open the serial port to monitor the assistant ③ Record values in air and water respectively The calibration code is as follows:

```
void setup() {
Serial.begin(9600); // open serial port, set the baud rate to 9600 bps
void loop() {
int val;
val = analogRead(0); //connect sensor to Analog 0
Serial.println(val); //print the value to serial
delay(100);
}
```

5: The demo code. After the calibration process, you should bring the two sets of data you just recorded into your test code.( The code is highlighted in red )

The demo code is as follows:

```
const int AirValue = 600;   //you need to change this value that you had recorded in the air
const int WaterValue = 360;  //you need to change this value that you had recorded in the water
int intervals = (AirValue - WaterValue)/3;   
int soilMoistureValue = 0;
void setup() {
  Serial.begin(9600); // open serial port, set the baud rate to 9600 bps
}
void loop() {
soilMoistureValue = analogRead(A0);  //put Sensor insert into soil
if(soilMoistureValue > WaterValue && soilMoistureValue < (WaterValue + intervals))
{
  Serial.println("Very Wet");
}
else if(soilMoistureValue > (WaterValue + intervals) && soilMoistureValue < (AirValue - intervals))
{
  Serial.println("Wet");
}
else if(soilMoistureValue < AirValue && soilMoistureValue > (AirValue - intervals))
{
  Serial.println("Dry");
}
delay(100);
}
```

6.The result in different condition after open the serial monitor:

![Crowtail-Capacitive Moisture V2.0 3.png](https://wiki.elecrow.com/images/thumb/a/a6/Crowtail-Capacitive_Moisture_V2.0_3.png/500px-Crowtail-Capacitive_Moisture_V2.0_3.png){ loading=lazy }

![Crowtail-Capacitive Moisture V2.0 4.png](https://wiki.elecrow.com/images/thumb/a/ae/Crowtail-Capacitive_Moisture_V2.0_4.png/500px-Crowtail-Capacitive_Moisture_V2.0_4.png){ loading=lazy }

![Crowtail-Capacitive Moisture V2.0 5.png](https://wiki.elecrow.com/images/thumb/f/f1/Crowtail-Capacitive_Moisture_V2.0_5.png/500px-Crowtail-Capacitive_Moisture_V2.0_5.png){ loading=lazy }

## Resource
--------

- [Crowtail-Capacitive\_Moisture-V2.0-20190408-01.pdf](https://wiki.elecrow.com/images/8/8f/Crowtail-Capacitive_Moisture-V2.0-20190408-01.pdf)
- [Crowtail-Capacitive\_Moisture-V2.0-20190408-01-Eagle.zip](https://wiki.elecrow.com/images/a/ac/Crowtail-Capacitive_Moisture-V2.0-20190408-01-Eagle.zip)
- [Capacitive\_Moisture\_code](https://wiki.elecrow.com/images/3/3f/Capacitive_Moisture.zip)