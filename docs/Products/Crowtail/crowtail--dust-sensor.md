---
title: Crowtail- Dust Sensor
---

## Description
-----------

A NEW Crowtail product! we add a crowtail port for pluging into crowtail base board. so it can simple use for our Crowduino. The dust sensor module DSM501A is low cost, compact size for a particle density sensor.it is used to quantitative particle (&gt; 1 micron) measurement with the principle of particle counter, can sense the tobacco smoke and pollen, house dust . This sensor is consist of light emitting diode lamp, detector, signal amplifier circuit and heater, it can be used in applications such as the air cleaner or air purifier, users can used this sensor easily with sensor PWM output.  
**Model: [CT0039DSD](http://www.elecrow.com/crowtail-dust-sensor-dsm501a-p-1484.html)**

![Crowtail- Dust Sensor011.jpg](https://wiki.elecrow.com/images/thumb/0/0e/Crowtail-_Dust_Sensor011.jpg/400px-Crowtail-_Dust_Sensor011.jpg){ loading=lazy }

## Feature
-------

- PWM Output
- Compact size and lightweight
- Easy installation
- 5V Single power supply
- Dimensions(mm):58.5(L)x45.0(W)x18.5(H)

## Usage
-----

1.Hardware connection

![Crowtail- Dust Sensor11.jpg](https://wiki.elecrow.com/images/thumb/d/df/Crowtail-_Dust_Sensor11.jpg/600px-Crowtail-_Dust_Sensor11.jpg){ loading=lazy }

2.Copy and paste code below to a new Arduino sketch:

```


#include<string.h>
byte buff[2];
int pin = 8;//DSM501A input D8
unsigned long duration;
unsigned long starttime;
unsigned long endtime;
unsigned long sampletime_ms = 30000;
unsigned long lowpulseoccupancy = 0;
float ratio = 0;
float concentration = 0;
 
int i=0;
void setup()
{
  Serial.begin(9600);
  pinMode(8,INPUT);
  starttime = millis(); 
}
void loop()
{
  duration = pulseIn(pin, LOW);
  lowpulseoccupancy += duration;
  endtime = millis();
  if ((endtime-starttime) > sampletime_ms)
  {
    ratio = (lowpulseoccupancy-endtime+starttime + sampletime_ms)/(sampletime_ms*10.0);  // Integer percentage 0=>100
    concentration = 1.1*pow(ratio,3)-3.8*pow(ratio,2)+520*ratio+0.62; // using spec sheet curve
    Serial.print("lowpulseoccupancy:");
    Serial.print(lowpulseoccupancy);
    Serial.print("    ratio:");
    Serial.print(ratio);
    Serial.print("    DSM501A:");
    Serial.println(concentration);
    lowpulseoccupancy = 0;
    starttime = millis();
  } 
}
```

4.Open the serial monitor. You should the test result.

![DSM501A result.jpg](https://wiki.elecrow.com/images/thumb/2/24/DSM501A_result.jpg/400px-DSM501A_result.jpg){ loading=lazy }

## Resource
--------

- [DSM501A demo code](../../files/DSM501A-zip.md)
- [DSM501 Dust Sensor Datasheet](../../files/DSM501-pdf.md)