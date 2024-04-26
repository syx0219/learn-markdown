---
title: Crowtail- Solid-State Relay
---

## Description
-----------

Crowtail- Solid-State Relay is a non-contact electronic switch module that has relay features.It has a maximum output of 240VAC/4A, with a switching speed less than 10ms. The featured LED indicates that the relay is on. It can be widely used in various areas such as computer peripheral interfaces, temperature/speed light adjustment, servo control, petrochemical, medical instrumentations, financial devices, coal, meters, traffic signals, etc.   
**Model: [CT009739R](https://www.elecrow.com/crowtail-solid-state-relay.html)**

![Crowtail- Solid-State Relay.jpg](https://wiki.elecrow.com/images/thumb/5/52/Crowtail-_Solid-State_Relay.jpg/600px-Crowtail-_Solid-State_Relay.jpg){ loading=lazy }

## Features
--------

- Compatible with both 3.3V and 5V control level
- Low switching latency（≤10ms）
- LED on-state indicator
- Level trigger
- Crowtail compatible
- Dimensions(mm):40.0(L)x20.0(W)x22.9(H)

## Application Ideas
-----------------

- Operations that require low-latency switching, e.g. stage light control
- Devices that require high stability, e.g. medical devices, traffic signals
- Situations that require explosion-proof, anticorrosion, moisture-proof, e.g. coal, chemical industries.
- For all Grove users (especially beginners), we provide you guidance PDF documents. Please download and read through Preface - Getting Started and Introduction to Grove before your using of the product.

## Usage
-----

1.Trigger signal voltage:

- Low level: 0-1.5 V the relay ON
- High level: 2.5-5 V the relay OFF

2.Connect Crowtail- Solid-State Relay to port D2(one button to D5) of Crowtail - Base Shield and plug it into Arduino/Crowduino.

![20160531 1113071.jpg](https://wiki.elecrow.com/images/thumb/e/e2/20160531_1113071.jpg/500px-20160531_1113071.jpg){ loading=lazy }

3.Copy and paste code below to a new Arduino sketch, and upload it to your Arduino.

```
 int relay=2;
 int buttonPin=5;
 int buttonState = 0;
 void setup ()
 { 
   pinMode(relay,OUTPUT);
   pinMode(buttonPin, INPUT); 
 }
 void loop()
 {
        buttonState = digitalRead(buttonPin);
         if (buttonState == HIGH) {     
      
    digitalWrite(relay, LOW);  
  } 
  else {
    
    digitalWrite(relay, HIGH); 
  }
 }
```

4.When upload the code complete. Press the button, the yellow indicator light turns on , Relay on. Loosen the button, indicator light off and relay is off yet.

## Resource
--------

- [Crowtail- Solid-State Relay eagle file](../../files/Crowtail-Solid-State-Relay-eagle-file-zip.md)