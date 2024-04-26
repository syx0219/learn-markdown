---
title: Non-invasive AC Current Sensor-100A
---

## Description
-----------

The AC current sensor is based on Current transformers, it transforms the big AC current to little, and then convert to voltage with the build-in resistor so users can get the AC current value via measuring the output voltage with any microcontroller such as Arduino. The split core type makes this sensor suitable for DIY usage such as energy monitoring for house &amp; building.  
**Model:[SEL98100NI](http://www.elecrow.com/noninvasive-ac-current-sensor100a-p-823.html)**  

![Non-invasive AC Current Sensor-100A.jpg](https://wiki.elecrow.com/images/thumb/1/11/Non-invasive_AC_Current_Sensor-100A.jpg/400px-Non-invasive_AC_Current_Sensor-100A.jpg){ loading=lazy }

## Feature
-------

- Input Current: 0~100A AC
- Output Mode: 0~50mA
- Non-linearity: ±3%
- Turn Ratio: 100A:0.05A
- Resistance Grade: Grade B
- Work Temperature: -25°C ~ ﹢70°C
- Dielectric Strength(between shell and output): 1000V AC/1min 5mA
- Leading Wire in Length: 1m
- Open Size: 13mm x 13mm

## Specification
-------------

![2009511142810295.jpg](https://wiki.elecrow.com/images/a/aa/2009511142810295.jpg){ loading=lazy }

## Usage
-----

1.Hardware connection

![AC Current Sensor-100A hardware2.png](https://wiki.elecrow.com/images/thumb/6/60/AC_Current_Sensor-100A_hardware2.png/600px-AC_Current_Sensor-100A_hardware2.png){ loading=lazy } 
![AC Current Sensor-100A hardware.png](https://wiki.elecrow.com/images/a/ae/AC_Current_Sensor-100A_hardware.png){ loading=lazy }

2.Download the library [EmonLib](https://wiki.elecrow.com/images/6/63/EmonLib.zip);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.  
3.Open the code directly by the path:File -&gt; Example -EmonLib-&gt;current only.

```
// EmonLibrary examples openenergymonitor.org, Licence GNU GPL V3

#include "EmonLib.h"                   // Include Emon Library
EnergyMonitor emon1;                   // Create an instance

void setup()
{  
  Serial.begin(9600);
  
  emon1.current(A1, 111.1);             // Current: input pin, calibration.
}

void loop()
{
  double Irms = emon1.calcIrms(1480);  // Calculate Irms only
  Serial.print("Apparent power:");
  Serial.print(Irms*230.0);	       // Apparent power
  Serial.print(" ");
  Serial.print("Irms:");
  Serial.println(Irms);		       // Irms
}
```

4.Upload the Code,then open the serial monitor. You should the test result.

![AC Current Sensor-100A result.jpg](https://wiki.elecrow.com/images/thumb/7/7e/AC_Current_Sensor-100A_result.jpg/400px-AC_Current_Sensor-100A_result.jpg){ loading=lazy }

### **Resource**

- [EmonLib](https://wiki.elecrow.com/images/6/63/EmonLib.zip)
- [SCT013 Datasheet](https://wiki.elecrow.com/images/1/10/SCT013-000_datasheet.pdf)
- [How to build an Arduino energy monitor](http://openenergymonitor.org/emon/buildingblocks/how-to-build-an-arduino-energy-monitor-measuring-current-only)
- [CT sensors - Interfacing with an Arduino](http://openenergymonitor.org/emon/buildingblocks/ct-sensors-interface)
- [CT sensors - An introduction](http://openenergymonitor.org/emon/buildingblocks/ct-sensors-introduction)