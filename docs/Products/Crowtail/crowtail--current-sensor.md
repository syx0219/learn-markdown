---
title: Crowtail- Current Sensor
---

## Description
-----------

This current sensor gives precise current measurement for both AC and DC signals. These are good sensors for metering and measuring overall power consumption of systems. The ACS712 current sensor measures up to 20A of DC or AC current. The ACS712 Low Current Sensor Breakout outputs an analog voltage that varies linearly with sensed current. To calibrate, first set the output offset to the desired level (with zero current on the sense lines, read output with a DVM). Then with a known current input (a 100mA limited supply works well for this), set the output deflection with the gain pot. Sensitivity is then calculated as (Vref - Vdeflect)/(current input).

**Model: [CT0029CS](http://www.elecrow.com/crowtail-current-sensor-p-1309.html)**

![Crowtail-Current Sensor.JPG](https://wiki.elecrow.com/images/thumb/c/c2/Crowtail-Current_Sensor.JPG/600px-Crowtail-Current_Sensor.JPG){ loading=lazy }

## Features
--------

- Voltage: 5V
- MAX current:20A
- Dimensions(mm):40.0(L)x20.0(W)x6.8(H)

## Usage
-----

Arduino test the crrrent.

1.Hardware connection

Connect the Crowtail- Current Sensor to A0.

![Currenthware11.jpg](https://wiki.elecrow.com/images/thumb/e/ec/Currenthware11.jpg/600px-Currenthware11.jpg){ loading=lazy } 
![Currenthware1.jpg](https://wiki.elecrow.com/images/thumb/f/fe/Currenthware1.jpg/600px-Currenthware1.jpg){ loading=lazy }

2.Connect the board to PC using USB cable.

3.Upload the following sample sketch:

```
void setup() {
  Serial.begin(9600);
}
 
void loop() {
 float average = 0;
 for(int i = 0; i < 1000; i++) {
// average = average + (.0264 * analogRead(A0) -13.51);//for the 5A mode,  
   average = average + (.049 * analogRead(A0) -25);// for 20A mode
// average = average + (.742 * analogRead(A0) -37.8);// for 30A mode
   delay(1);
 }
 Serial.print("Current :");
 Serial.print(average/1000);
 Serial.println("A");
}
```

4.Open the serial monitor.You can see the current you test.

![Currentresult1.jpg](https://wiki.elecrow.com/images/thumb/e/e3/Currentresult1.jpg/400px-Currentresult1.jpg){ loading=lazy }

## Resource
--------

- [Current Sensor Program](https://wiki.elecrow.com/images/6/60/Current_Sensor.zip)
- [Crowtail- Current Sensor ACS712 eagle files](https://wiki.elecrow.com/images/7/74/Crowtail-Current_Sensor_ACS712_eagle_files.zip)
- [ACS712.pdf](../../files/ACS712-pdf.md)