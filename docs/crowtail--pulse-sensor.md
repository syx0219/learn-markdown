---
title: Crowtail- Dry-Reed Relay
---

## Description
-----------

The Pulse Sensor is used to measure the heart rate of the human.Heart rate data can be really useful whether you’re designing an exercise routine, studying your activity or anxiety levels or just want your shirt to blink with your heart beat. The problem is that heart rate can be difficult to measure. Luckily, the Pulse Sensor Amped can solve that problem! The Pulse Sensor Amped is a plug-and-play heart-rate sensor for Arduino. It can be used by students, artists, athletes, makers, and game &amp; mobile developers who want to easily incorporate live heart-rate data into their projects.It essentially combines a simple optical heart rate sensor with amplification and noise cancellation circuitry making it fast and easy to get reliable pulse readings. Also, it sips power with just 4mA current draw at 5V so it’s great for mobile applications. Simply clip the Pulse Sensor to your earlobe or finger tip and plug it into your 3or5 Volt Arduino and you’re ready to read heart rate! The 24" cable on the Pulse Sensor is terminated with standard male headers so there’s no soldering required. Of course Arduino example code is available as well as a Processing sketch for visualizing heart rate data.

**Model: [CT010712P](https://www.elecrow.com/crowtail-pulse-sensor-p-1673.html)**

![Crowtail- Pulse Sensor1.jpg](https://wiki.elecrow.com/images/thumb/8/87/Crowtail-_Pulse_Sensor1.jpg/600px-Crowtail-_Pulse_Sensor1.jpg){ loading=lazy }

## Description
-----------

- Voltage: 3-5V
- Diameter: 16mm
- Magnification: 330
- Led wavelength: 609nm
- Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

## Usage
-----

### **With Arduino**

**1.Hardware Connection**  
The Crowtail- Pulse Sensor is connecting to analog port A0 of Crowtail - Base Shield.  
![Pulse sensor 11.jpg](https://wiki.elecrow.com/images/thumb/e/ed/Pulse_sensor_11.jpg/400px-Pulse_sensor_11.jpg){ loading=lazy }

2.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.Or download:[Pulse Sensor demo code](./files/PulseSensorAmped-Arduino-1dot2-zip.md) . Unzip it and open the file:PulseSensorAmped\_Arduino\_1\_2.ino.

```
//  VARIABLES
int pulsePin = 0;                 // Pulse Sensor purple wire connected to analog pin 0
int blinkPin = 13;                // pin to blink led at each beat
int fadePin = 5;                  // pin to do fancy classy fading blink at each beat
int fadeRate = 0;                 // used to fade LED on with PWM on fadePin


// these variables are volatile because they are used during the interrupt service routine!
volatile int BPM;                   // used to hold the pulse rate
volatile int Signal;                // holds the incoming raw data
volatile int IBI = 600;             // holds the time between beats, must be seeded! 
volatile boolean Pulse = false;     // true when pulse wave is high, false when it's low
volatile boolean QS = false;        // becomes true when Arduoino finds a beat.


void setup(){
  pinMode(blinkPin,OUTPUT);         // pin that will blink to your heartbeat!
  pinMode(fadePin,OUTPUT);          // pin that will fade to your heartbeat!
  Serial.begin(115200);             // we agree to talk fast!
  interruptSetup();                 // sets up to read Pulse Sensor signal every 2mS 
   // UN-COMMENT THE NEXT LINE IF YOU ARE POWERING The Pulse Sensor AT LOW VOLTAGE, 
   // AND APPLY THAT VOLTAGE TO THE A-REF PIN
   //analogReference(EXTERNAL);   
}



void loop(){
  sendDataToProcessing('S', Signal);     // send Processing the raw Pulse Sensor data
  if (QS == true){                       // Quantified Self flag is true when arduino finds a heartbeat
        fadeRate = 255;                  // Set 'fadeRate' Variable to 255 to fade LED with pulse
        sendDataToProcessing('B',BPM);   // send heart rate with a 'B' prefix
        sendDataToProcessing('Q',IBI);   // send time between beats with a 'Q' prefix
        QS = false;                      // reset the Quantified Self flag for next time    
     }
  
  ledFadeToBeat();
  
  delay(20);                             //  take a break
}


void ledFadeToBeat(){
    fadeRate -= 15;                         //  set LED fade value
    fadeRate = constrain(fadeRate,0,255);   //  keep LED fade value from going into negative numbers!
    analogWrite(fadePin,fadeRate);          //  fade LED
  }


void sendDataToProcessing(char symbol, int data ){
    Serial.print(symbol);                // symbol prefix tells Processing what type of data is coming
    Serial.println(data);                // the data to send culminating in a carriage return
  }
```

3.Download the upper computer software [processing](https://processing.org/download/?processing).Unzip it,and open the processing.exe,then file—open,you should download the file:[processing\_code](./files/Processing-code-zip.md).Unzip it and open the file:PulseSensorAmpd\_Processing\_1dot1.pde

![Processing code.png](https://wiki.elecrow.com/images/thumb/6/65/Processing_code.png/400px-Processing_code.png){ loading=lazy }


4.Open the device manager of the computer and check whether there's a port named COM1. If there is a COM1 port, please disable it;


![Pulse sensor com1.png](https://wiki.elecrow.com/images/thumb/e/ee/Pulse_sensor_com1.png/400px-Pulse_sensor_com1.png){ loading=lazy }


5.Run the Processing software. Put you finger on the pulse sensor area of the heart shape.You will see that your heart rate and heart rate waveform(electrocardiogram)

![Processing measurement.png](https://wiki.elecrow.com/images/thumb/a/a5/Processing_measurement.png/400px-Processing_measurement.png){ loading=lazy }

## Resource
--------

- [Pulse Sensor Arduino demo code](./files/PulseSensorAmped-Arduino-1dot2-zip.md)
- [processing](https://processing.org/download/?processing)
- [processing\_code](./files/Processing-code-zip.md)
- [Crowtail- Pulse Sensor eagle file](./files/Crowtail-Pulse-Sensor-eagle-file-zip.md)
- [APDS-9008-020-Avago](./files/APDS-9008-020-Avago-pdf.md)