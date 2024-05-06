---
title: Weight Sensor Scales Kit- 20KG
---

## Description
-----------

This Kit includes a weight sensor that has a capacity of 20kg, and the mechanic parts to install the weight sensor, ready for an electronic scale application. As you know, the most difficult parts in developing such an electronic scales is the mechanic parts and A/D parts, we help you solving the whole problem by providing you all the mechanic parts and the Data acquisition parts. You can collect the data with any microcontroller include Arduino board. The Weight sensor outputs differential signal, with the Green wire (+) and White wire (-).

**Model:[SEN20KGO](http://www.elecrow.com/weight-sensor-scales-kit-20kg-p-714.html)**

![Weight Sensor Scales Kit- 20KG1.jpg](https://wiki.elecrow.com/images/thumb/0/09/Weight_Sensor_Scales_Kit-_20KG1.jpg/400px-Weight_Sensor_Scales_Kit-_20KG1.jpg){ loading=lazy }

## Features
--------

- Dimension: 170\*115 mm
- Working Voltage: 3.3\*10 V
- Max Output Voltage(mv): Power Voltage\*2.0; for example, when power by 5V voltage, the full scale(20 Kg) output voltage is 10 mv

## Usage
-----

The following sketch demonstrates a simple application of setting the time and reading it out.

1.Hardware connection

![Weight Sensor Scales Kit- 20KG hardware.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Weight_Sensor_Scales_Kit-_20KG_hardware.jpg/600px-Weight_Sensor_Scales_Kit-_20KG_hardware.jpg){ loading=lazy } 
![Weight Sensor Scales Kit- 20KG hardware1.jpg](https://wiki.elecrow.com/images/thumb/1/10/Weight_Sensor_Scales_Kit-_20KG_hardware1.jpg/600px-Weight_Sensor_Scales_Kit-_20KG_hardware1.jpg){ loading=lazy }

2.Download the library File:[Hx711 Library](https://wiki.elecrow.com/images/2/25/Hx711.zip)

3.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries.

4.Open the code directly by the path:File -&gt; Example -&gt;hx711-&gt;SerialScale.

```
// Hx711.DOUT - pin #A1
// Hx711.SCK - pin #A0

#include "hx711.h"

Hx711 scale(A1, A0);

void setup() {

  Serial.begin(9600);

}

void loop() {

  Serial.print(scale.getGram(), 1);
  Serial.println(" g");

  delay(200);
}
```

5.Upload the code,then open the serial monitor to see the result.

![Weight Sensor Scales Kit- 20KG result.jpg](https://wiki.elecrow.com/images/thumb/a/a7/Weight_Sensor_Scales_Kit-_20KG_result.jpg/400px-Weight_Sensor_Scales_Kit-_20KG_result.jpg){ loading=lazy }

## Resource
--------

- [Demo code](https://wiki.elecrow.com/images/2/25/Hx711.zip)
- [HX711 datasheet](https://wiki.elecrow.com/images/2/2b/HX711.pdf)