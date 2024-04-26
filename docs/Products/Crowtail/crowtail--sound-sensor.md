---
title: Crowtail- Sound Sensor
---

## Description
-----------

Crowtail- Sound Sensor can detect the sound loudness of the environment. The main component of the module is a simple microphone to receive the sound signal, with band pass filter and a LMV358 amplifier to make the output signal easy to be received by microprocessor. This module outputs analog signal that shows the relative loudness. Besides, an on-board potentiometer can be used to adjust output voltage.

**Model: [CT0021SS](http://www.elecrow.com/crowtail-sound-sensor-p-1273.html)**

![Crowtail- Sound Sensor.JPG](https://wiki.elecrow.com/images/thumb/3/3d/Crowtail-_Sound_Sensor.JPG/600px-Crowtail-_Sound_Sensor.JPG)](#file)

## Features
--------

- Easy to use sound sensor module
- Provides analog output signal

## Specifications
--------------

- Operating voltage : 5V
- Operating current (Vcc=5V): 4-8mA
- Dimensions(mm):20.0(L)x20.0(W)x9.4(H)

## Usage
-----

Turning on a LED by Sound (Sound Sensor)

This example program shows how to use the sound sensor (microphone. When the incoming sound amplitude exceeds a threshold, we will turn an LED on for 1 second.

1.When using the module in conjunction with an Arduino or a Crowduino, use the Crowtail - Base Shield and connect the Crowtail - Sound Sensor module to the shield using a designated Crowdtail Interface. Also attach an output module such as a Crowtail - LED which will get triggered based on input received from the sound sensor (shown below).

![Crowtail- Sound Senso.JPG](https://wiki.elecrow.com/images/thumb/c/c9/Crowtail-_Sound_Senso.JPG/400px-Crowtail-_Sound_Senso.JPG){ loading=lazy }

2.Upload the following sample sketch to make the LED turn ON and OFF based on input from the sound sensor:

```
/*
   Sound Sensor
   A simple program demonstrate sound sensor senses a sound that is up to the threshold you set 
   in the code, the LED is on for 1s.
*/ 
const int SOUND_SENSOR=A0 ;         /* sound sensor pin */          
const int  LED=5;          /* LED pin D5*/
#define THRESHOLD_VALUE    300        
#define ON                 HIGH                    /* led on */
#define OFF                LOW                     /* led off */
#define handle_led(x)     digitalWrite(LED, x)    /* handle led */
/* Global Variables */
int sound_value = 0;
void setup() { 
  /* Initialize led pin */
  pinMode(LED, OUTPUT);  
  digitalWrite(LED, LOW);
} 
void loop() {  
 /* read the sound value */
  sound_value = analogRead(SOUND_SENSOR);         
  /* if the value is larger than threshold, turn on led */
  if(sound_value > THRESHOLD_VALUE) {
      handle_led(ON); 
      delay(1000);
  }
  handle_led(OFF);
}
```

3.Make a noice and you will see the LED lights up.
![Sound Sensor result1.jpg](https://wiki.elecrow.com/images/thumb/c/c5/Sound_Sensor_result1.jpg/500px-Sound_Sensor_result1.jpg){ loading=lazy }

## Resource
--------

- [Sound Sensor Program](../../files/Sound-controlled-led-zip.md)
- [Crowtail- Sound Sensor eagle files](../../files/Crowtail-Sound-Sensor-v1.0-eagle-files-zip.md)
- [Crowtail-\_Sound\_Sensor\_v2.0.zip](../../files/Crowtail-Sound-Sensor-v2.0-zip.md)