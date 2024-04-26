---
title: Weight Sensor Amplifier-HX711
---

## Description
-----------

This Weight Sensor amplifier is based on HX711,which consist of an amplifier and a precision 24-bit analog-to-digital convertor designed for weigh scale and industrial control applications to interface directly with a bridge sensor. Compared with other chips, HX711 not only has a few basic function, also contains high integration, fast response, immunity, and other features. The chip lowed the cost of the electronic scale, at the same time, improving the performance and reliability. The input interface of this weight sensor module is used sensor interface, which is compatible with Arduino I/O ports. The output adopts compact terminal that makes weight sensor module easier to connect the weight sensor. It's the best choose for electronic enthusiast to do some tiny home scale.

**Model: [SHX711O](https://www.elecrow.com/weight-sensor-amplifier-hx711-p-715.html)**  
![Weight sensor amplifier HX711.jpg](https://wiki.elecrow.com/images/thumb/7/79/Weight_sensor_amplifier_HX711.jpg/500px-Weight_sensor_amplifier_HX711.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/weight-sensor-amplifier-hx711-p-715.html?wiki "Title text")

## Schematic
---------

![Hx711 sch.jpg](https://wiki.elecrow.com/images/thumb/a/a8/Hx711_sch.jpg/800px-Hx711_sch.jpg){ loading=lazy }

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