---
title: Fingerprint Sensor
---

## Description
-----------

This all-in-one optical fingerprint sensor will make adding fingerprint detection and verification super simple. These modules are typically used in safes - there's a high powered DSP chip AS601 that does the image rendering, calculation, feature-finding and searching. Connect to any microcontroller or system with TTL serial, and send packets of data to take photos, detect prints, hash and search. You can also enroll new fingers directly - up to 120 finger prints can be stored in the onboard FLASH memory. As the usage, the fingerprint is really easy to use with the serial UART. There is already some libraries to help your using this sensor with Arduino , such as the adafruit fingerprint library.

**Model:[SOT6439F](http://www.elecrow.com/fingerprint-sensor-p-697.html)**

![Fingerprint Sensor.jpg](https://wiki.elecrow.com/images/thumb/a/aa/Fingerprint_Sensor.jpg/400px-Fingerprint_Sensor.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/fingerprint-sensor-p-697.html?wiki "Title text")

## Features
--------

- Communication: UART(TTL)
- Fingerprint number: 120 on default
- Can set the security level and baud rate flexibility
- Working Current@Voltage: &lt;120mA@DC3.6~6V
- Temprature: -20 - +50 degrees
- Humidity: &lt;85%
- Dimension: 56x20x21.5mm

## Usage
-----

### **Enrolling New Users with Windows**

1.Hardware Connection

![Fingerprint Sensor hardware.jpg](https://wiki.elecrow.com/images/thumb/3/3a/Fingerprint_Sensor_hardware.jpg/600px-Fingerprint_Sensor_hardware.jpg){ loading=lazy }

2.Copy the below code to you new skecth,then upload it.

```
// Red connects to +5V
// Black connects to Ground
// White goes to Digital 0
// Green goes to Digital 1
 
void setup() {}
void loop() {}
```

3.Download the SFGDemoV2.0 :[SFGDemoV2.0](./files/SFGDemoV2.0-zip.md)    
3.Start up the SFGDemo software and click Open Device from the bottom left corner. Select the COM port used by the Arduino.

![SFGDemoV2.01.jpg](https://wiki.elecrow.com/images/thumb/c/c0/SFGDemoV2.01.jpg/600px-SFGDemoV2.01.jpg){ loading=lazy }

4.And press OK when done. You should see the following, with a blue success message and some device statistics in the bottom corner. You can change the baud rate in the bottom left hand corner, as well as the "security level" (how sensitive it is) but we suggest leaving those alone until you have everything running and you want to experiment. They should default to 57600 baud and security level 3 so set them if they're wrong .

![SFGDemoV2.02.jpg](https://wiki.elecrow.com/images/thumb/4/49/SFGDemoV2.02.jpg/600px-SFGDemoV2.02.jpg){ loading=lazy }

5.Lets enroll a new finger! Click the Preview checkbox and press the Enroll button next to it (Con Enroll means 'Continuous' enroll, which you may want to do if you have many fingers to enroll). When the box comes up, enter in the ID # you want to use. You can use up to 162 ID numbers.

![SFGDemoV2.03.jpg](https://wiki.elecrow.com/images/0/07/SFGDemoV2.03.jpg){ loading=lazy }

6.The software will ask you to press the finger to the sensor.

![SFGDemoV2.04.jpg](https://wiki.elecrow.com/images/0/02/SFGDemoV2.04.jpg){ loading=lazy }

7.You can then see a preview (if you cliecked the preview checkbox) of the fingerprint.

![SFGDemoV2.05.jpg](https://wiki.elecrow.com/images/thumb/9/99/SFGDemoV2.05.jpg/600px-SFGDemoV2.05.jpg){ loading=lazy }

You will then have to repeat the process, to get a second clean print. Use the same finger!  
On success you will get a notice.

![SFGDemoV2.06.jpg](https://wiki.elecrow.com/images/thumb/a/a3/SFGDemoV2.06.jpg/600px-SFGDemoV2.06.jpg){ loading=lazy }

If there's a problem such as a bad print or image, you'll have to do it again.

### **Searching with the Software**

1.Click on the Search button on the right hand side.

![SFGDemoV2.07.jpg](https://wiki.elecrow.com/images/2/2a/SFGDemoV2.07.jpg){ loading=lazy }

2.When prompted, press a different/same finger to the sensor.  
If it is the same finger, you should get a match with the ID #

![SFGDemoV2.08.jpg](https://wiki.elecrow.com/images/thumb/d/d5/SFGDemoV2.08.jpg/600px-SFGDemoV2.08.jpg){ loading=lazy }

If it is not a finger in the database, you will get a failure notice.

![SFGDemoV2.09.jpg](https://wiki.elecrow.com/images/thumb/d/d4/SFGDemoV2.09.jpg/600px-SFGDemoV2.09.jpg){ loading=lazy }

### **Wiring for use with Arduino**

1.Hardware Connection

![Fingerprint Sensor hardware2.jpg](https://wiki.elecrow.com/images/thumb/b/bd/Fingerprint_Sensor_hardware2.jpg/600px-Fingerprint_Sensor_hardware2.jpg){ loading=lazy }

2.Download the Fingerprint Sensor library:[Fingerprint Sensor library](https://wiki.elecrow.com/images/7/7a/Adafruit_Fingerprint.zip),Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

3.Open the code directly by the path:File -&gt; Example -&gt;Adafruit\_Fingerprint→fingerprint

```
#include <Adafruit_Fingerprint.h>
#include <SoftwareSerial.h>

int getFingerprintIDez();

// pin #2 is IN from sensor (GREEN wire)
// pin #3 is OUT from arduino  (WHITE wire)
SoftwareSerial mySerial(2, 3);


Adafruit_Fingerprint finger = Adafruit_Fingerprint(&mySerial);

void setup()  
{
  Serial.begin(9600);
  Serial.println("fingertest");

  // set the data rate for the sensor serial port
  finger.begin(57600);
  
  if (finger.verifyPassword()) {
    Serial.println("Found fingerprint sensor!");
  } else {
    Serial.println("Did not find fingerprint sensor :(");
    while (1);
  }
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
  return finger.fingerID; 
}
```

4.Upload the Code,Open up the serial monitor at 9600 baud and when prompted place your finger against the sensor that was already enrolled.  
You should see the following:

![SFGDemoV2.010.jpg](https://wiki.elecrow.com/images/8/84/SFGDemoV2.010.jpg){ loading=lazy }

### **Enrolling with Arduino**

1.Hardware Connection

![Fingerprint Sensor hardware2.jpg](https://wiki.elecrow.com/images/thumb/b/bd/Fingerprint_Sensor_hardware2.jpg/600px-Fingerprint_Sensor_hardware2.jpg){ loading=lazy }

2.Download the Fingerprint Sensor library:[Fingerprint Sensor library](https://wiki.elecrow.com/images/7/7a/Adafruit_Fingerprint.zip),Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

3.Open the code directly by the path:File -&gt; Example -&gt;Adafruit\_Fingerprint→enroll

```
#include <Adafruit_Fingerprint.h>
#include <SoftwareSerial.h>

uint8_t getFingerprintEnroll(int id);


// pin #2 is IN from sensor (GREEN wire)
// pin #3 is OUT from arduino  (WHITE wire)
SoftwareSerial mySerial(2, 3);

Adafruit_Fingerprint finger = Adafruit_Fingerprint(&mySerial);

void setup()  
{
  Serial.begin(9600);
  Serial.println("fingertest");

  // set the data rate for the sensor serial port
  finger.begin(57600);
  
  if (finger.verifyPassword()) {
    Serial.println("Found fingerprint sensor!");
  } else {
    Serial.println("Did not find fingerprint sensor :(");
    while (1);
  }
}

void loop()                     // run over and over again
{
  Serial.println("Type in the ID # you want to save this finger as...");
  int id = 0;
  while (true) {
    while (! Serial.available());
    char c = Serial.read();
    if (! isdigit(c)) break;
    id *= 10;
    id += c - '0';
  }
  Serial.print("Enrolling ID #");
  Serial.println(id);
  
  while (!  getFingerprintEnroll(id) );
}

uint8_t getFingerprintEnroll(int id) {
  int p = -1;
  Serial.println("Waiting for valid finger to enroll");
  while (p != FINGERPRINT_OK) {
    p = finger.getImage();
    switch (p) {
    case FINGERPRINT_OK:
      Serial.println("Image taken");
      break;
    case FINGERPRINT_NOFINGER:
      Serial.println(".");
      break;
    case FINGERPRINT_PACKETRECIEVEERR:
      Serial.println("Communication error");
      break;
    case FINGERPRINT_IMAGEFAIL:
      Serial.println("Imaging error");
      break;
    default:
      Serial.println("Unknown error");
      break;
    }
  }

  // OK success!

  p = finger.image2Tz(1);
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
  
  Serial.println("Remove finger");
  delay(2000);
  p = 0;
  while (p != FINGERPRINT_NOFINGER) {
    p = finger.getImage();
  }

  p = -1;
  Serial.println("Place same finger again");
  while (p != FINGERPRINT_OK) {
    p = finger.getImage();
    switch (p) {
    case FINGERPRINT_OK:
      Serial.println("Image taken");
      break;
    case FINGERPRINT_NOFINGER:
      Serial.print(".");
      break;
    case FINGERPRINT_PACKETRECIEVEERR:
      Serial.println("Communication error");
      break;
    case FINGERPRINT_IMAGEFAIL:
      Serial.println("Imaging error");
      break;
    default:
      Serial.println("Unknown error");
      break;
    }
  }

  // OK success!

  p = finger.image2Tz(2);
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
  p = finger.createModel();
  if (p == FINGERPRINT_OK) {
    Serial.println("Prints matched!");
  } else if (p == FINGERPRINT_PACKETRECIEVEERR) {
    Serial.println("Communication error");
    return p;
  } else if (p == FINGERPRINT_ENROLLMISMATCH) {
    Serial.println("Fingerprints did not match");
    return p;
  } else {
    Serial.println("Unknown error");
    return p;
  }   
  
  Serial.print("ID "); Serial.println(id);
  p = finger.storeModel(id);
  if (p == FINGERPRINT_OK) {
    Serial.println("Stored!");
  } else if (p == FINGERPRINT_PACKETRECIEVEERR) {
    Serial.println("Communication error");
    return p;
  } else if (p == FINGERPRINT_BADLOCATION) {
    Serial.println("Could not store in that location");
    return p;
  } else if (p == FINGERPRINT_FLASHERR) {
    Serial.println("Error writing to flash");
    return p;
  } else {
    Serial.println("Unknown error");
    return p;
  }   
}
```

4.Upload the Code,open up the serial monitor, it will ask for you to type in the ID to enroll - use the box up top to type in a number and click Send


![SFGDemoV2.011.jpg](https://wiki.elecrow.com/images/c/c0/SFGDemoV2.011.jpg){ loading=lazy }

5.Then go through the enrollment process as indicated. When it has successfully enrolled a finger, it will print Stored!

![SFGDemoV2.012.jpg](https://wiki.elecrow.com/images/4/44/SFGDemoV2.012.jpg){ loading=lazy }

## Resource
--------

- [Fingerprint library](https://wiki.elecrow.com/images/7/7a/Adafruit_Fingerprint.zip)
- [SFGDemoV2.0](./files/SFGDemoV2.0-zip.md)
- [Datasheet](./files/DY001fingerprint-pdf.md)