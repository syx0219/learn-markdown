---
title: Crowbits-Keyboard
---


## Description
-----------

Each key on the keyboard can input various numbers and symbols, which also integrated a microphone. You can use it for scenarios such as phone buttons. Add a lot of fun to your project.

![Crowbits-Keyboard-1.jpg](https://wiki.elecrow.com/images/f/f1/Crowbits-Keyboard-1.jpg){ loading=lazy }

## Features
--------

- SMD silicone silent keyboard

## Specification
-------------

- Interface Type: Analog input
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*56(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the A2 interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-Keyboard-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/d/d9/Crowbits-Keyboard-Wiki_1.JPG/600px-Crowbits-Keyboard-Wiki_1.JPG){ loading=lazy }

3\. Upload the following code to the Crowbits-UNO board.

```
int sensorPin = A2;
int sensorValue = 0;
int a = 0;

void setup() {
  Serial.begin(9600);
  Serial.println("Please press a Key");
}

void loop() 
{
  sensorValue = analogRead(sensorPin);
  a = sensorValue;
  // a = sensorValue/10;
  //Serial.println(sensorValue);
  if (a >= 0 && a <= 40 ) {
    Serial.println("7");
   // Serial.println(a);
    delay(500);
  }

  if (a >= 50 && a <= 90 ) {
    Serial.println("8");
   // Serial.println(a);
    delay(500);
  }

  if (a >= 100 && a <= 150 ) {
    Serial.println("9");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 160 && a <= 200 ) {
    Serial.println("+");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 230 && a <= 270 ) {
    Serial.println("4");
    delay(500);
  }
  if (a >= 290 && a <= 330 ) {
    Serial.println("5");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 350 && a <= 390 ) {
    Serial.println("6");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 420 && a <= 460 ) {
    Serial.println("-");
    //Serial.println(a);
    delay(500);
  }
  if (a >= 480 && a <= 520 ) {
    Serial.println("1");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 545 && a <= 585 ) {
    Serial.println("2");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 600 && a <= 640 ) {
    Serial.println("3");
    //Serial.println(a);
    delay(500);
  }
  if (a >= 670 && a <= 710 ) {
    Serial.println("*");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 735 && a <= 775 ) {
    Serial.println(".");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 790 && a <= 835 ) {
    Serial.println("0");
   // Serial.println(a);
    delay(500);
  }
  if (a >= 860 && a <= 900 ) {
    Serial.println("=");
    //Serial.println(a);
    delay(500);
  }
  if (a > 900 && a <= 945 ) {
    Serial.println("/");
   // Serial.println(a);
    delay(500);
  }
}
```

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Press the keys on the keyboard, the serial port will output the corresponding numbers and symbols.

![Crowbits-Keyboard-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/0/0a/Crowbits-Keyboard-Wiki_2.jpg/600px-Crowbits-Keyboard-Wiki_2.jpg){ loading=lazy }