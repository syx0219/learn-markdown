---
title: Ultrasonic Ranging Sensor Module
---

## Introduction
------------

Description: This HC-SR04 Ultrasonic Ranging Sensor is a non-contact distance measurement module with stable performance and high ranging accuracy. with the inexpensive price, The measurment range if it can be upto 5M, which would be helpful for your project such as robotic Obstacle Avoidance and so on.   
**Model: [SOD00201S](https://www.elecrow.com/hcsr04-ultrasonic-ranging-sensor-p-316.html)**

![Ultrosonic11.jpg](https://wiki.elecrow.com/images/thumb/7/74/Ultrosonic11.jpg/400px-Ultrosonic11.jpg){ loading=lazy }
![Ultrosonic21.jpg](https://wiki.elecrow.com/images/thumb/a/a3/Ultrosonic21.jpg/400px-Ultrosonic21.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/hcsr04-ultrasonic-ranging-sensor-p-316.html?wiki "Title text")

## Features
--------

- Power supply: 5V DC.
- Effectual angle: &lt;15°.
- Ranging distance: 25cm – 500 cm.
- Resolution: 1 cm.
- Ultrasonic Frequency: 40k Hz.

## Usage
-----

![Ultrasonic10.jpg](https://wiki.elecrow.com/images/9/97/Ultrasonic10.jpg){ loading=lazy }
![Ultrasonic11.png](https://wiki.elecrow.com/images/7/72/Ultrasonic11.png){ loading=lazy }     
A short ultrasonic pulse is transmitted at the time 0, reflected by an object. The senor receives this signal and converts it to an electric signal. The next pulse can be transmitted when the echo is faded away. This time period is called cycle period. The recommend cycle period should be no less than 50ms. If a 10μs width trigger pulse is sent to the signal pin, the Ultrasonic module will output eight 40kHz ultrasonic signal and detect the echo back. The measured distance is proportional to the echo pulse width and can be calculated by the formula above. If no obstacle is detected, the output pin will give a 38ms high level signal.

### **Hardware**

Connect this triple axis magnetometer breadkout module to your Arduino/Crowduino I2C wires(SDA:A4, D18;SCL:A5, D19)as below:  
![Ultrosonic hard.jpg](https://wiki.elecrow.com/images/f/ff/Ultrosonic_hard.jpg){ loading=lazy }

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

### **Resource**

[File:Ultrosonic ranger module Library and demo code for arduino 10.zip](https://wiki.elecrow.com/images/0/0a/Ultrosonic_ranger_module_Library_and_demo_code_for_arduino_10.zip "File:Ultrosonic ranger module Library and demo code for arduino 10.zip")