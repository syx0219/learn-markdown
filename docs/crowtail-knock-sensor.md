---
title: Crowtail- Knock Sensor
---

## Description
-----------

The Crowtail-knock sensor is a piezoelectric sensor that contains a piezoelectric sensing crystal and a resister. This crystal creates a small amount of voltage when shaken and takes advantage of this unique property. It will output a pulse when vibration is detected.  
**Model: [CRT00516K](https://www.elecrow.com/crowtail-knock-sensor.html)**  
![Crowtail-knock sensor 1 1.jpg](https://wiki.elecrow.com/images/thumb/6/6b/Crowtail-knock_sensor_1_1.jpg/400px-Crowtail-knock_sensor_1_1.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-knock-sensor.html?wiki "Title text")

## Features
--------

- Digital Crowtail connector

## Specifications
--------------

| **Item** | **Value** |
|---|---|
| Presence sensing | vibration |
| Sensor | KY-031 |
| Power supply | 5V |
| Dimensions(mm) | 20.0(L)x20.0(W)x7.1(H) |

## Pin Map
-------

![Knock sensor interface.png](https://wiki.elecrow.com/images/thumb/b/b6/Knock_sensor_interface.png/500px-Knock_sensor_interface.png){ loading=lazy }

| **Pin Name** | **Description** |
|---|---|
| VCC | Supply Voltage |
| GND | GND |
| SIG | Output a pulse when vibration is detected |

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### Hardware

STEP1 Prepare the below stuffs:

| **Crowduino Uno**                                            | **Base Shield**                                              | **Crowtail-Knock Sensor**                                    | **Crowtail-LED**                                             |
| :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: |
| [![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg){ loading=lazy } | ![Crowtail-base shield 2.jpg](https://wiki.elecrow.com/images/thumb/c/cb/Crowtail-base_shield_2.jpg/200px-Crowtail-base_shield_2.jpg){ loading=lazy } | ![Crowtail-knock sensor 1 1.jpg](https://wiki.elecrow.com/images/thumb/6/6b/Crowtail-knock_sensor_1_1.jpg/250px-Crowtail-knock_sensor_1_1.jpg){ loading=lazy } | ![Crowtail-led 2.jpg](https://wiki.elecrow.com/images/thumb/3/30/Crowtail-led_2.jpg/250px-Crowtail-led_2.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/crowtail-base-shield-p-1264.html) | [**Get one now**](https://www.elecrow.com/crowtail-knock-sensor.html) | [**Get one now**](https://www.elecrow.com/crowtail-led-p-1224.html) |

STEP2 Plug Crowtail-Base Shield into Crowduino Uno;  
STEP3 Plug Crowtail-Knock Sensor into D2 slot on the Crowtail-Base Shield I Port with Crowtail cable;  
STEP4 Plug Crowtail-LED into D3 slot on the Crowtail-Base Shield I Port with Crowtail cable;  
STEP5 Connect Crowduino Uno to PC via a Mini USB cable.  

| ==**NOTE**== |
|---|
| ==If we don't have Crowtail Base Shield, We also can directly connect this module to Crowduino Uno as below.== |

| **Crowduino Uno** | **Crowtail-Knock Sensor** | **Crowtail-LED** |
|:-:|:-:|:-:|
| DIGITAL 2 | SIG | \\ |
| DIGITAL 3 | \\ | SIG |
| 5V | VCC | VCC |
| GND | GND | GND |

### Software

STEP 1.Download program files[Knock\_Sensor.zip](./files/Knock-Sensor-zip.md)  
STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }  
STEP 3 Load the program in the Arduino IDE

```
const int SensorPin = 2;     // the number of the pushbutton pin
const int ledPin =  12;      // the number of the LED pin

// variables will change:
int SensorState = 0;         // variable for reading the pushbutton status

void setup() {
  // initialize the LED pin as an output:
  pinMode(ledPin, OUTPUT);      
  // initialize the pushbutton pin as an input:
  pinMode(SensorPin, INPUT);     
}

void loop(){
  // read the state of the pushbutton value:
  SensorState = digitalRead(SensorPin);

  // check if the pushbutton is pressed.
  // if it is, the buttonState is HIGH:
  if (SensorState == HIGH) {     
    // turn LED on:    
    digitalWrite(ledPin, HIGH);  
  } 
}
```

STEP4 Click the ![Upload.png](./assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP5 After the program is downloaded, knock the sensor you will see the LED lights up.

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Knock\_Sensor.zip](./files/Knock-Sensor-zip.md)  
[Crowtail-\_Knock\_Sensor\_v2.0-Eagle\_file.zip](./files/CrowtailKnock-Sensor-v2.0-Eagle-file.zip.md)