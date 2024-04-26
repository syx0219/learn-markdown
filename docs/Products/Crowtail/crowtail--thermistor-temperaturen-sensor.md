---
title: Crowtail- Thermistor Temperaturen Sensor
---

## Description
-----------

The Crowtail- Thermistor Temperature Sensor uses a Thermistor to detect the ambient temperature. The resistance of a thermistor will increase when the ambient temperature decreases. It's this characteristic that we use to calculate the ambient temperature.The detection range of this sensor is between -40 to 125 degrees Celsius with an accuracy of ±1.5℃. However it doesn’t output the temperature value directly. To get the specific temperature value, we will use the formula in the code below.The Crowtail- Thermistor Temperaturen Sensor uses a Thermistor to detect the ambient temperature. The resistance of a thermistor will increase when the ambient temperature decreases. It's this characteristic that we use to calculate the ambient temperature.The detection range of this sensor is between -40 to 125 degrees Celsius with an accuracy of ±1.5℃. However it doesn’t output the temperature value directly. To get the specific temperature value, we will use the formula in the code below.

**Model: [Crowtail- Thermistor Temperature Sensor](http://www.elecrow.com/crowtail-thermistor-temperature-sensor-p-1268.html)**

![Crowtail-Thermistor Temperaturen Sensor.JPG](https://wiki.elecrow.com/images/thumb/7/73/Crowtail-Thermistor_Temperaturen_Sensor.JPG/600px-Crowtail-Thermistor_Temperaturen_Sensor.JPG){ loading=lazy }

## Features
--------

- Voltage: 3.3 ~ 5V
- Max power rating at 25℃: 300mW
- Zero power resistance: 10 KΩ
- Operating temperature range: -40 ~ +125 ℃
- Dimensions(mm):22.0(L)x20.0(W)x9.7(H)

## Usage
-----

Here is an example to show you how to read temperature information from the sensor.

1.Connect the module to the Analog port 0 of Crowtail - Basic Shield using the 3-pin grove cable.

2\. Plug the Crowtail - Basic Shield into Arduino.

3\. Connect Arduino to PC by using a USB cable.

![Temperaturehardware1.jpg](https://wiki.elecrow.com/images/thumb/a/aa/Temperaturehardware1.jpg/600px-Temperaturehardware1.jpg){ loading=lazy }

4.Upload the following sample sketch:

```
#include <math.h>
int a;
float temperature;
int B=3975;                  //B value of the thermistor
float resistance;

void setup()
{
   Serial.begin(9600);  
}

void loop()
{
   a=analogRead(0);
   resistance=(float)(1023-a)*10000/a; //get the resistance of the sensor;
   temperature=1/(log(resistance/10000)/B+1/298.15)-273.15;//convert to temperature via datasheet ;
   delay(1000);
   Serial.print("Current temperature is ");
   Serial.println(temperature);
}
```

5.Open the serial monitor. You should see current temperature.

![Temperatureresult.jpg](https://wiki.elecrow.com/images/thumb/1/17/Temperatureresult.jpg/400px-Temperatureresult.jpg){ loading=lazy }

## Resource
--------

- [Crowtail- Thermistor Temperature Sensor Program](https://wiki.elecrow.com/images/5/56/Thermistor_Temperature_sensor.zip)
- [Crowtail- Thermistor Temperature Sensor \_eagle\_files](https://wiki.elecrow.com/images/2/29/Crowtail-Thermistor_Temperaturen_Sensor_eagle_files.zip)