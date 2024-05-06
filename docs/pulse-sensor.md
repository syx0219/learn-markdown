---
title: Pulse Sensor
---

## Description
-----------

The Pulse Sensor is a plug-and-play heart-rate sensor for Arduino. It can be used by students, artists, athletes, makers, and game &amp; mobile developers who want to easily incorporate live heart-rate data into their projects.Essence it is an integrated optical amplifying circuit and noise eliminating circuit sensor. Clip the Pulse Sensor to your earlobe or finger tip and plug it into your Arduino ,you can ready to read heart rate. Also it have an Arduino demo code that make it easy to use.

**Model:[SO00837PS](http://www.elecrow.com/pulse-sensor-p-1237.html)**

![Pulse Sensor.jpg](https://wiki.elecrow.com/images/thumb/b/b3/Pulse_Sensor.jpg/400px-Pulse_Sensor.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/pulse-sensor-p-1237.html?wiki "Title text")

## Features
--------

- Working voltage: 5V
- Working current: 4mA

## Usage
-----

In the example,we will tell you how to test your pulse with Arduino use the pluse sensor,the pluse ware will display in your PC. So, in this example,we need to install procesing and need two code,one for Arduino,another for processing.

1.Hardware connection  
![Pulse Sensor1.jpg](https://wiki.elecrow.com/images/thumb/9/9e/Pulse_Sensor1.jpg/600px-Pulse_Sensor1.jpg){ loading=lazy }

2.Download the Arduino demo code:[Pulse Sensor Arduino demo code](https://wiki.elecrow.com/images/1/15/PulseSensorAmpd_Processing_1dot2.zip)

3.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries.

4.Open the code directly by the path:File -&gt; Example -&gt;PulseSensorAmpd\_Processing\_1dot1.

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

5.Download the processing code:[processing demo code](https://wiki.elecrow.com/images/b/b5/PulseSensorAmpd_Processing_1dot1.zip),then unzip to your PC.  
6.Download the processing.exe:[processing.exe](https://processing.org/download/?processing),then insstall it.  
7.Open the processing.  
8.Open the processing code.  
![Pulse Sensor4.jpg](https://wiki.elecrow.com/images/thumb/b/b3/Pulse_Sensor4.jpg/400px-Pulse_Sensor4.jpg){ loading=lazy }  
9.Run it,stick the Pulse Sensor onto your fingertip, then you can see the pulse wave.  
![Pulse Sensor5.jpg](https://wiki.elecrow.com/images/c/ce/Pulse_Sensor5.jpg){ loading=lazy }

10.Upload the code,then open the serial monitor to see the result.

![Pulse Sensor6.jpg](https://wiki.elecrow.com/images/thumb/1/14/Pulse_Sensor6.jpg/400px-Pulse_Sensor6.jpg){ loading=lazy }

## Resource
--------

- [Pulse Sensor Arduino demo code](https://wiki.elecrow.com/images/1/15/PulseSensorAmpd_Processing_1dot2.zip)
- [Arduino Code Walkthrough](http://pulsesensor.com/pages/pulse-sensor-amped-arduino-v1dot1)
- [processing demo code](https://wiki.elecrow.com/images/b/b5/PulseSensorAmpd_Processing_1dot1.zip)
- [processing.exe](https://processing.org/download/?processing)