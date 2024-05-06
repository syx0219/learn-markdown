---
title: Crowtail- MAX30105 Particle Sensor
---

## **Description**
---------------

The MAX30105 is an integrated particle-sensing module. It includes internal LEDs, photodetectors, optical elements, and low-noise electronics with ambient light rejection. The MAX30105 provides a complete system solution to ease the design-in process of smoke detection applications including fire alarms. The MAX30105 is designed to operate at 5V and can communicate with both 3.3V and 5V microcontrollers.

**Model:** [CRT00226P](https://www.elecrow.com/crowtail-max30105-particle-sensor.html)

![Crowtail- MAX30105 Particle Sensor.jpg](https://wiki.elecrow.com/images/thumb/1/10/Crowtail-_MAX30105_Particle_Sensor.jpg/500px-Crowtail-_MAX30105_Particle_Sensor.jpg){ loading=lazy }

## **Features**
------------

Built-in Red, IR, and Green LEDs

5V operation

Onboard 1.8V regulation and I2C interface circuitry

Sensitivity configurable down to 7.81pA

3200Hz maximum sample rate

Built-in 32 sample FIFO (First In, First Out

Dimensions(mm):20.0(L)x20.0(W)x11.8(H)

## **Application**
---------------

Presence detection, distance sensing (18" max), pulse oximetry, blood oxygen saturation level (SpO2), smoke and particle detection

## **Usage**
---------

This demo will show you when When the sensor detects the object, the serial monitor will print "Something is there!".

**Hardwire connection**

The Crowtail- MAX30105 Particle Sensor is connecting to IIC port of Crowtail - Base Shield.

![Exampdgs.jpg](https://wiki.elecrow.com/images/thumb/e/ee/Exampdgs.jpg/600px-Exampdgs.jpg){ loading=lazy }

Download "[MAX3010x\_Sensor\_Library](https://wiki.elecrow.com/images/3/38/MAX3010x_Sensor_Library.zip)" for arduino boards, unzip and put it in the libraries of Arduino IDE by the path : ..\\arduino-1.x.x\\libraries;

```


#include <Wire.h>
#include "MAX30105.h"

MAX30105 particleSensor;

long samplesTaken = 0; //Counter for calculating the Hz or read rate
long unblockedValue; //Average IR at power up
long startTime; //Used to calculate measurement rate

void setup()
{
  Serial.begin(115200);
  Serial.println("Initializing...");

  // Initialize sensor
  if (!particleSensor.begin(Wire, I2C_SPEED_FAST)) //Use default I2C port, 400kHz speed
  {
    Serial.println("MAX30105 was not found. Please check wiring/power. ");
    while (1);
  }

  //Setup to sense up to 18 inches, max LED brightness
  byte ledBrightness = 0xFF; //Options: 0=Off to 255=50mA
  byte sampleAverage = 4; //Options: 1, 2, 4, 8, 16, 32
  byte ledMode = 2; //Options: 1 = Red only, 2 = Red + IR, 3 = Red + IR + Green
  byte sampleRate = 400; //Options: 50, 100, 200, 400, 800, 1000, 1600, 3200
  int pulseWidth = 411; //Options: 69, 118, 215, 411
  int adcRange = 2048; //Options: 2048, 4096, 8192, 16384

  particleSensor.setup(ledBrightness, sampleAverage, ledMode, sampleRate, pulseWidth, adcRange); //Configure sensor with these settings

  particleSensor.setPulseAmplitudeRed(0); //Turn off Red LED
  particleSensor.setPulseAmplitudeGreen(0); //Turn off Green LED

  //Take an average of IR readings at power up
  unblockedValue = 0;
  for (byte x = 0 ; x < 32 ; x++)
  {
    unblockedValue += particleSensor.getIR(); //Read the IR value
  }
  unblockedValue /= 32;

  startTime = millis();
}

void loop()
{
  samplesTaken++;

  Serial.print("IR[");
  Serial.print(particleSensor.getIR());
  Serial.print("] Hz[");
  Serial.print((float)samplesTaken / ((millis() - startTime) / 1000.0), 2);
  Serial.print("]");

  long currentDelta = particleSensor.getIR() - unblockedValue;

  Serial.print(" delta[");
  Serial.print(currentDelta);
  Serial.print("]");

  if (currentDelta > (long)100)
  {
    Serial.print(" Something is there!");
  }

  Serial.println();
}

```

Cope the code and upload it into your arduino board, open the Serial Monitor, if the sensor detects a significant change from the average, it will print "Something is there!".

![Examsgsple.png](https://wiki.elecrow.com/images/8/84/Examsgsple.png){ loading=lazy }