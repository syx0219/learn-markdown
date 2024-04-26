---
title: Crowtail- 80cm Infrared Proximity Sensor
---

## Description
-----------

The Sharp distance sensors are a popular choice for many projects that require accurate distance measurements. This IR sensor is more economical than sonar rangefinders, yet it provides much better performance than other IR alternatives. Interfacing to most microcontrollers is straightforward: the single analog output can be connected to an analog-to-digital converter for taking distance measurements, or the output can be connected to a comparator for threshold detection.

**Model: [CT0038IPS](http://www.elecrow.com/crowtail-80cm-infrared-proximity-sensor-p-1483.html)**

![Crowtail- 80cm Infrared Proximity Sensor11.jpg](https://wiki.elecrow.com/images/thumb/9/98/Crowtail-_80cm_Infrared_Proximity_Sensor11.jpg/400px-Crowtail-_80cm_Infrared_Proximity_Sensor11.jpg){ loading=lazy }

## Specification
-------------

- Operating voltage: 4.5 V to 5.5 V
- Average current consumption: 30 mA (typical)
- Distance measuring range: 10 cm to 80 cm (4" to 32")
- Output type: analog voltage
- Output voltage differential over distance range: 1.9 V (typical)
- Response time: 38 ± 10 ms
- Weight: 3.5 g (0.12 oz)
- Dimensions(mm):44.5(L)x13.5(W)x19.0(H)

The detection range of this version is approximately 10 cm to 80 cm (4" to 32"); a plot of distance versus output voltage is shown below:  
![80cm Infrared Proximity Sensor-GP2Y0A21YK0F1.jpg](https://wiki.elecrow.com/images/0/00/80cm_Infrared_Proximity_Sensor-GP2Y0A21YK0F1.jpg){ loading=lazy }

## Usage
-----

The module detects one-axis rotation with analog signal.

1.Hardware Connection

![Crowtail- 80cm Infrared Proximity Sensor21.jpg](https://wiki.elecrow.com/images/thumb/c/c1/Crowtail-_80cm_Infrared_Proximity_Sensor21.jpg/600px-Crowtail-_80cm_Infrared_Proximity_Sensor21.jpg){ loading=lazy }

2.Copy the below code to you new skecth,then upload it.

```


#define pin A0
 
void setup () {
    Serial.begin (9600);
    pinMode (pin, INPUT);
}
 
void loop () {
    uint16_t value = analogRead (pin);
    uint16_t range = get_gp2d12 (value);
    Serial.print("Analog value:");
    Serial.println (value);
    Serial.print ("Distance:");
    Serial.print (range);
    Serial.println (" mm");
    Serial.println ();
    delay (500);
}
 
uint16_t get_gp2d12 (uint16_t value) {
    if (value < 10) value = 10;
    return ((67870.0 / (value - 3.0)) - 40.0);
}
```

3.Open the serial tool,you can see the distance:

![80cm Infrared Proximity Sensor-GP2Y0A21YK0F reslut.jpg](https://wiki.elecrow.com/images/thumb/6/62/80cm_Infrared_Proximity_Sensor-GP2Y0A21YK0F_reslut.jpg/400px-80cm_Infrared_Proximity_Sensor-GP2Y0A21YK0F_reslut.jpg)

## Resource
--------

- [Demo code](../../files/80-Infrared-Arduino-Demo-zip.md)
- [Datasheet](../../files/80-Infrare-Datasheet-pdf.md)