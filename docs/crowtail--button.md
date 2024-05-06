---
title: Crowtail- Button
---

## Description
-----------

The Crowtail-Button is a momentary push button which rebounds on its own after it is released. The button outputs a HIGH signal when pressed, and LOW when released.

**Model: [CT0002BT](http://www.elecrow.com/crowtailbutton-p-1222.html)**

![Crowtail-Button.JPG](https://wiki.elecrow.com/images/thumb/0/0b/Crowtail-Button.JPG/600px-Crowtail-Button.JPG){ loading=lazy }

## Features
--------

- Easy to use momentary ON/OFF button
- Uses Standard 3-pin Crowtail Cables to connect to the Crowtail - Base Shield
- Dimensions(mm):20.0(L)x20.0(W)x11.4(H)

## Usage
-----

Button control LED

1.Hardware connection

![Buttoncontro.jpg](https://wiki.elecrow.com/images/thumb/c/c9/Buttoncontro.jpg/500px-Buttoncontro.jpg){ loading=lazy }

2.Upload the following sample sketch to make the LED turn ON and OFF based on input from Crowtial - Button:

```
/*
 Button
 
 Turns on and off a light emitting diode(LED) connected to digital  
 pin 5, when pressing a pushbutton attached to pin 4. 
*/

// set pin numbers:
const int buttonPin = 4;     // the number of the pushbutton pin
const int ledPin =  5;      // the number of the LED pin

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status

void setup() {
 // initialize the LED pin as an output:
 pinMode(ledPin, OUTPUT);      
 // initialize the pushbutton pin as an input:
 pinMode(buttonPin, INPUT);     
}

void loop(){
 // read the state of the pushbutton value:
 buttonState = digitalRead(buttonPin);

 // check if the pushbutton is pressed.
 // if it is, the buttonState is HIGH:
 if (buttonState == HIGH) {     
   // turn LED on:    
   digitalWrite(ledPin, HIGH);  
 } 
 else {
   // turn LED off:
   digitalWrite(ledPin, LOW); 
 }
}
```

3.Press the Botton, you will see the LED lights up.

## Resource
--------

- [Button Program](./files/Button-zip.md)
- [Crowtail\_Button\_eagle\_files](./files/Crowtail-Button-files-zip.md)