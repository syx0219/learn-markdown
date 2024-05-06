---
title: Crowtail- Microwave sensor
---

## Description
-----------

A new product of crowtail family, it’s a microwave sensor module which is applies the Doppler effect to detect moving objects using microwaves.This differs from the method used by a regular infrared (IR) sensor as microwave is sensitive to a variety of objects that are microwave-reflective, and its sensor readings are not affected by the ambient temperature.This type of sensor is widely used in industrial, transportation and civil applications such as measuring vehicle speed, liquid levels, automatic door motion detection, automatic washing, production line material detection and car reversing sensors etc.

**Model: [CMS38743C](http://www.elecrow.com/crowtail-microwave-sensor-p-1636.html)**
![Crowtail- Microwave.jpg](https://wiki.elecrow.com/images/thumb/3/33/Crowtail-_Microwave.jpg/600px-Crowtail-_Microwave.jpg){ loading=lazy }

The microwave detection method has the following advantages compared to other methods:

```
  Non-contact detection
  Readings not affected by temperature, humidity, noise, air, dust or light - suitable for harsh environments
  Strong resistance to radio frequency interference
  Low output, urharmful to human
  Wide detection range and high velocity
  Supports non-living object detection
```

## Features
--------

- Working Voltage: 5V + 0.25V
- Working Current (CW): 60mA max., 37mA typical
- Interface: Crowtail 4-Pin interface（Digital）
- Dimensions(mm):63.0(L)x48.5(W)x8.0(H)
- Emission parameters:

```
    Detection Distance: 2-16M continuously adjustable
    Emission Frequency: 10.525 GHz
    Precision Frequency Setting: 3MHz
    Output Power (minimum): 13dBm EIRP
    Harmonic Emission: < -10dBm
    Average Current (5%DC): 2mA typ.
    Pulse Width (Min.): 5uSec
    Load Cycle (Min.): 1%
```

- Reception Parameters:

```
    Sensitivity:(10dB S/N ratio) 3Hz to 80Hz
    Bandwidth: -86dBm
    3Hz to 80Hz Bandwidth Clutter: 10uV
    Antenna Gain: 8dBi
    Vertical 3dB Beam Width: 36 degrees
    Level 3dB Beam Width: 72 degrees
```

## Sensor Module Description
-------------------------

### **Antenna Description**

![SEN0192.png](https://wiki.elecrow.com/images/thumb/0/01/SEN0192.png/500px-SEN0192.png){ loading=lazy }

### **Signal Processing**

The following diagram demonstrates the working principle of the sensor module. It works by amplifying a tiny signal which is received by the microwave sensor, and then through the comparison circuit it converts the signal into a square signal with a digital output of 0 or 1 which an Arduino or other micro controller can easily handle.

![SEN0192-001.png](https://wiki.elecrow.com/images/e/ee/SEN0192-001.png){ loading=lazy }

### **Signal Detection Range**

Detection Angle: The angle of detection is 72 degrees with the antenna in a parallel direction (azimuth) The vertical (pitch) direction of the antenna is 36 degrees.
![SEN0192-003.png](https://wiki.elecrow.com/images/thumb/9/9a/SEN0192-003.png/500px-SEN0192-003.png){ loading=lazy }

### **Install**

Microwaves can penetrate through walls.So sometimes it is inaccuracies when microwaves penetrate to outside walls and detect moving objects in non-target areas. Be sure to choose an installation location to avoid this! 
![SEN0192-004.png](https://wiki.elecrow.com/images/thumb/1/1c/SEN0192-004.png/500px-SEN0192-004.png){ loading=lazy }

### **Indicators and Output Status**

When the microwave sensor does not detect moving objects, the indicator LED remains off. When the sensor detects moving objects, the LED will turn on and the output level will be change from HIGH to LOW. The LED will automatically turn off about after 0.5s and the output level will change from LOW to HIGH. If the microwave sensor detects continuously moving objects the LED will keep flashing on and off. The output level will fluctuate between HIGH and LOW until the object stops moving.

## Usage
-----

The library of Microwave sensor we use that is MsTimer2.
You can download here:[MsTimer2 ](http://www.elecrow.com/wiki/images/1/1d/MsTimer2.zip)Check that the MsTimer2 contains MsTimer2.cpp and MsTimer2.h
Place the MsTimer2 library folder your arduino sketchfolder/libraries/ folder.
You may need to create the libraries subfolder if its your first library. Restart the IDE.

1.Keep the Microwave sensor in a smooth. connect it onto the digital 2 port .

![Microwave sensor12.jpg](https://wiki.elecrow.com/images/thumb/b/b4/Microwave_sensor12.jpg/400px-Microwave_sensor12.jpg){ loading=lazy }

2.Upload the below program.

```
#include <MsTimer2.h>           //Timer interrupt function library
int pbIn = 0;                    // Define interrupt 0 that is digital pin 2
int ledOut = 12;                 // Define the indicator LED pin digital pin 13
int number=0;                    //Interrupt times
volatile int state = LOW;         // Defines the indicator LED state, the default is not bright
  
void setup()
{      
     Serial.begin(9600);          
     pinMode(ledOut, OUTPUT);// 
     attachInterrupt(pbIn, stateChange, FALLING); // Set the interrupt function, interrupt pin is digital pin D2, interrupt service function is stateChange (), when the D2 power change from high to low , the trigger interrupt.
     MsTimer2::set(1000, Handle); // Set the timer interrupt function, running once Handle() function per 1000ms 
     MsTimer2::start();//Start timer interrupt function
 
}
  
void loop()                     
{
Serial.println(number); // Printing the number of times of interruption, which is convenient for debugging.
    delay(1);        
    if(state == HIGH)  //When a moving object is detected, the ledout is automatically closed after the light 2S, the next trigger can be carried out, and No need to reset. Convenient debugging.
    {
        delay(2000);
        state = LOW;
        digitalWrite(ledOut, state);    //turn off led
    }
 
 }
 
  
void stateChange()  //Interrupt service function
{  
  number++;  //Interrupted once, the number +1
 
}
 
void Handle()   //Timer service function
{
    if(number>1)  //If in the set of the interrupt time the number more than 1 times, then means have detect moving objects,This value can be adjusted according to the actual situation, which is equivalent to adjust the threshold of detection speed of moving objects.
         {
                   state = HIGH;            
                   digitalWrite(ledOut, state);    //light led
                   number=0;   //Cleare the number, so that it does not affect the next trigger
         }
        else
              number=0;   //If in the setting of the interrupt time, the number of the interrupt is not reached the threshold value, it is not detected the moving objects, Cleare the number.
}
```

3.The microwave sensor has a distance range of 2-16m. The detection distance can be adjusted using the potentiometer. If it is turned in the direction on MIN, the detection distance decreases. If it is turned in the opposite direction, the range increases.

## Resources
---------

- [MsTimer2 ](http://www.elecrow.com/wiki/images/1/1d/MsTimer2.zip)
- [Microwave sensor - EAGLE (Schematic and Board) files](./files/Crotail-Microwave-sensor-zip.md)
- [Doppler\_effect ](https://en.wikipedia.org/wiki/Doppler_effect)