---
title: Crowtail-Digital-Programmable-Potentiometer
---

## Description
-----------

In a variety of bridge circuits, due to vibration, shock and temperature and humidity and other environmental factors, the potentiometer position and parameters will always change, so our common potentiometer always need to constantly adjust, these to use Brought a lot of inconvenient place. So we designed this product, a Crowtail- Digital Programmable Potentiometer, which not only eliminates the need for constant adjustment, but also improves the accuracy of the entire system, in addition to our unique crowtail interface and arduino with it when used More convenient, it uses the potentiometer is X9C103S - a 100-order digital potentiometer, the resistance range from 40R to 100K, in its internal contains 99 resistance array, a temperature compensation function, and resistance resolution up to 1%.

**Model: [CRT02106P](https://www.elecrow.com/crowtail-digital-programmable-potentiometer.html)**  
![Crowtail-digital programmable potentiometer 3.jpg](https://wiki.elecrow.com/images/thumb/e/e3/Crowtail-digital_programmable_potentiometer_3.jpg/400px-Crowtail-digital_programmable_potentiometer_3.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-digital-programmable-potentiometer.html?wiki "Title text")

## Features
--------

- Crowtail interface
- Temperature compensation
- Digital and Programmable
- High resistance resolution
- No manual adjustment

## Specifications
--------------

| **Item** | **Value** |
|---|---|
| Operating voltage | 5V |
| Total resistance | 100kΩ |
| Terminal voltage | -5V ~ 5V |
| Resistance increase mode | linear |
| Interface | Crowtail |
| Operating current | 3mA |
| Temperature | -40℃ ~ 85℃ |
| Resistance resolution | 1% |
| Resistance range | 40R-100K |
| Dimensions | 28.5mm(L)x20.0mm(W)x9.8mm(H) |

## Pin Map
-------

![PINMAP.png](https://wiki.elecrow.com/images/thumb/7/74/PINMAP.png/500px-PINMAP.png){ loading=lazy }

| **Pin Name** | **Description** |
|---|---|
| U\_D | Up/Down Input |
| INC | Increment Input |
| VCC | Supply Voltage |
| GND | GND |
| VH | High Terminal |
| VW | Wiper Terminal |
| VL | VL Low Terminal |

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### Hardware

STEP1 Prepare the below stuffs:  

| **Crowduino Uno**                                            | **Base Shield**                                              | **Crowtail-digital programmable potentiometer**                            |
| :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg){ loading=lazy } | ![Crowtail-base shield 2.jpg](https://wiki.elecrow.com/images/thumb/c/cb/Crowtail-base_shield_2.jpg/200px-Crowtail-base_shield_2.jpg){ loading=lazy } | ![Crowtail-digital programmable potentiometer 3.jpg](https://wiki.elecrow.com/images/thumb/e/e3/Crowtail-digital_programmable_potentiometer_3.jpg/300px-Crowtail-digital_programmable_potentiometer_3.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/crowtail-base-shield-p-1264.html) | [**Get one now**](https://www.elecrow.com/crowtail-digital-programmable-potentiometer.html) |

STEP2 Plug Crowtail-Base Shield into Crowduino Uno;  
STEP3 Plug Crowtail-Digital Programmable Potentiometer-V2.0 into D2&amp;D3 port on the Crowtail-Base Shield U Port;  
STEP4 Connect VH on the Crowtail-Digital Programmable Potentiometer V2.0 to the 5V power supply on the Crowduino Uno with the dupont cable;  
STEP5 Connect VL on the crowtail-digital Programmable Potentiometer-V2.0 to the GND on the Crowduino Uno with the dupont cable;  
STEP6 Connect Crowduino Uno to PC via a Mini USB cable. 

| ==**NOTE**==                                                    |
| ------------------------------------------------------------ |
| ==If we don't have Crowtail Base Shield, We also can directly connect this module to Crowduino Uno as below.== | 

| **Crowduino Uno** | **Digital Programmable Potentiometer** |
|:-:|:-:|
| 2(J5) | U\_D |
| 3(J5) | INC |
| 5V | VH |
| GND | VL |
| 5V/3.3V | VCC |
| GND | GND |

### Software

STEP 1.Download program files[Test\_Demo.zip](../../files/Test-Demo-zip.md)

STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
[![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }  
STEP 3.Load the program in the Arduino IDE

```
int INC = 3;                     // pin D3 of Arduino
int U_D= 2;                    //  pin D2 of Arduino
      
void setup() {
    pinMode (INC, OUTPUT);
    pinMode (U_D, OUTPUT);

    Serial.begin(9600);                                                     // setting the serial speed
    Serial.println("ready!");
}

void loop() {
    for (int i = 0; i < 100; i++) {
      digitalWrite(U_D,LOW);
     for(int n=1;n>0;n--)
     {
     digitalWrite(INC,HIGH);
     delay(50);
     digitalWrite(INC,LOW);    
     }
     
    }
    for (int i = 100; i > 0; i--) {
      digitalWrite(U_D,HIGH);
     for(int n=1;n>0;n--)
     {
     digitalWrite(INC,HIGH);
     delay(50);
     digitalWrite(INC,LOW);  
     }
    }
}
```

STEP4 Click the ![Upload.png](../../assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP5 After downloading the program, use a voltmeter to measure the voltage at VW. It can be seen that the voltage slowly changes from 5V to 0V, and then from 0V to 5V

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Crowtail-Digital\_Programmable\_Potentiometer-V2.0-Eagle.zip](../../files/Crowtail-Digital-Programmable-Potentiometer-V2.0-Eagle-zip.md)  
[Test\_Demo.zip](../../files/Test-Demo-zip.md)  
[X9C103S\_Datasheet.pdf](../../files/X9C103S-Datasheet-pdf.md)  