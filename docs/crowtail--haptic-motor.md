---
title: Crowtail- Rotation Angle Sensor
---

## Introduction
------------

The Crowtail-haptail Motor is using little DRV2605 motor driver form TI. Its designed specifically for controlling haptic motors - buzzers and vibration motors. Normally one would just turn those kinds of motors on and off, but this driver has the ability to have various effects when driving a vibe motor. For example, ramping the vibration level up and down, 'click' effects, different buzzer levels, or even having the vibration follow a musical/audio input.

**Mode: [CRT00349H](https://www.elecrow.com/crowtail-haptic-motor.html)**

![Crowtail- Haptic Motor.jpg](https://wiki.elecrow.com/images/thumb/c/ce/Crowtail-_Haptic_Motor.jpg/500px-Crowtail-_Haptic_Motor.jpg){ loading=lazy }

## Features
--------

- Specifically for controlling haptic motors- buzzers and vibration motors

- Follow a musical/audio input

- Support LRA (Linear Resonance Actuator) and ERM (Eccentric Rotating Mass)

- Works with both 3V and 5V power/logic

## Specification
-------------

- Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

- Crowtail IIC interface

- motor : round or flatte 10\*2.7MM

- using little vibration pancake ERM

## **Uager**
---------

We have set the pin to IIC interface and have a library for you to use, so it's usage pretty simple.

1.Hardware Connection

Connect the Crowtail- Haptic Motor to IIC port of the Crowtail - Basic Shield using a 4 pin cable .Then connect Arduino to PC by using a USB cable.

![Hallcdsgdgs.jpg](https://wiki.elecrow.com/images/thumb/7/7c/Hallcdsgdgs.jpg/600px-Hallcdsgdgs.jpg){ loading=lazy }


2.Softwart Connection

Download [DRV2605 library](./files/DRV2605-zip.md) for Arduino boards; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;


Upload it into your Arduino board and observe the vibration of the motor.

```


#include <Wire.h>
#include "DRV2605.h"

DRV2605 drv;

void setup() {
  Serial.begin(9600);
  Serial.println("DRV test");
  drv.begin();
  
  drv.selectLibrary(1);
  
  // I2C trigger by sending 'go' command 
  // default, internal trigger when sending GO command
  drv.setMode(DRV2605_MODE_INTTRIG); 
}

uint8_t effect = 1;

void loop() {
  Serial.print("Effect #"); Serial.println(effect);

  // set the effect to play
  drv.setWaveform(0, effect);  // play effect 
  drv.setWaveform(1, 0);       // end waveform

  // play the effect!
  drv.go();

  // wait a bit
  delay(500);

  effect++;
  if (effect > 117) effect = 1;
}

```