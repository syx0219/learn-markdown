---
title: Encoder Gear Motor-25MM 95RPM
---

## Description
-----------

This is a gear motor that has an encoder to help users adjust the speed. The gear motor has a large torque, low loudness and easy to use. Besides, the encoder on this module has two outputs: output\_A and output\_B, to monitor the motor speed and direction of rotation, so that you can monitor the speed and then to adjust it in a closed-loop control.  
The encoder output 2 signals with 90 degree phase difference. There will be 334 pulses on each of the signal for a round of the motor, with the rising &amp; falling edge, you can get 334x2x2=1336 signals for a round of the motor, with a interval of 360/1336=0.2694 degree.  
**Model:[AM2595EC](http://www.elecrow.com/encoder-gear-motor25mm-95rpm-p-752.html)**

![Encoder Gear Motor-25MM 95RPM.jpg](https://wiki.elecrow.com/images/thumb/0/0e/Encoder_Gear_Motor-25MM_95RPM.jpg/400px-Encoder_Gear_Motor-25MM_95RPM.jpg){ loading=lazy }

## Specification
-------------

- Working Voltage for Motor: 6~24 VDC
- Rated Voltage for Motor: 12 VDC
- Voltage for Encoder: 5 VDC
- Motor Speed: 95 rpm@12V
- Torque: 1.1 kg.cm
- Motor Length: 65 mm
- Motor diameter: 25 mm
- Current: 250 mA
- Motor Power: 1.25W
- Weight: 86 g

## Application Ideas
-----------------

- High precision non-contact temperature measurements
- Thermal Comfort sensor for Mobile AirConditioning control system
- Temperature sensing element for residential,commercial and industrial building airconditioning
- Windshield defogging
- Automotive blind angle detection
- Industrial temperature control of moving parts
- Temperature control in printers and copiers
- Home appliances with temperature control
- Healthcare
- Livestock monitoring
- Movement detection
- Multiple zone temperature control – up to 127sensors can be read via common 2 wires
- Thermal relay / alert
- Body temperature measurement

## Usage
-----

### **Hardware Installation**

![Encoder Gear Motor-25MM 95RPM hardware.jpg](https://wiki.elecrow.com/images/5/53/Encoder_Gear_Motor-25MM_95RPM_hardware.jpg){ loading=lazy } 
![Encoder Gear Motor-25MM 95RPM hardware2.jpg](https://wiki.elecrow.com/images/thumb/d/dc/Encoder_Gear_Motor-25MM_95RPM_hardware2.jpg/800px-Encoder_Gear_Motor-25MM_95RPM_hardware2.jpg){ loading=lazy }

### **Demo c0de**

1.Download the library File:[Encoder Gear Motor Library](https://wiki.elecrow.com/images/9/9a/Encoder_Gear_Motor.zip)

2.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries.

3.Open the code directly by the path:File -&gt; Examples -&gt;MsTimer2 -&gt;Encoder\_Gear\_Motor.

```
#include <MsTimer2.h> 
#define ENCODER_A_PIN 2
long position;
long speed=0;
void setup(){
  MsTimer2::set(1000, flash);       
  MsTimer2::start();   
  pinMode(ENCODER_A_PIN, INPUT);
  attachInterrupt(0, read_quadrature, CHANGE);
  Serial.begin(9600);
}

void loop(){
   Serial.print("speed: ");
   Serial.print(speed/334, DEC);
   Serial.println("rmp");
   delay(1000);
}

void read_quadrature(){  
 
  if (digitalRead(ENCODER_A_PIN) == LOW){   
      position++;
  }
}
void flash()                      
{                        
     speed=position;
     position=0;     
}
```

4.Open the monitor of Arduino IDE, you can see the speed of the motor.  
![Encoder Gear Motor-25MM 95RPM test resullt.JPG](https://wiki.elecrow.com/images/a/a1/Encoder_Gear_Motor-25MM_95RPM_test_resullt.JPG){ loading=lazy }

## Resources
---------

- [Encoder Gear Motor Library](https://wiki.elecrow.com/images/9/9a/Encoder_Gear_Motor.zip)