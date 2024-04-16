---
title: Crowbits-Gas Sensor
---

## Description
-----------

This module is a converter that converts a gas integral number into a corresponding electrical signal. It mainly uses the chemical potential difference between two electrodes. One electrode measures the gas concentration in the gas, and the other electrode is a fixed reference electrode When the concentration of a certain measured gas exceeds the standard, the concentration value will be higher than the electrical signal of the reference electrode, and the module will output the corresponding concentration value effect.

![Crowbits-Gas-Sensor-1.jpg](https://wiki.elecrow.com/images/thumb/1/1a/Crowbits-Gas-Sensor-1.jpg/600px-Crowbits-Gas-Sensor-1.jpg){ loading=lazy }

## Features
--------

- Easy to use

## Specification
-------------

- Interface Type: Analog input
- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-Gas Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/f/f3/Crowbits-Gas_Sensor-Wiki_1.JPG/600px-Crowbits-Gas_Sensor-Wiki_1.JPG){ loading=lazy }

3.Upload the following code to the Crowbits-UNO board.

```
void setup() 
{
  Serial.begin(9600);
}

void loop() 
{
  float sensor_volt;
  float sensorValue;

  sensorValue = analogRead(A2);
  sensor_volt = sensorValue / 1024 * 5.0;

  Serial.print("sensor_volt = ");
  Serial.print(sensor_volt);
  Serial.println("V");
  delay(1000);
}
```

4.After the upload is successful, open the serial port monitor, the baud rate is set to 9600.When gas is detected, the voltage value output by the serial port will change.

![Crowbits-Gas Sensor-Wiki.jpg](https://wiki.elecrow.com/images/thumb/8/84/Crowbits-Gas_Sensor-Wiki.jpg/600px-Crowbits-Gas_Sensor-Wiki.jpg){ loading=lazy }