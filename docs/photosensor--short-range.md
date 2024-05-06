---
title: Photosensor- Short Range
---

## Introduction
------------

The reflectivity of infrared light varies with the color and distance of the reflecting surface, According to this principle,Photosensor- Short Range utilizes a TCRT5000 reflective photosensor module to detect color and distance. When a light-colored object approaches,the signal intensity received by infrared reflective sensor increases and the indicator LED on board turns ON. When a dark-colored object approaches, the intensity decreases and the LED turns off. This sensor is a basic and widely used part in applications such as line-following cars, rotary speed detection, auto data logging on utility meters or other situations where color or distance contrast is sharp.  
There is also [a long range version](./photosensor--long-range.md) Photosensor for you to choose.  
[SLS01013S](http://www.elecrow.com/sensors-c-111/proximity-c-111_113/tcrt5000-infrared-photo-reflective-sensor-p-405.html)  
![Photosensor- Short Range1.jpg](https://wiki.elecrow.com/images/thumb/7/77/Photosensor-_Short_Range1.jpg/400px-Photosensor-_Short_Range1.jpg){ loading=lazy }

## Features
--------

- Operating voltage: 4.5 V - 5.5 V.
- Digital output, 0 or VCC.
- High resolution sensor;minumum detectable length: 1mm black line.
- Effective distance：1-8mm,optimum:2.5mm.
- Indicator LED on board.
- Size:35\*7.5\*5mm.
- Easy to use in obstacle sensoring; White/Black wire tracking

## Usage
-----

There is a infrared emitter and a receiver on this module, the emitter always emit infrared ray. When the infrared light emitted by the emitter gets reflected on a surface that blocked it, the phototransistor can pick up the signal. with this way, this module can be used to detect if there is a obstacle in the measuring range. It can be also use to do White/Black wire tracking because the black wire absorb the rays while the white wire reflect the rays.

### **Hardware**

Connect the Photosensor to your Arduino/Crowduino power supply pin and digital pins. You can can connect the "s" terminal to any of your arduino Pins,like the "D6" as belows:
![Phosensor hard.jpg](https://wiki.elecrow.com/images/e/e1/Phosensor_hard.jpg){ loading=lazy }

### **Programming**

1.Copy the following program to Arduino IDE and upload to your Arduino/Crowduino:

```
void setup()  {
  Serial.begin(9600);
  pinMode(6,INPUT);
}
void loop()  {
  while(1)  {
    delay(500);
    if(digitalRead(6)==HIGH)  {
      Serial.println("Somebody is here.");
    }
    else  {
      Serial.println("Nobody.");
    }
  }
}
```

2.Open the Serial moniter , and set the baudrate to 9600, you will see that When somebody is in front of the sensor , the Serial Monitor will output "Somebody is here.".Or, the Serial Monitor output "Nobody."   
![Photosensor- Short Range test result.jpg](https://wiki.elecrow.com/images/d/df/Photosensor-_Short_Range_test_result.jpg){ loading=lazy }

### **Resource**

[File:TCRT5000 datasheet.pdf](https://wiki.elecrow.com/images/9/9f/TCRT5000_datasheet.pdf "File:TCRT5000 datasheet.pdf")