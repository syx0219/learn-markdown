---
title: Crowbits-80cm Infrared Proximity Sensor
---

## Description
-----------

The Sharp distance sensors are a popular choice for many projects that require accurate distance measurements. This IR sensor is more economical than sonar rangefinders, yet it provides much better performance than other IR alternatives. Interfacing to most microcontrollers is straightforward: the single analog output can be connected to an analog-to-digital converter for taking distance measurements, or the output can be connected to a comparator for threshold detection

![Crowbits-80cm Infrared Proximity Sensor 1.jpg](https://wiki.elecrow.com/images/thumb/4/4e/Crowbits-80cm_Infrared_Proximity_Sensor_1.jpg/600px-Crowbits-80cm_Infrared_Proximity_Sensor_1.jpg){ loading=lazy }

## Features
--------

- High precision
- Easy to use

## Specification
-------------

- Distance measuring range: 10 cm to 80 cm (4" to 32")
- Operating voltage: 3.3V
- Response time: 38 ± 10ms

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the A0 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-80cm Infrared Proximity Sensor-Wiki 1.jpg](https://wiki.elecrow.com/images/thumb/6/68/Crowbits-80cm_Infrared_Proximity_Sensor-Wiki_1.jpg/600px-Crowbits-80cm_Infrared_Proximity_Sensor-Wiki_1.jpg){ loading=lazy }

3.Upload the following code to the Crowbits-UNO board.

```
/*
 *      
 *      VCC -- VCC  
 *      GND -- GND  
 *      Signal -- Analog 0 
 */
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

4.After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Place an object in front of the sensor and the serial port will print its distance.

![Crowbits-80cm Infrared Proximity Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/7/79/Crowbits-80cm_Infrared_Proximity_Sensor-Wiki_2.jpg/600px-Crowbits-80cm_Infrared_Proximity_Sensor-Wiki_2.jpg){ loading=lazy }