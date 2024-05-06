---
title: Crowbits-Grayscale Sensor
---

## Description
-----------

The grayscale sensor is an analog sensor. The gray-scale sensor uses different detection colors to reflect different levels of light, and the photoresistor uses different principles to detect the color depth of light returned by different detection surfaces. It is used to distinguish black from other colors when the ambient light interference is not very serious.

![Crowbits-Grayscale-Sensor-1.jpg](https://wiki.elecrow.com/images/thumb/8/8b/Crowbits-Grayscale-Sensor-1.jpg/600px-Crowbits-Grayscale-Sensor-1.jpg){ loading=lazy }

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

2\. Connect the module to the A2 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-Grayscale Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/1/1f/Crowbits-Grayscale_Sensor-Wiki_1.JPG/600px-Crowbits-Grayscale_Sensor-Wiki_1.JPG){ loading=lazy }

3\. Upload the following code to the Crowbits-UNO board.

```
void setup()
{
  Serial.begin(9600); // open serial port, set the baud rate to 9600 bps
}
void loop()
{
      int val;
      val=analogRead(A2);   //connect grayscale sensor to Analog 0
      Serial.println(val,DEC);//print the value to serial        
      delay(1000);
}
```

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. When you point the sensor at a white surface object and a black surface object, the value printed by the serial port is not different.

![Crowbits-Grayscale Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/f/f3/Crowbits-Grayscale_Sensor-Wiki_2.jpg/600px-Crowbits-Grayscale_Sensor-Wiki_2.jpg){ loading=lazy }