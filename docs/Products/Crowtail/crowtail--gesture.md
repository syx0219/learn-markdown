---
title: Crowtail- Gesture
---

## Description
-----------

The sensor on Crowtail- Gesture is PAJ7620U2 that integrates gesture recognition function with general I2C interface into a single chip. It can recognize 9 basic gestures ,and these gestures information can be simply accessed via the I2C bus.

Application: You can use Gesture as an input device to control another Cowtail, or a computer, mobile phone, smart car, robot, and more with a simple swipe of your hand.

**Model: [CT010628G](https://www.elecrow.com/crowtail-gesture-p-1674.html)**

![Crowtail- Gesture.jpg](https://wiki.elecrow.com/images/thumb/5/52/Crowtail-_Gesture.jpg/600px-Crowtail-_Gesture.jpg){ loading=lazy }

## Features
--------

1 See 9 gestures in the following figure

![110823.png](https://wiki.elecrow.com/images/8/8c/110823.png){ loading=lazy }

2 Built-in proximity detection

3 Various main boards support : Arduino UNO/Crowduino/Arduino Mega2560

## Specification
-------------

Dimensions(mm):20.0(L)x20.0(W)x11.8(H)

| Sensor | PAJ7620U2 |
|---|---|
| Power supply | 5V |
| Ambient light immunity | &lt; 100k Lux |
| Gesture speed in Normal Mode | 60°/s to 600°/s |
| Gesture speed in Gaming Mode | 60°/s to 1200°/s |
| Interface type | IIC interface up to 400 kbit/s |
| Operating Temperature | -40°C to +85°C |

## Usage
-----

### **Hardware Installation**

1.Connect this Crowtail- Gesture module to the I2C port of Base Shield.

2.The red led connect to D5 port,yellow led connect to D4 port,green led connect to D3 port.

![1605271105411.jpg](https://wiki.elecrow.com/images/thumb/e/ec/1605271105411.jpg/600px-1605271105411.jpg){ loading=lazy }

3.Download the library code as a zip file [Gesture\_PAJ7620](https://wiki.elecrow.com/images/7/72/Paj7620.zip).

3.Unzip the downloaded file into your …/arduino/libraries.

4.The following simple demo will show you a very easy application:

- When you move left to right, the red led will be turned on, the opposite gesture ,the red led will be turned off.

- When you move front to back, the green led will be turned on, the opposite gesture , the green led will be turned off.

- When you move top to bottom, the yellow led will be turned on, the opposite gesture , the green led will be turned off.

```
#include <Wire.h>
#include "paj7620.h"
int led1 = 5; 
int led2 = 4;
int led3 = 3;
void setup()
{
  paj7620Init();
  pinMode(led1, OUTPUT);    
   pinMode(led2, OUTPUT); 
    pinMode(led3, OUTPUT);  
}
 
void loop()
{
	uint8_t data = 0;  // Read Bank_0_Reg_0x43/0x44 for gesture result.
 
	paj7620ReadReg(0x43, 1, &data); 
	if (data == GES_UP_FLAG) 							
	{digitalWrite(led1, HIGH); 
	}			        
	if (data == GES_DOWN_FLAG) 
{	digitalWrite(led1, LOW); 					
       }  
       	if(data == GES_FORWARD_FLAG) 
       {
       digitalWrite(led2, HIGH);
       }
       if(data == GES_BACKWARD_FLAG)
       {digitalWrite(led2, LOW); 
       }
       if(data == GES_RIGHT_FLAG)
       {digitalWrite(led3, HIGH);
       }
       if(data ==GES_LEFT_FLAG)
       {
         digitalWrite(led3, LOW); 
       }
       				    
}
```

## Resource
--------

- [Gesture\_PAJ7620](https://wiki.elecrow.com/images/7/72/Paj7620.zip)
- [Crowtail- Gesture eagle file](https://wiki.elecrow.com/images/0/0b/Crowtail-_Gesture_eagle_file.zip)