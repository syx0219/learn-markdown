---
title: Crowtail- LiPo Fuel Gauge
---

## **Introduction**
----------------

Don’t worry about next time your board suddenly powers-down! The Crowtail- LiPo Fuel Gauge connects your battery to your project and uses a sophisticated algorithm to detect relative state of charge and direct A/D measurement of battery voltage. In other words, it tells your microcontroller how much ‘fuel’ is left in the tank. The LiPo Fuel Gauge communicates with your project over I2C and an alert pin also tells you when the charge has dropped below a certain percentage.

**Model:** [CRT00413L](https://www.elecrow.com/crowtail-lipo-fuel-gauge.html)

![Crowtail- LiPo Fuel Gauge.jpg](https://wiki.elecrow.com/images/thumb/b/b3/Crowtail-_LiPo_Fuel_Gauge.jpg/500px-Crowtail-_LiPo_Fuel_Gauge.jpg){ loading=lazy }

## **Features**
------------

Fuel gauge system for single cell lithium ion batteries

Can be connected in circuit to monitor battery.

Hardware and Software Reset.

Corwtail I2C Interface

Dimensions(mm):40.0(L)x20.0(W)x7.2(H)

## **Interface**
-------------

![ExamEWETple.png](https://wiki.elecrow.com/images/thumb/b/b0/ExamEWETple.png/500px-ExamEWETple.png){ loading=lazy }

## **Usage**
---------

The Crowtail- LiPo Fuel Gauge is connecting to IIC port of Crowtail - Base Shield.

![Exampssgle1.jpg](https://wiki.elecrow.com/images/thumb/1/15/Exampssgle1.jpg/600px-Exampssgle1.jpg){ loading=lazy }

Download "[MAX17043.lib](../../files/MAX17043-zip.md)" for arduino boards, unzip and put it in the libraries of Arduino IDE by the path : ..\\arduino-1.x.x\\libraries;

open "ReadTag" example via the path: File--&gt;Examples--&gt;MAX17043--&gt;VoltageSoC.ino.

```
#include "MAX17043.h"
#include "Wire.h"

MAX17043 batteryMonitor;

void setup() {
  
  Wire.begin(); 
  Serial.begin(9600);
  Serial.println("MAX17043 Example: reading voltage and SoC");
  Serial.println();
  
  batteryMonitor.reset();
  batteryMonitor.quickStart();
  Serial.print("verison is :");
  Serial.println(batteryMonitor.getVersion(),4);
  delay(1000);
  
  
}

void loop() {    
  get_infor();
  delay(1000);
}
void get_infor()
{

  float cellVoltage = batteryMonitor.getVCell();
  Serial.print("Voltage:\t\t");
  Serial.print(cellVoltage, 4);
  Serial.println("V");

  float stateOfCharge = batteryMonitor.getSoC();
  Serial.print("State of charge:\t");
  Serial.print(stateOfCharge);
  Serial.println("%");
  }
```

Upload it into your arduino board and open the serial monitor to monitor the battery "fuel".

![Examplgdge.png](https://wiki.elecrow.com/images/e/e0/Examplgdge.png){ loading=lazy }