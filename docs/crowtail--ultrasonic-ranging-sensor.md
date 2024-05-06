---
title: Crowtail- Ultrasonic Ranging Sensor
---

## Introduction
------------

Description: This HC-SR04 has stable performance and high ranging accuracy. Compared to the Shap IR ranging module , HC-SR04 is more cheaper than it . But it has the same ranging accuracy and longer ranging distance. So we choose it to become “a family number of our Crowtail”, wish more good experience.  
**Model: [CT0051URS](https://www.elecrow.com/crowtail-ultrasonic-ranging-sensor.html)**

![17777.jpg](https://wiki.elecrow.com/images/thumb/c/ca/17777.jpg/400px-17777.jpg){ loading=lazy }

## Features
--------

- Power supply: 5V DC.
- Effectual angle: &lt;15°.
- Ranging distance: 2cm – 500 cm.
- Resolution: 1 cm.
- Ultrasonic Frequency: 40k Hz.
- Dimensions(mm):45.6(L)x34.7(W)x22.0(H)

## Usage
-----

![Ultrasonic10.jpg](https://wiki.elecrow.com/images/9/97/Ultrasonic10.jpg){ loading=lazy }
![Ultrasonic11.png](https://wiki.elecrow.com/images/7/72/Ultrasonic11.png){ loading=lazy }  
A short ultrasonic pulse is transmitted at the time 0, reflected by an object. The senor receives this signal and converts it to an electric signal. The next pulse can be transmitted when the echo is faded away. This time period is called cycle period. The recommend cycle period should be no less than 50ms. If a 10μs width trigger pulse is sent to the signal pin, the Ultrasonic module will output eight 40kHz ultrasonic signal and detect the echo back. The measured distance is proportional to the echo pulse width and can be calculated by the formula above. If no obstacle is detected, the output pin will give a 38ms high level signal.

### **Hardware**

Connect the Crowtail- Ultrasonic Ranging Sensor to the Crowtail base board as below:
![Crowtail- Ultrasonic Ranging Sensor11.jpg](https://wiki.elecrow.com/images/thumb/9/95/Crowtail-_Ultrasonic_Ranging_Sensor11.jpg/600px-Crowtail-_Ultrasonic_Ranging_Sensor11.jpg){ loading=lazy }

### **Programming**

Copy the following program to Arduino IDE and upload to your Arduino/Crowduino, you can also download the example in the [Resource](./triple-axis-magnetometer-breakout.md#resource).

```
#include "Ultrasonic.h"

Ultrasonic ultrasonic(12,13);
void setup() {
Serial.begin(9600);
}

void loop()
{
Serial.println(ultrasonic.Ranging(CM));
delay(100);
}
```

Open the Sscom32 terminal or the Serial moniter , and set the baudrate to 9600, you will see the output changing with the object distance. 
![Ultrasonic sensor result.jpg](https://wiki.elecrow.com/images/6/67/Ultrasonic_sensor_result.jpg){ loading=lazy }

### Resource

[File:Ultrosonic ranger module Library and demo code for arduino 10.zip](./files/Ultrosonic-ranger-module-Library-and-demo-code-for-arduino-10-zip.md "File:Ultrosonic ranger module Library and demo code for arduino 10.zip")