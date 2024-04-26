---
title: Crowtail- Air Quality Sensor
---

## Description
-----------

This sensor is designed for comprehensive monitor over indoor air condition. It's responsive to a wide scope of harmful gases, as carbon monixide, alcohol, acetone, thinner, formaldehyde and so on. Due to the measuring mechanism, this sensor can not output specific data to describe target gases' concentrations quantitatively. But it's still competent enough to be used in applications that require only qualitative results, like auto refresher sprayers and auto air cycling systems.  
**Model: [CT009989A](http://www.elecrow.com/crowtail-air-quality-sensor-p-1650.html)**

![Crowtail- Air Quality Sensor.jpg](https://wiki.elecrow.com/images/thumb/b/b0/Crowtail-_Air_Quality_Sensor.jpg/600px-Crowtail-_Air_Quality_Sensor.jpg){ loading=lazy }

## Features
--------

- Responsive to a wide scope of target gases
- Cost efficient
- Durable
- Compatible with 5V
- Dimensions(mm):40.0(L)x20.0(W)x10.2(H)

## Cautions
--------

- Requires relatively clean air as an initial condition.
- Long time exposure to highly polluted air can significantly weaken its sensitivity.
- Coffre-fort et armoire forte.

## Usage
-----

### **With Arduino**

As described in Introduction, this sensor does better in providing qualitative results over a wide scope of target gases. In this demo, we define 4 statuses for reference in the .cpp file. They are:

```
a. air fresh -- indicating a good air condition
b. low pollution -- indicating a rather low concentration of target gases exist.
c. high pollution(without "Force signal active" message printed on serial monitor) -- you should be aware of the pollution level and consider if some measures could be taken.
d. high pollution(with "Force signal active" message printed on serial monitor) -- instant measures should be taken to improve the air quality.
```

We encapsulated the decision structure in a .cpp file. You can find info in there on how to modify the thresholds. Let's try it out!

## Getting Started
---------------

1\. Connect the Crowtail- Air Quality Sensor to A0 port as shown in the above picture.
 [![201605311524001.jpg](https://wiki.elecrow.com/images/thumb/c/c9/201605311524001.jpg/400px-201605311524001.jpg){ loading=lazy }

2\. Download the File :[AirQuality\_Sensor Library](../../files/AirQuality-zip.md)

3\. Wait at least 2 minutes after powering on for heat-up of the sensor. Then open the example below by the path: File -&gt; Example -&gt;AirQuality-&gt;AirQuality\_Sensor

```
<syntaxhighlight lang="Arduino">
#include"AirQuality.h"
#include"Arduino.h"
AirQuality airqualitysensor;
int current_quality =-1;
void setup()
{
    Serial.begin(9600);
    airqualitysensor.init(14);
}
void loop()
{
    current_quality=airqualitysensor.slope();
    if (current_quality >= 0)// if a valid data returned.
    {
        if (current_quality==0)
            Serial.println("High pollution! Force signal active");
        else if (current_quality==1)
            Serial.println("High pollution!");
        else if (current_quality==2)
            Serial.println("Low pollution!");
        else if (current_quality ==3)
            Serial.println("Fresh air")
}
}
```

4.When you upload the code complete,you can see the result via the serial port debug window.

![160531161709.jpg](https://wiki.elecrow.com/images/thumb/6/64/160531161709.jpg/400px-160531161709.jpg){ loading=lazy }

## Resource
--------

- [Crowtail- Air Quality Sensor eagle files](../../files/Crowtail-Air-Quality-Sensor-eagle-files-zip.md)
- [AirQuality\_Sensor Library](../../files/AirQuality-zip.md)