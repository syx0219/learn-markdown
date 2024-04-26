---
title: Crowtail- IR Receiver
---

## Description
-----------

The Crowtail- IR Receiver module uses the HS0038B which is miniaturized receivers for infrared remote control systems and it is the standard IR remote control receiver series, supporting all major transmission codes. The IR detector have a demodulator inside that looks for modulated IR at 38 KHz. The Infrared Receiver can receive signals well within 10 meters. If more than 10 meters , the receiver may not get the signals. We often use the two Crowtail-the Infrared Receiver and the Crowtail- Infrared Emitter to work together.

**Model: [CT0031IRR](http://www.elecrow.com/crowtail-ir-emitter-p-1308.html)**

![Crowtail-IR Receiver.JPG](https://wiki.elecrow.com/images/thumb/e/ef/Crowtail-IR_Receiver.JPG/600px-Crowtail-IR_Receiver.JPG){ loading=lazy }

## Features
--------

- Connection Mode: D(digtal)
- Voltage: 3.3-5V
- Distance:10m
- Dimensions(mm):20.0(L)x20.0(W)x11.0(H)

## Usage
-----

The Crowtail - IR Receiver will receive the data that the Crowtail - Infrared Emitter send.

1.Hardware connection

Connect the Crowtail- IR Receiver to D2.

Connect the Crowtail- IR Emitter to D3.

![IRhardware11.jpg](https://wiki.elecrow.com/images/thumb/5/5e/IRhardware11.jpg/600px-IRhardware11.jpg){ loading=lazy }

2.Download the library[IRSendRev library](https://wiki.elecrow.com/images/6/67/IRSendRev.zip);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

3.Open the code directly by the path:File -&gt; Example -&gt;IRSendRev-&gt;sendTest.

```
//**************
//IR sent demo v1.0
//Connect the IR sent pins to D3 for this demo
//******************************
#include <IRSendRev.h>

void setup()
{
   //enableIROut(38);
}
//unsigned char d[] = {9, 90, 91, 11, 31, 4, 1, 2, 3, 4};
unsigned char d[] = {15, 70, 70, 20, 60, 10, 1, 2, 3, 4,5,6,7,8,9,10};
//Very Important:
//the first parameter(15): the data that needs to be sent;
//the next 2 parameter(70,70): the logic high and low duration of "Start";
//the next 2 parameter(20,60): the logic "short" and "long"duration in the communication
//                             that to say:  if "0", the high duration is 20ms and  low is 20 ms; while logic "1",
//                              the high duration is 20 ms and low is 60 ms;
//the next 2 parameter(10): number of data you will sent;
//the next parameter(1, 2, 3, 4,5,6,7,8,9,10): data you will sent ;
void loop()
{
   IR.Send(d, 38);//sent the data via 38Kz IR
   delay(1000);
}
```

4.Open the code directly by the path:File -&gt; Example -&gt;IRSendRev-&gt;revTest.

```
//**************
//IR receive demo v1.0
//Connect the IR sent pins to D2 for this demo
//******************************
#include <IRSendRev.h>
//#include <IRSendRevInt.h>

void setup()
{
   Serial.begin(9600);
   IR.Init(2);
   Serial.println("init over");
}

unsigned char dta[20];
 
void loop()
{
   if(IR.IsDta())
   {
      // IR.Recv(dta);
       int length= IR.Recv(dta);
       for (int i =0;i<length;i++)
       {
         Serial.print(dta[i]);
         Serial.print("\t");
       }
       Serial.println();
// Very Important:
// the received data is comprised of the trsmission parameters , please refer to 
// the sendTest.ino in the library ;
   }  
}
```

5.Upload the Code to the receiver Arduino.

6.When the IR Emitter tube faces the IR receiver tube(the distance of emitter to receiver should be less than 10m), then open the Crowtail-IR-Receiver serial port for see information:

![IRresult.jpg](https://wiki.elecrow.com/images/thumb/5/5b/IRresult.jpg/400px-IRresult.jpg){ loading=lazy }

## Resource
--------

- [IRSendRev Program](https://wiki.elecrow.com/images/6/67/IRSendRev.zip)
- [Crowtail- IR Emitter eagle files](https://wiki.elecrow.com/images/f/f0/Crowtail-IR_Emitter_eagle_files.zip)