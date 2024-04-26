---
title: Crowtail- Relay
---

## Description
-----------

The Crowtail- Relay module is a digital normally-open switch. Through it, you can control circuit of high voltage with low voltage, say 5V on the controller.

**Model: [CT0008RE](http://www.elecrow.com/crowtail-relay-p-1232.html)**

![Crowtail- Relay.JPG](https://wiki.elecrow.com/images/thumb/c/c8/Crowtail-_Relay.JPG/600px-Crowtail-_Relay.JPG){ loading=lazy }

## Features
--------

- High Switching Current

## Specification
-------------

Dimensions(mm):40.0(L)x20.0(W)x17.2(H)

| Parameter | Description |
|:-:|:-:|
| Operating Voltage | 5V |
| Operating Current | 90mA |
| Relay Life | 100,000 Cycle |
| Max Switching Voltage | 120VAC/24VDC |
| Max Switching Current | 3A |

## Usage
-----

### **Intelligent Temperature Control Fan**

1.Hardware Connection

![Relaycontrol1.jpg](https://wiki.elecrow.com/images/6/60/Relaycontrol1.jpg){ loading=lazy }

2.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.You can set a threshold temperature value to control the realy ON or OFF, then control the fan work or not.

```
/*
Temperature sensor connect to AO
Relay connetct to D5
*/

#include <math.h>
int a;
float temperature;
int B=3975;                  //B value of the thermistor
float resistance;
// Connect the Relay to digital pin D5.
// give it a name:
int Relay = 5;

void setup()
{
 // initialize the digital pin as an output.
 pinMode(Relay, OUTPUT);  
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
   if(temperature>20)
   {
         digitalWrite(Relay, HIGH);  //if temperature >20 degree,turn the Relay on,fan working
   }
   else
   {
        digitalWrite(Relay, LOW);//if temperature <=20 degree,turn the Relay off,fan not working
   }
}
```

3.When the temperature above 20 degrees,the fan will working.

![Relay result.jpg](https://wiki.elecrow.com/images/thumb/8/82/Relay_result.jpg/400px-Relay_result.jpg){ loading=lazy } 
![Relay result1.jpg](https://wiki.elecrow.com/images/thumb/7/75/Relay_result1.jpg/600px-Relay_result1.jpg){ loading=lazy }

## Resource
--------

- [Relay Program](../../files/Relay-zip.md)
- [DSM501 Dust Sensor Datasheet](../../files/DSM501-pdf.md)