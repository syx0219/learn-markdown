---
title: Crowtail- Rotation Angle Sensor
---

## Description
-----------

This rotation Angle sensor using the SV01 series of PSV01A, excellent resistance materials and high reliability wiper achieves 1M cycles，dust-proof construction protects the interior from dust, which maintains stable characteristics.

**Model:** [CRT03345R](https://www.elecrow.com/crowtail-rotation-angel-sensor.html)

![Crowtail- Crowtail-Rotation Angle Sensor.jpg](https://wiki.elecrow.com/images/thumb/5/5d/Crowtail-_Crowtail-Rotation_Angle_Sensor.jpg/500px-Crowtail-_Crowtail-Rotation_Angle_Sensor.jpg){ loading=lazy }

## Features
--------

- Dust-proof construction protects the interior from dust, which maintains stable characteristics.
- Easy-to-use Crowtail compatible interface
- Supports analog interface
- D formation thru-hole rotor enables selection of any kind of gear shape.

## Specification
-------------

Category: Sensors, Transducers

Family: Position Sensors - Angle, Linear Position Measuring

Series: SV01

For Measuring: Rotary Position

Technology: Resistive

Resistance (Ohms): 10k

Rotation Angle - Electrical, Mechanical: 0°~333.3°

Actuator Type: Hole for Shaft

Linearity: ±2%

Resistance Tolerance: ±30%

Mounting Type: Surface Mount

Termination Style: SMD (SMT) Tab

Operating Temperature: -40°C ~ 85°C

Dimensions(mm):40.0(L)x20.0(W)x6.8(H)

## Usage
-----

1\. Plug it onto the Analog port 0 of Crowtail - Base Shield using a Crowtail cable.

2.Plug the Crowtail - Base Shield onto Arduino.

3\. Connect Arduino to PC by using a USB cable.

![Sdggfgd1.jpg](https://wiki.elecrow.com/images/thumb/9/9c/Sdggfgd1.jpg/600px-Sdggfgd1.jpg){ loading=lazy }

4.Copy and paste code below to a new Arduino sketch, and upload it to your Arduino.

```
const int analogInPin = A0;  // Analog input pin that the potentiometer is attached to

int sensorValue = 0; 
void setup() {
  // initialize serial communications at 9600 bps:
  Serial.begin(9600);
}

void loop() {
  // read the analog in value:
  sensorValue = analogRead(analogInPin);
    Serial.println(sensorValue);

  delay(1500);
}
```

5.When you upload the code complete,you can see the result via the serial port debug window.

![Exampldsagadse.png](https://wiki.elecrow.com/images/thumb/d/d5/Exampldsagadse.png/500px-Exampldsagadse.png){ loading=lazy }