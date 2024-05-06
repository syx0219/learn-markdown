---
title: 4MM Inductive Metal Proximity Sensor
---

## Description
-----------

Metal Proximity Sensor, which is also called non-contact proximity switch, it is composed of generator and shaping amplifier oscillator vibration in the switch after induction head, and produces an alternating magnetic field when the metal body detected.  
This Inductive Proximity Sensor has high sensitivity, fast frequency response, high repeat positioning accuracy and also stability and reliable, it can detects metal components in 0~4mm distance, and is widely used in modern industry, such as machinery, metallurgy, transportation, electric power, military industry and so on.

**Model:[SPM0409IP](http://www.elecrow.com/4mm-inductive-metal-proximity-sensor-p-1162.html)**

![4MM Inductive Metal Proximity Sensor.jpg](https://wiki.elecrow.com/images/thumb/b/b8/4MM_Inductive_Metal_Proximity_Sensor.jpg/400px-4MM_Inductive_Metal_Proximity_Sensor.jpg){ loading=lazy }

## Specification
-------------

- Working Voltage:DC 6~36V;
- Probe Demension: 12mm diameter;
- Sensoring Distance: 0~4mm
- Output signal: Low

## Usage
-----

1.Hardware Connection

![4MM Inductive Metal Proximity Sensor hardware.jpg](https://wiki.elecrow.com/images/thumb/2/24/4MM_Inductive_Metal_Proximity_Sensor_hardware.jpg/600px-4MM_Inductive_Metal_Proximity_Sensor_hardware.jpg){ loading=lazy }

2.Copy the below code to you new skecth,then upload it.

```
const int ledpin=5;
const int Sensor = 4;
void setup()
{
  pinMode(ledpin,OUTPUT);
  pinMode(Sensor,INPUT); 
}
void loop()
{
    if(digitalRead(Sensor))
    {
       digitalWrite(ledpin,LOW);
    }
    else{
        digitalWrite(ledpin,HIGH);
    }
}
```

3.The LED will light up when a metal gets closed to the metal proximity sensor(0-4mm).

## Resource
--------

- [Demo code](./files/Metal-Proximity-Sensor-zip.md)