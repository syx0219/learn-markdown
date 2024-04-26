---
title: Crowtail- Non-contact liquid level sensor
---

## Description
-----------

Intelligent non-contact liquid level sensor (here in after referred to as the liquid level sensor) adopted the advanced signal processing technology and high-speed signal processing chip, broke through the vessel wall thickness, the influence of realized in an airtight container level of real non-contact detection.Liquid level sensor (probe) installed on the outer wall of the container to be tested on the lower part (level of high and low), non-metallic containers without the hole, easy to install, do not affect production.Can realize various toxic substances of high pressure airtight container, strong acid, strong alkali and all kinds of liquid level detection.The material of liquid level sensor for liquid medium and container no special requirements, can be widely used.

**Model: [CT008998L](http://www.elecrow.com/crowtail-noncontact-liquid-level-sensor-p-1656.html)**  
![Crowtail- Non-contact liquid level sensor1.jpg](https://wiki.elecrow.com/images/thumb/1/12/Crowtail-_Non-contact_liquid_level_sensor1.jpg/500px-Crowtail-_Non-contact_liquid_level_sensor1.jpg){ loading=lazy }

## Feature
-------

- No direct contact with liquid
- NPN output
- Working Voltage: 5V～24V
- Induction distance can reach more than 12 mm
- Crowtail Interface
- Easy to use

## Specification
-------------

Power flow 5 mA

Output voltage (high level) InVCC

Output voltage (low level) 0 v

The output current 1 ～ 50 mA

The response time 500 ms

Working environment temperature 0 ～100 ℃

The thickness of the induction (sensitivity) 0 ～ 20 mm

humidity 5% ～ 100%

The material ABS.

Waterproof properties IP67

Sensor dimensions(mm):28.3(L)x28.3(W)x17.0(H)

Cable length:58.5cm

## Usage
-----

Here is an example showing how to turn on the Crowtail- PP Plastic Float Switch.

1.Plug it onto the Digital port 2 of Crowtail - Base Shield using a Crowtail cable ,and plug a buzzer onto Digital port 5 .

2.Plug the Crowtail - Base Shield onto Arduino.

3\. Connect Arduino to PC by using a USB cable.

![Non-contact liquid level sensor.jpg](https://wiki.elecrow.com/images/thumb/5/55/Non-contact_liquid_level_sensor.jpg/600px-Non-contact_liquid_level_sensor.jpg){ loading=lazy }

4.Stick the Non-contact liquid level sensor on the outside of the container on the surface of a certain height.

5\. Copy and paste code below to a new Arduino sketch, and upload it to your Arduino.

```
 int liquid_level=2;
int buzzer=5;
int liquid_state=0;

void setup()
{
   pinMode( liquid_level,INPUT);
   pinMode(buzzer,OUTPUT);
}

void loop()
{
 liquid_state=digitalRead(liquid_level);
 if(liquid_state==HIGH)
 {
 digitalWrite(buzzer,HIGH);
 }
 else
 {
  digitalWrite(buzzer,LOW);
 }
}
```

6.When you upload the code complete,you can Pour water into the container, when the water level and the Non-contact liquid level sensor keep the same height, the indicator light on and the buzzer alarm.