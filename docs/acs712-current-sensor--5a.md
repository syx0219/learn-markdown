---
title: ACS712 Current Sensor- 5A
---

## Description
-----------

Sensing and controlling current flow is a fundamental requirement in a wide variety of applications including, over-current protection circuits, battery chargers, switching mode power supplies, digital watt meters, programmable current sources, etc. This ACS721 current module is based on ACS712 sensor, which can accurately detect AC or DC current. The maximum AC or DC that can be detected can reach 5A, and the present current signal can be read via analog I / O port of Arduino.

**Model:[SEL7125A](http://www.elecrow.com/acs712-current-sensor-5a-p-707.html)**

![ACS712 Current Sensor- 5A.jpg](https://wiki.elecrow.com/images/thumb/b/b3/ACS712_Current_Sensor-_5A.jpg/400px-ACS712_Current_Sensor-_5A.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/acs712-current-sensor-5a-p-707.html?wiki "Title text")

## Features
--------

- Supply Voltage: 4.5V~5.5V DC
- Measure Current Range: -5A~ 5A
- Sensitivity: 180mV/A ~190mV/A, Typical: 185mV/A

## Usage
-----

Arduino test the crrrent.

1.Hardware connection


![ACS712.jpg](https://wiki.elecrow.com/images/c/cc/ACS712.jpg){ loading=lazy } [600px]("File:ACS7122.jpg")

Notice:Current sensor can not directly connect on both ends of the power supply.

2.Connect the board to PC using USB cable.

3.Upload the following sample sketch:

```
void setup() {
  Serial.begin(9600);
}
 
void loop() {
 float average = 0;
 for(int i = 0; i < 1000; i++) {
     average = average + (.0264 * analogRead(A0) -13.51);//for the 5A mode,  
//   average = average + (.049 * analogRead(A0) -25);// for 20A mode
// average = average + (.742 * analogRead(A0) -37.8);// for 30A mode
   delay(1);
 }
 Serial.print("Current :");
 Serial.print(average/1000);
 Serial.println("A");
}
```

4.Open the serial monitor.You can see the current you test.

![ACS712tresult1.jpg](https://wiki.elecrow.com/images/thumb/9/97/ACS712tresult1.jpg/400px-ACS712tresult1.jpg){ loading=lazy }

## Resource
--------

- [Demo code](./files/ACS712-zip.md)
- [ACS712.pdf](./files/ACS712-pdf.md)