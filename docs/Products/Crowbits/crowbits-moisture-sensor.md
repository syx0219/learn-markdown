---
title: Crowbits-Moisture Sensor
---

## Description
-----------

This is a capacitive soil moisture sensor, it can measure the soil moisture level of your plant by capacitive sensing. Compared with other types of moisture sensor, the capacitive soil moisture sensor is made of a corrosion resistant material, which will provide a long service life. This moisture sensor can be used to detect the moisture of soil to monitor if the plants need water.

![Crowbits-Moisture Sensor 1.jpg](https://wiki.elecrow.com/images/thumb/3/39/Crowbits-Moisture_Sensor_1.jpg/600px-Crowbits-Moisture_Sensor_1.jpg){ loading=lazy }

## Features
--------

- Corrosion resistant
- Soil moisture sensor based on soil capacitive measurement
- Easy to use
- High sensitivity

## Specification
-------------

- Operating voltage: 3.3V
- Size: 20 (W)\*92.5(L)

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the A3 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-Moisture Sensor-Wiki 1.jpg](https://wiki.elecrow.com/images/thumb/e/ed/Crowbits-Moisture_Sensor-Wiki_1.jpg/600px-Crowbits-Moisture_Sensor-Wiki_1.jpg){ loading=lazy }

3.Upload the following code to the Crowbits-UNO board.

```
void setup() {                
 // initialize the digital pin5 as an output.
 Serial.begin(9600); // open serial port, set the baud rate to 9600 bps
}

int val0=A3;

int SensorValue0=0;

void loop() {

    SensorValue0 = analogRead(val0); //connect sensor to Analog 0

  Serial.print("SensorValue0:"); //print the value to serial
  Serial.println(SensorValue0); //print the value to serial

  delay(100);
}
```

4.After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Put the sensor in the soil, the serial port will output the corresponding voltage value.

![Crowbits-Moisture Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/0/05/Crowbits-Moisture_Sensor-Wiki_2.jpg/600px-Crowbits-Moisture_Sensor-Wiki_2.jpg){ loading=lazy }