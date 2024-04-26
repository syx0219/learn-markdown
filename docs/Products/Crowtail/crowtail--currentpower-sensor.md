---
title: Crowtail- CurrentPower Sensor
---

## Introduction
------------

The Crowtail- CurrentPower Sensor will solve all your power-monitoring problems. Instead of struggling with two multimeters, you can use this breakout to measure both the high side voltage and DC current draw over I2C with 1% precision.It is use the INA219B chip that much smarter - it can handle high side current measuring, up to +26VDC, even though it is powered with 3 or 5V. It will also report back that high side voltage, which is great for tracking battery life or solar panels.

**Model: [CRT00455C](https://www.elecrow.com/crowtail-current-power-sensor.html)**

![Crowtail- CurrentPower Sensor.jpg](https://wiki.elecrow.com/images/thumb/e/e9/Crowtail-_CurrentPower_Sensor.jpg/500px-Crowtail-_CurrentPower_Sensor.jpg){ loading=lazy }

## **Features**
------------

Measuring up to +26VDC

Simultaneously measure current and voltage

Chip:INA219BIDCNT

Corwtail IIC interface

IIC address: 0x40

Dimensions(mm):40.0(L)x20.0(W)x12.0(H)

## Usage
-----

This demo is going to show you how to measure the voltage and current when the DC motor working. Here we use Crowtail as a load and measure it's voltage and current.

**1.Software Installation**

Download "[INA219.zip](../../files/INA219.zip.md)" for arduino boards, unzip and put it in the libraries of Arduino IDE by the path : ..\\arduino-1.x.x\\libraries;

Cope this code and upload it into your arduino board.

```


#include <Wire.h>
#include <Adafruit_INA219.h>

Adafruit_INA219 ina219;

void setup(void) 
{
  Serial.begin(115200);
  while (!Serial) {
      // will pause Zero, Leonardo, etc until serial console opens
      delay(1);
  }

  uint32_t currentFrequency;
    
  Serial.println("Hello!");
  
  // Initialize the INA219.
  // By default the initialization will use the largest range (32V, 2A).  However
  // you can call a setCalibration function to change this range (see comments).
  ina219.begin();
  // To use a slightly lower 32V, 1A range (higher precision on amps):
  //ina219.setCalibration_32V_1A();
  // Or to use a lower 16V, 400mA range (higher precision on volts and amps):
  //ina219.setCalibration_16V_400mA();

  Serial.println("Measuring voltage and current with INA219 ...");
}

void loop(void) 
{
  float shuntvoltage = 0;
  float busvoltage = 0;
  float current_mA = 0;
  float loadvoltage = 0;

  shuntvoltage = ina219.getShuntVoltage_mV();
  busvoltage = ina219.getBusVoltage_V();
  current_mA = ina219.getCurrent_mA();
  loadvoltage = busvoltage + (shuntvoltage / 1000);
  
  Serial.print("Bus Voltage:   "); Serial.print(busvoltage); Serial.println(" V");
  Serial.print("Shunt Voltage: "); Serial.print(shuntvoltage); Serial.println(" mV");
  Serial.print("Load Voltage:  "); Serial.print(loadvoltage); Serial.println(" V");
  Serial.print("Current:       "); Serial.print(current_mA); Serial.println(" mA");
  Serial.println("");

  delay(2000);
}

```

**2.Hardware Installation**


CurrentPower Sensor ----- Crowduino1 ---- Crowduino2

IIC pin ----------------- IIC port

Intput"+" ----------------- 5V

Output"-" ------------------------------------- 5V

Null -------------------- GND ---------------- GND

![Exagdsagmdgdple1.jpg](https://wiki.elecrow.com/images/thumb/d/db/Exagdsagmdgdple1.jpg/600px-Exagdsagmdgdple1.jpg){ loading=lazy }

Open the serial monitor and then observe the information.

![Exadgdgggmple.png](https://wiki.elecrow.com/images/3/35/Exadgdgggmple.png){ loading=lazy }