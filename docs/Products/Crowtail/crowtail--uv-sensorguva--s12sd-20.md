---
title: Crowtail- UV sensor(GUVA- S12SD) 2.0
---

## Description
-----------

The Crowtail- UV Sensor(GUVA- S12SD) 2.0 is a module that can measures the intensity of ultraviolet light. It very suitable to measure the total amount of ultraviolet ray of sunlight, the response time is fast and have all interchangeability. It can aslo detect the 200-370nm UV wavelength.

Model: [CRT00542U](https://www.elecrow.com/crowtail-uv-sensor-guva-s12sd.html)

![UV sensor LED .jpg](https://wiki.elecrow.com/images/thumb/2/29/UV_sensor_LED_.jpg/500px-UV_sensor_LED_.jpg){ loading=lazy }

## Features
--------

- Operating voltage: 3.3v-5v
- Output voltage: DC0-1V
- Measuring accuracy: 1UV INDEX
- Response wavelength: 200nm-370nm
- Stable work: &lt;0.5s
- Operating current: typical value 0.03mA, maximum value 0.1mA

## Specification
-------------

Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

| Item | Description |
|:-:|:-:|
| LED Control Mode | Analog Pin of Arduino |
| Working Voltage | 5V |
| Supply Mode | Crowtail Interface |

## Application
-----------

Occasions where need to high reliability and accuracy measure the uv index(UVI).

## Usage
-----

1.Connect the LED to Base Shield's analog port A0 with 3pin Crowtail Cable.

![Uv sensor connect1.jpg](https://wiki.elecrow.com/images/thumb/4/49/Uv_sensor_connect1.jpg/500px-Uv_sensor_connect1.jpg){ loading=lazy }

2\. Plug it onto the Arduino/Crowduino. Connect the board to PC via USB cable.

![Uv sensor usb1.jpg](https://wiki.elecrow.com/images/thumb/5/55/Uv_sensor_usb1.jpg/500px-Uv_sensor_usb1.jpg){ loading=lazy }

3.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
#define vref 4.9
void setup(){

    Serial.begin(9600);

}

void loop()
{
    int sensorValue;
    long  sum=0;
    for(int i=0;i<10;i++)// accumulate readings for 1024 times
    {
        sensorValue=analogRead(A0);
        sum=sensorValue+sum;
    //    delay(2);
    }
    long meanVal = sum/10;  // get mean value
    float vout=meanVal*vref;
    Serial.print("vout is :");
    Serial.print(vout,2);
    Serial.print("\n");
    if(vout<=90)
    {
    Serial.print("The current UV index is:");
    Serial.println(0);// get a detailed calculating expression for UV index in schematic files.
    //Serial.print("\n");
    }
    else
    {
    Serial.print("The current UV index is:");
    Serial.println(1E-06*vout*vout+0.008*vout-0.715,2);// get a detailed calculating expression for UV index in schematic files.
  //  Serial.print("\n");
    }
    delay(1000);

}
```

4.After successfully upload the code. Open the monitor and observe the data, as below:

![Uv sensor off.jpg](https://wiki.elecrow.com/images/thumb/a/a3/Uv_sensor_off.jpg/500px-Uv_sensor_off.jpg){ loading=lazy }

5.And then, take the sensor in the sunshine, observe the data:

![Uv sensor on.jpg](https://wiki.elecrow.com/images/thumb/7/7b/Uv_sensor_on.jpg/500px-Uv_sensor_on.jpg){ loading=lazy }

## Resource
--------

- [uv sensor code](../../files/Uv-sensor-code-zip.md)
- [uv sensor schematic](../../files/Uv-sensor-schematic-zip.md)