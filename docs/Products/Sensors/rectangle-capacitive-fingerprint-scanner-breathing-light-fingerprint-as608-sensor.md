---
title: Rectangle capacitive fingerprint scanner breathing light fingerprint AS608 sensor
---

## Description
-----------

This fingerprint module can store 300 fingerprints and has the functions of collecting fingerprints, reading fingerprints, and identifying fingerprints. It is not only small in size, low in power consumption, simple in interface, high in reliability, and also has fast recognition speed and good adaptability to wet and dry fingers.  
When the fingerprint image is read, it has a sensitive response and judgment to dry and wet fingers and obtains the best imaging quality, which is suitable for a wide range of people. At the same time, it has the function of self-learning, which can achieve better matching. The module also has the function of sensing the finger. When the finger is pressed on the fingerprint collection surface, the module Touch pin outputs a high level. The module communication interface is UART communication interface.  
**Model:[DPI50249S](https://www.elecrow.com/rectangle-capacitive-fingerprint-module-breathing-light-fingerprint-as608-sensor-support-identify-stm32-source-code.html)**   
![Rectangle fingerprint.png](https://wiki.elecrow.com/images/thumb/7/79/Rectangle_fingerprint.png/300px-Rectangle_fingerprint.png){ loading=lazy }

## Module dimension drawing (unit: mm)
-----------------------------------

![Module dimension drawing.png](https://wiki.elecrow.com/images/4/43/Module_dimension_drawing.png){ loading=lazy }

## Feature
-------

- Compact size and simple structure
- Low power consumption, simple interface, high reliability
- Fast recognition speed, good adaptability to wet and dry fingers, and fast fingerprint search

| Parameter | VALUE |
|:-:|:-:|
| Sensor | Capacitive touch sensor |
| Resolution | 508 DPI |
| Image pixels | 160\*160 |
| Fingerprint image collection time | &lt;110ms |
| Fingerprint capacity | 300 |
| Algorithmic search time | &lt;30ms(100pcs) |
| Matching method | 1:1,1:N |
| Overall recognition time | &lt;1s(100pcs) |
| False acceptance rate | &lt;0.001% |
| False rejection rate | &lt;1% |
| Operating voltage | 3.3±0.3（v） |
| Operating current | &lt;55mA |
| Communication port | UART |

## Pin Definition
--------------

| Pin Number | Name | Type | Function Description |
|---|---|---|---|
| 1 | Vsen | In | Fingerprint sensor power input, +3.3V |
| 2 | Touch | Out | Fingerprint sensor touch sensing signal output, active high by default |
| 3 | VDD | In | Module DSP power positive input, +3.3V |
| 4 | TX | Out | Serial data output, TTL logic level |
| 5 | RX | In | Serial data input, TTL logic level |
| 6 | GND | - | Signal ground, internally connected to power ground |

![Rectangle fingerprint pin.png](https://wiki.elecrow.com/images/thumb/e/eb/Rectangle_fingerprint_pin.png/250px-Rectangle_fingerprint_pin.png){ loading=lazy }  
**The Wiring diagram：**

The order of the pins is from right to left, ① in the figure is the No. 1 pin  
![Rectangle fingerprint wiring diagram.png](https://wiki.elecrow.com/images/thumb/c/c4/Rectangle_fingerprint_wiring_diagram.png/400px-Rectangle_fingerprint_wiring_diagram.png){ loading=lazy }

## Building a Smart fingerprint box
--------------------------------

**Download files:[Smart fingerprint box](https://wiki.elecrow.com/images/7/78/Smart_fingerprint_box.zip)**

**Implement a box that can lock and unlock by fingerprint identification:**  
**1. Fingerprint sensor cable details:**  
![IMG 3996.JPG](https://wiki.elecrow.com/images/thumb/e/e0/IMG_3996.JPG/200px-IMG_3996.JPG){ loading=lazy } 
![IMG 3997.JPG](https://wiki.elecrow.com/images/thumb/8/84/IMG_3997.JPG/200px-IMG_3997.JPG){ loading=lazy } 
![IMG 3999.JPG](https://wiki.elecrow.com/images/thumb/b/b8/IMG_3999.JPG/200px-IMG_3999.JPG){ loading=lazy }

![Smart fingerprint box.png](https://wiki.elecrow.com/images/thumb/1/11/Smart_fingerprint_box.png/600px-Smart_fingerprint_box.png){ loading=lazy }

**2. Uploading code:**  
Upload code with Arduino：  
![4001.png](https://wiki.elecrow.com/images/thumb/c/ca/4001.png/800px-4001.png){ loading=lazy }

```
#include <Adafruit_Fingerprint.h>
// For UNO and others without hardware serial, we must use software serial...
// pin #2 is IN from sensor (GREEN wire)
// pin #3 is OUT from Arduino  (WHITE wire)
// comment these two lines if using hardware serial
#include <Servo.h>
SoftwareSerial mySerial(2, 3);
Servo myservo;  // create servo object to control a servo
int i = 0;
int potpin = A0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

Adafruit_Fingerprint finger = Adafruit_Fingerprint(&mySerial);

void setup()  
{
  Serial.begin(9600);
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
  myservo.write(80);
  while (!Serial);  // For Yun/Leo/Micro/Zero/...
  delay(100);
  Serial.println("\n\nAdafruit finger detect test");

  // set the data rate for the sensor serial port
  finger.begin(57600);
  delay(5);
  if (finger.verifyPassword()) {
    Serial.println("Found fingerprint sensor!");
  } 
  else {
    Serial.println("Did not find fingerprint sensor :(");
    while (1) { delay(1); }
  }

  finger.getTemplateCount();
  Serial.print("Sensor contains "); Serial.print(finger.templateCount); Serial.println(" templates");
  Serial.println("Waiting for valid finger...");
}

void loop()                     // run over and over again
{
  getFingerprintIDez();
  delay(50);            //don't ned to run this at full speed.
}

uint8_t getFingerprintID() {
  uint8_t p = finger.getImage();
  switch (p) {
    case FINGERPRINT_OK:
      Serial.println("Image taken");
      break;
    case FINGERPRINT_NOFINGER:
      Serial.println("No finger detected");
      return p;
    case FINGERPRINT_PACKETRECIEVEERR:
      Serial.println("Communication error");
      return p;
    case FINGERPRINT_IMAGEFAIL:
      Serial.println("Imaging error");
      return p;
    default:
      Serial.println("Unknown error");
      return p;
  }

  // OK success!

  p = finger.image2Tz();
  switch (p) {
    case FINGERPRINT_OK:
      Serial.println("Image converted");
      break;
    case FINGERPRINT_IMAGEMESS:
      Serial.println("Image too messy");
      return p;
    case FINGERPRINT_PACKETRECIEVEERR:
      Serial.println("Communication error");
      return p;
    case FINGERPRINT_FEATUREFAIL:
      Serial.println("Could not find fingerprint features");
      return p;
    case FINGERPRINT_INVALIDIMAGE:
      Serial.println("Could not find fingerprint features");
      return p;
    default:
      Serial.println("Unknown error");
      return p;
  }
  
  // OK converted!
  p = finger.fingerFastSearch();
  if (p == FINGERPRINT_OK) {
    Serial.println("Found a print match!");
  } else if (p == FINGERPRINT_PACKETRECIEVEERR) {
    Serial.println("Communication error");
    return p;
  } else if (p == FINGERPRINT_NOTFOUND) {
    Serial.println("Did not find a match");
    return p;
  } else {
    Serial.println("Unknown error");
    return p;
  }   
  
  // found a match!
  Serial.print("Found ID #"); Serial.print(finger.fingerID); 
  Serial.print(" with confidence of "); Serial.println(finger.confidence); 

  return finger.fingerID;
}

// returns -1 if failed, otherwise returns ID #
int getFingerprintIDez() {
  uint8_t p = finger.getImage();
  
  if (p != FINGERPRINT_OK)  return -1;

  p = finger.image2Tz();
  if (p != FINGERPRINT_OK)  return -1;

  p = finger.fingerFastSearch();
  if (p != FINGERPRINT_OK)  return -1;
  
  // found a match!
  Serial.print("Found ID #"); Serial.print(finger.fingerID); 
  Serial.print(" with confidence of "); Serial.println(finger.confidence);
  if(finger.confidence > 80){
    if (i > 0){
      myservo.write(80);
      delay(1000);
      i = 0;
      Serial.print(i);
    }
    else{
      myservo.write(160);
      delay(1000);
      i = 1;
      Serial.print(i);
      }
    
    }
 
  return finger.fingerID; 
}
```