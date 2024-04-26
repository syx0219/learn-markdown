---
title: Crowtail- I2C Motor Driver
---

## Description
-----------

This Crowtail- I2C motor driver included two DRV8830, The DRV8830 provides an integrated motor driver solution for battery-powered toys, printers, and other low-voltage or battery-powered motion control applications. The module has two H-bridge drivers, and can drive two DC motors or two winding of stepper motors, as well as other loads like solenoids.It requires an onboard 5V voltage regulator which can power the I2C bus. All driver lines are diode protected from back EMF.It features two LEDs for fault indicator and four LEDs to indicate which direction each motor is running. CROWTAIL system plug and I2C interface enables you to daisy-chain the driver with many other devices.

**Model: [CT009280D](https://www.elecrow.com/crowtail-i2c-motor-driver.html)**

![Crowtail- I2C Motor Driver.jpg](https://wiki.elecrow.com/images/thumb/4/4f/Crowtail-_I2C_Motor_Driver.jpg/600px-Crowtail-_I2C_Motor_Driver.jpg){ loading=lazy }

## Features
--------

- Without external power supply
- Two leds for fault indicator
- Default maximum drive current 200 mA
- Crowtail compatible
- I2C interface
- Motor's speed and direction can control
- Number of channels: 2
- Easy to use

## Application Ideas
-----------------

This motor driver can be used to drive any brushed electronic motor as long as it doesn't consume more than 1A at 5v. Two motors can be driven simultaneously while set to a different speed and direction. The speed can be set fully proportional and is controlled by I2C command.

- Battery-Powered:

```
  *Printers
  *Toys
  *Robotics
  *Cameras
  *Phone
```

- Small Actuators, Pumps, etc.

## Specifications
--------------

Dimensions(mm):50.0(L)x35.1(W)x11.8(H)

| Item | Min | Typical | Max | Unit |
|---|---|---|---|---|
| Working Voltage | 2.75 | 5 | 6.8 | VDC |
| Max Output Current per channel | 0.2(default) | - | 1 | A |
| Input/output voltage on I2C bus | 3.3/5 | 3.3/5 | 3.3/5 | V |
| Communication protocol | I2C | I2C | I2C | / |
| Default I2C Address | 0xC0, 0xC4 | 0xC0, 0xC4 | 0xC0, 0xC4 | / |

## Interface Function
------------------

![I2C motor driver0121.jpg](https://wiki.elecrow.com/images/thumb/9/92/I2C_motor_driver0121.jpg/600px-I2C_motor_driver0121.jpg){ loading=lazy }

- Crowtail Interface -Crowtail products have a eco system and all have a same connector which can plug onto the Base Shield. Connect this module to the I2C port of Base Shield, and then it can work well with Arduino. However, you can also connect Crowtail- I2C Motor Driver to Arduino without Base Shield by jumper wires.

- CH1 fault indicator - Channel 1 fault indicator.
- CH2 fault indicator - Channel 2 fault indicator.
- Direction indicator - Motor direction indicator
- CH1 Output Connector - Motor 1 connector.
- CH2 Output Connector - Motor 2 connector.

## Hardware function
-----------------

### **Change Default maximum drive current**

The default maximum drive current of each channel is 200mA, see the front picture of the board  
![I2C motor driver1013.jpg](https://wiki.elecrow.com/images/thumb/c/c6/I2C_motor_driver1013.jpg/400px-I2C_motor_driver1013.jpg){ loading=lazy }  
Each channel (CH1,CH2) has been added a resistor, and each value of resistor (R5,R12) is 1 Ω, so the maximum drive current is 200mA according to the following equation   
![I2C motor 7.png](https://wiki.elecrow.com/images/2/21/I2C_motor_7.png){ loading=lazy }  
Meantime, each channel provides a reserved solderable pad (R6 for CH1, R13 for CH2), so you can solder a resistor onto the board to change the resistor value of each channel. Following is the new equation if adding resistor to the board  
![I2C motor 8.png](https://wiki.elecrow.com/images/thumb/4/4b/I2C_motor_8.png/400px-I2C_motor_8.png){ loading=lazy } 
![I2C motor 9.png](https://wiki.elecrow.com/images/thumb/1/1c/I2C_motor_9.png/400px-I2C_motor_9.png){ loading=lazy }

Caution:

- Maximum working current of each channel must be less than 1A. So the minimum value of resistor soldered to the reserved pad should not less than 0.2 Ω.

### **Change Default I2C Address**

The I2C address of each channel is changeable.You can find there's 4 jumper pin, A0\_CH1 and A1\_CH1 are for channel 1, A0\_CH2 and A1\_CH2 are for channel 2. As shown below:  
![I2C motor11022.jpg](https://wiki.elecrow.com/images/thumb/b/b6/I2C_motor11022.jpg/400px-I2C_motor11022.jpg){ loading=lazy }  
You can Connect each jumper with jump hats to change the I2C address:  
![I2C motor 10.png](https://wiki.elecrow.com/images/thumb/8/8f/I2C_motor_10.png/600px-I2C_motor_10.png){ loading=lazy }  
 Note1: The library of Crowtail- I2C Motor driver is depended on the default address.  

## Usage
-----

Now, Let's begin to use the Crowtail- I2C Motor Driver.

1.Preparations
Now we are making a demo for Crowtail- I2C Motor Driver v1.0 which require following modules.

- 2 \* DC Motor 2V-6V
- Crowduino Board

2.Hardware Installation
Crowtail- I2C Motor Driver got one Crowtail socket for connecting two modules above.

They are:

- 2\* DC Motor 2V-6V - connnect to CH1 &amp; CH2 Output connecter.
- Crowduino Board - connect Crowduino's Crowtail I2C Interface to Mini Motor Driver's Crowtail Interface.

As shown below:  
![201605311654341.jpg](https://wiki.elecrow.com/images/thumb/4/4f/201605311654341.jpg/600px-201605311654341.jpg){ loading=lazy }

3.Software Work

The Crowtail- I2C Motor Driver can control motor which is based on the chip DRV8830. The DRV8830 is not just a dual motor driver, it is a dual H-bridge. An h-bridge is basically a specific setup of transistors that allow you to switch direction of current. You can use your Arduino to make them spin at any speed. Because the module has 2 H-bridges, you can not only make a robot go forwards and backwards, but also turn around by having each wheel spin in a different direction.  
Connect Seeeduino to computer use a micro USB cable.   
Now, let's use the Crowtail- I2C Motor Driver to control two DC motors rotating in the positive or opposite direction.  
The below is an example program to be used with an Arduino. The code for this is very basic, but you can also change it up and do it your own way.

```
#include <SparkFunMiniMoto.h>  // Include the MiniMoto library

// Create two MiniMoto instances, with different address settings.
MiniMoto motor0(0xC4); // A1 = 1, A0 = clear
MiniMoto motor1(0xC0); // A1 = 1, A0 = 1 (default)

#define FAULTn  16     // Pin used for fault detection.

// Nothing terribly special in the setup() function- prep the
//  serial port, print a little greeting, and set up our fault
//  pin as an input.
void setup()
{
  Serial.begin(9600);
  Serial.println("Hello, world!");
  pinMode(FAULTn, INPUT);
}

// The loop() function just spins the motors one way, then the
//  other, while constantly monitoring for any fault conditions
//  to occur. If a fault does occur, it will be reported over
//  the serial port, and then operation continues.
void loop()
{
  Serial.println("Forward!");
  motor0.drive(100);
  motor1.drive(100);
  delayUntil(1000);
  Serial.println("Stop!");
  motor0.stop();
  motor1.stop();
  delay(1000);
  Serial.println("Reverse!");
  motor0.drive(-100);
  motor1.drive(-100);
  delayUntil(1000);
  Serial.println("Brake!");
  motor0.brake();
  motor1.brake();
  delay(1000);
}

// delayUntil() is a little function to run the motor either for
//  a designated time OR until a fault occurs. Note that this is
//  a very simple demonstration; ideally, an interrupt would be
//  used to service faults rather than blocking the application
//  during motion and polling for faults.
void delayUntil(unsigned long elapsedTime)
{
  // See the "BlinkWithoutDelay" example for more details on how
  //  and why this loop works the way it does.
  unsigned long startTime = millis();
  while (startTime + elapsedTime > millis())
  {
    // If FAULTn goes low, a fault condition *may* exist. To be
    //  sure, we'll need to check the FAULT bit.
    if (digitalRead(FAULTn) == LOW)
    {
      // We're going to check both motors; the logic is the same
      //  for each...
      byte result = motor0.getFault();
      // If result masked by FAULT is non-zero, we've got a fault
      //  condition, and we should report it.
      if (result & FAULT)
      {
        Serial.print("Motor 0 fault: ");
        if (result & OCP) Serial.println("Chip overcurrent!");
        if (result & ILIMIT) Serial.println("Load current limit!");
        if (result & UVLO) Serial.println("Undervoltage!");
        if (result & OTS) Serial.println("Over temp!");
        break; // We want to break out of the motion immediately,
               //  so we can stop motion in response to our fault.
      }
      result = motor1.getFault();
      if (result & FAULT)
      {
        Serial.print("Motor 1 fault: ");
        if (result & OCP) Serial.println("Chip overcurrent!");
        if (result & ILIMIT) Serial.println("Load current limit!");
        if (result & UVLO) Serial.println("Undervoltage!");
        if (result & OTS) Serial.println("Over temp!");
        break;
      }
    }
  }
}
```

After upload completed, the motors will rotating in the positive or opposite direction in cycle.

## Resources
---------

- [DRV8830 Datasheet](../../files/DRV8830-pdf.md)
- [Crowtail- I2C Motor Driver eagle file](../../files/Crowtail-I2C-Motor-Driver-eagle-file-zip.md)
- [Crowtail- I2C Motor Driver Source Library](../../files/Crowtail-I2C-Motor-Driver-Source-Library-zip.md)