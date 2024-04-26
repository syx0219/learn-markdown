---
title: Crowtail- Mini PIR Motion Sensor
---

## **Description**
---------------

The Crowtail- Mini PIR Motion Sensor is a compact, low power consumption and cost effective PIR sensor. It interfaces directly with up to two conventional PIR sensors via a high impedance different input. The PIR Signal is converted to a 15 bit digital value on chip. Is's used for making motion detecting applications such as alarm burglar systems, visitor presence monitoring, light switches and robots.

**Model:** [CRT00255P](https://www.elecrow.com/crowtail-mini-pir-motion-sensor.html)

![Crowtail- Mini PIR Motion Sensor.jpg](https://wiki.elecrow.com/images/thumb/d/d8/Crowtail-_Mini_PIR_Motion_Sensor.jpg/500px-Crowtail-_Mini_PIR_Motion_Sensor.jpg){ loading=lazy }

## **Features**
------------

Low power consumption

Digital signal processing（DSP）

Built-in filter, high immunity to RFI

Best detect distance:&gt;2m

Crowtail interface

## **Specification**
-----------------

Dimensions(mm):20.0(L)x20.0(W)x18.0(H)

Sensor chip:S16-L221D

Sensitivity:120 – 530 μV

Max detecting range:2m(25℃)

## **Application**
---------------

PIR motion detection, Intruder detection, Occupancy detection, Motion sensor lights, Computer monitor, Security system, Automatic control,etc.

## **Usage**
---------

This example show you how to make a simple alarm device.

The Crowtail- Mini PIR Motion Sensor is connecting to D2 port of Crowtail - Base Shield and connect the Corwtail LED to the D5 port.

![Exampledds1.jpg](https://wiki.elecrow.com/images/thumb/2/2c/Exampledds1.jpg/600px-Exampledds1.jpg){ loading=lazy }

Cope the code and upload it to your arduino board.

```


void setup() {
  // put your setup code here, to run once:
  pinMode(2 , INPUT);
    pinMode(5 , OUTPUT);
  Serial.begin(9600);
  
}

void loop() {
  // put your main code here, to run repeatedly:
int A = digitalRead ( 2);
Serial.println(A);
if(A==HIGH){
digitalWrite(5, HIGH);
}
else
digitalWrite(5,LOW);
delay(500);
}

```

Then it Alarm "lights" will be on if it detects the body is moving.

![Exaasfdmple2.jpg](https://wiki.elecrow.com/images/thumb/e/e2/Exaasfdmple2.jpg/600px-Exaasfdmple2.jpg){ loading=lazy }