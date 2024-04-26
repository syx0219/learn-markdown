---
title: Elecrow SIMduino UNO+SIM808 GPRS/GSM Board
---

## Description
-----------

The Elecrow Simduino combines Arduino uno and sim808 module. It will save more cost and space for your project and easier to build other modules. It not only by DC power supply, we have designed a battery interface for it, you can also use a 3.7V lithium battery to power it. Whether you want to get a Arduino or a SIM808 module, even start a SIM808 related application that base on Arduino. It will make your satisfaction. Come on and add it to your shopping cart.

Same as the Arduino UNO, the SIMduino also has 14 digital input/output pins (of which 6 can be used as PWM outputs), 6 analog inputs, a 16 MHz ceramic resonator, a USB connection, a power jack, an ICSP header, a reset button, and of course a Mini USB cable, simply connect it to a computer with a USB cable or power it with a AC-to-DC adapter or battery to get started.

**Model: [ACM12425E](http://www.elecrow.com/elecrow-simduino-unosim808-gprsgsm-board-p-1607.html)**

![Simduinodd fem.JPG](https://wiki.elecrow.com/images/thumb/f/fa/Simduinodd_fem.JPG/600px-Simduinodd_fem.JPG){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/elecrow-simduino-unosim808-gprsgsm-board-p-1607.html?wiki "Title text")


## Summary
-------

| **Microcontroller** | **ATmega328** |
|:-:|:-:|
| Operating Voltage | 5v |
| Input Voltage (recommended) | 3.3-5V |
| Input Voltage (limits) | &lt; 5V |
| Digital I/O Pins | 14 (of which 6PINs provide PWM output) |
| Analog Input Pins | 8 |
| DC Current per I/O Pin | 40mA |
| DC Current for 3.3V Pin | 50 mA |
| Flash Memory | 32 KB (ATmega328) of which 0.5 KB used by bootloader |
| SRAM | 2 KB (ATmega328) |
| EEPROM | 1 KB (ATmega328) |
| Clock Speed | 16 MHz |

## Features
--------

- UNO+SIM808,TWO in one board;
- Flat DC Jack.
- Inherits all of Arduino Uno's features.
- Compatible to Uno's pin layout, screw hole and dimensions.
- Evolved with SMD components.
- Quad-band 850/900/1800/1900MHz
- GPRS mobile station class B
- Controlled by AT Command (3GPP TS 27.007, 27.005 and SIMCOM enhanced AT Commands)
- Integrated GPS/CNSS and supports A-GPS
- Low power consumption, 1mA in sleep mode
- Supports GPS NMEA protocol
- Standard Micro SIM Card
- GPRS multi-slot class12 connectivity: max. 85.6kbps(down-load/up-load)
- Indicator LEDs for power and network connectivity
- uFL connection for external passive GPS &amp; external GSM antenna
- Any standard 2G SIM slides into a secure connector
- Standard 4-pole TRRS headphone jack. Use any 'Android' or 'iPhone'-compatible headset with mic
- Dimensions(mm):70.0(L)x55.0(W)x14.0(H)

## Interface Function
------------------

### **Connectors**

JST 2-PIN: This is the battery input connector.(3.3-5V)    
MiniUSB connector:Arduino IDE Programming port.    
Headset jack:This is a 'standard' TRRS 3.5mm phone headset jack with stereo earphone and mono microphone.

### **Antenna ports**

There is two antenna inferface in the board,"GSM" where you can plug your GSM antennea and "GPS" connect the GPS antenna.

### **SIM Connector (on Back)**

A 2G Micro SIM card is required to use the module. Nearly any cell phone shop can sell you a SIM card. It must be a 2G GSM card. AT&amp;T in the US does not sell these anymore!

### **LEDs**

PWR:RED   
NET:Orange!You can use this for checking the current state without sending an AT command:   
\--64ms on, 800ms off - the module is running but hasn't made connection to the cellular network yet   
\--64ms on, 3 seconds off - the module has made contact with the cellular network and can send/receive voice and SMS    
\--64ms on, 300ms off - the GPRS data connection you requested is active   
\--By watching the blinks you can get a visual feedback on whats going on    
STA：Blue!Lit when the SIM808 module is booted and running.

## The Usage of UNO
----------------

The usage of SIMduino is same as the Arduino UNO:

## The Usage of SIM808
-------------------

### **Attaching Antenna**

GPS antenna and GSM antenna is required!   
![SIM808 Antenna.jpg](https://wiki.elecrow.com/images/thumb/9/92/SIM808_Antenna.jpg/500px-SIM808_Antenna.jpg){ loading=lazy }

### **SIM Card**

You must insert a SIM card to do anything but the most basic tests. GPS does work without a SIM but of course you cannot send or receive texts, calls, etc!   
The SIM card holder is on the back. It holds a very-standard "Micro SIM",Mini SIMs will not work! Make sure you get a "Micro SIM".   
![SIM808 SIMddd card.jpg](https://wiki.elecrow.com/images/0/0b/SIM808_SIMddd_card.jpg){ loading=lazy }

### **Connect the USB and DC power**

Due to the SIM808 power up need more than 2.5A current, you need to connect a DC power to it.   
![Usb connect.jpg](https://wiki.elecrow.com/images/thumb/5/5d/Usb_connect.jpg/500px-Usb_connect.jpg){ loading=lazy }

### **Power the SIM808**

Press the KEY more than 3S, the STA LED will light up and the NET LED will blink.    
![Power sim808.jpg](https://wiki.elecrow.com/images/thumb/8/8f/Power_sim808.jpg/500px-Power_sim808.jpg){ loading=lazy }

## Arduino Test
------------

#### **Making a call: using Software UART**

1.Copy the demo code as bellow and paste it in the IDE.   
![SIM808 Picture12.jpg](https://wiki.elecrow.com/images/3/3a/SIM808_Picture12.jpg){ loading=lazy }

2.Upload to your Arduino wired up to the moduleOnce uploaded to your Arduino, open up the serial console at 115200 baud speed to begin the tester sketch.

```
#include <SoftwareSerial.h>
SoftwareSerial mySerial(7, 8);
void setup()
{
mySerial.begin(19200);               // the GPRS baud rate   
Serial.begin(19200);               // the GPRS baud rate   
delay(2000);
mySerial.println("ATDxxxxxxxxx;"); // xxxxxxxxx is the number you want to dial.  

if(mySerial.available())

Serial.print((unsigned char)mySerial.read());


delay(10000); 
delay(10000); 

mySerial.println("ATH"); //End the call.
if(mySerial.available())

Serial.print((unsigned char)mySerial.read());
}


void loop()
{
//Do nothing
}
```

### **Sending SMS: using Software UART**

```


#include <SoftwareSerial.h>

SoftwareSerial mySerial(7, 8);

void setup()
{
mySerial.begin(19200);  //Default serial port setting for the GPRS modem is 19200bps 8-N-1
mySerial.print("\r");
delay(1000);                    //Wait for a second while the modem sends an "OK"
mySerial.print("AT+CMGF=1\r");    //Because we want to send the SMS in text mode
delay(1000);

//mySerial.print("AT+CSCA=\"+919032055002\"\r");  //Setting for the SMS Message center number,  
//delay(1000);                                  //uncomment only if required and replace with
//the message center number obtained from
//your GSM service provider.
//Note that when specifying a tring of characters
// " is entered as \"

mySerial.print("AT+CMGS=\"+9184460xxxx\"\r");    //Start accepting the text for the message
//to be sent to the number specified.
//Replace this number with the target mobile number.
delay(1000);
mySerial.print("Hello,Elecrow!\r");   //The text for the message
delay(1000);
mySerial.write(0x1A);  //Equivalent to sending Ctrl+Z 
}

void loop()
{
//We just want to send the SMS only once, so there is nothing in this loop.
//If we put the code for SMS here, it will be sent again and again and cost us a lot.
}
```

### **Using Sms to Control an LED Status**

This example is controbuted by MChobby, for more information please visit: [https://wiki.mchobby.be/index.php?title=SmsCommand](https://wiki.mchobby.be/index.php?title=SmsCommand)

Send a SMS message "on" or "off" from your cellphone to the GPRS Shield to control the Digital Pin 13(LED) Status.

- <font color="red">The default Buffer of Rx in SoftwareSerial.h is 32/64, you may experience some data lose while the returns of SIM808 are many(Receiving SMS/TCPIP), you can try to change the Buffer of Rx in SoftwareSerial.h into

**\#define \_SS\_MAX\_RX\_BUFF** *128* // RX buffer size</font>

```


#include <SoftwareSerial.h>
 
SoftwareSerial mySerial(7, 8);
 
// EN: String buffer for the GPRS shield message

String msg = String("");
// EN: Set to 1 when the next GPRS shield message will contains the SMS message

int SmsContentFlag = 0;
 
// EN: Pin of the LED to turn ON and OFF depending on the received message

int ledPin = 13;
 
// EN: Code PIN of the SIM card (if applied)

//String SIM_PIN_CODE = String( "XXXX" );
 
void setup()
{
  mySerial.begin(19200);               // the GPRS baud rate   
  Serial.begin(19200);                 // the GPRS baud rate
 
  // Initialize la PIN
  pinMode( ledPin, OUTPUT ); 
  digitalWrite( ledPin, LOW ); 
}
 
void loop()
{
    char SerialInByte;
 
    if(Serial.available())
    {
       mySerial.print((unsigned char)Serial.read());
     }  
    else  if(mySerial.available())
    {
        char SerialInByte;
        SerialInByte = (unsigned char)mySerial.read();
 
        // EN: Relay to Arduino IDE Monitor
   
        Serial.print( SerialInByte );
 
        // -------------------------------------------------------------------
        // EN: Program also listen to the GPRS shield message.
   
        // -------------------------------------------------------------------
 
        // EN: If the message ends with <CR> then process the message
       
        if( SerialInByte == 13 ){
          // EN: Store the char into the message buffer
        
          ProcessGprsMsg();
         }
         if( SerialInByte == 10 ){
            // EN: Skip Line feed

         }
         else {
           // EN: store the current character in the message string buffer
 
           msg += String(SerialInByte);
         }
     }   
}
 
// EN: Make action based on the content of the SMS. 
//     Notice than SMS content is the result of the processing of several GPRS shield messages.

void ProcessSms( String sms ){
  Serial.print( "ProcessSms for [" );
  Serial.print( sms );
  Serial.println( "]" );
 
  if( sms.indexOf("on") >= 0 ){
    digitalWrite( ledPin, HIGH );
    Serial.println( "LED IS ON" );
    return;
  }
  if( sms.indexOf("off") >= 0 ){
    digitalWrite( ledPin, LOW );
    Serial.println( "LED IS OFF" );
    return;
  }
}
 
// EN: Send the SIM PIN Code to the GPRS shield

//void GprsSendPinCode(){
//  if( SIM_PIN_CODE.indexOf("XXXX")>=0 ){
//    Serial.println( "*** OUPS! you did not have provided a PIN CODE for your SIM CARD. ***" );
//    Serial.println( "*** Please, define the SIM_PIN_CODE variable . ***" );
//    return;
// }
//  mySerial.print("AT+CPIN=");
// mySerial.println( SIM_PIN_CODE );
}
 
// EN: Request Text Mode for SMS messaging

void GprsTextModeSMS(){
  mySerial.println( "AT+CMGF=1" );
}
 
void GprsReadSmsStore( String SmsStorePos ){
  // Serial.print( "GprsReadSmsStore for storePos " );
  // Serial.println( SmsStorePos ); 
  mySerial.print( "AT+CMGR=" );
  mySerial.println( SmsStorePos );
}
 
// EN: Clear the GPRS shield message buffer

void ClearGprsMsg(){
  msg = "";
}
 
// EN: interpret the GPRS shield message and act appropiately

void ProcessGprsMsg() {
  Serial.println("");
  Serial.print( "GPRS Message: [" );
  Serial.print( msg );
  Serial.println( "]" );
 
//  if( msg.indexOf( "+CPIN: SIM PIN" ) >= 0 ){
//     Serial.println( "*** NEED FOR SIM PIN CODE ***" );
 //    Serial.println( "PIN CODE *** WILL BE SEND NOW" );
 //    GprsSendPinCode();
//  }
 
  if( msg.indexOf( "Call Ready" ) >= 0 ){
     Serial.println( "*** GPRS Shield registered on Mobile Network ***" );
     GprsTextModeSMS();
  }
 
  // EN: unsolicited message received when getting a SMS message
  // FR: Message non sollicité quand un SMS arrive
  if( msg.indexOf( "+CMTI" ) >= 0 ){
     Serial.println( "*** SMS Received ***" );
     // EN: Look for the coma in the full message (+CMTI: "SM",6)
     //     In the sample, the SMS is stored at position 6
     int iPos = msg.indexOf( "," );
     String SmsStorePos = msg.substring( iPos+1 );
     Serial.print( "SMS stored at " );
     Serial.println( SmsStorePos );
 
     // EN: Ask to read the SMS store
     GprsReadSmsStore( SmsStorePos );
  }
 
  // EN: SMS store readed through UART (result of GprsReadSmsStore request)  
  if( msg.indexOf( "+CMGR:" ) >= 0 ){
    // EN: Next message will contains the BODY of SMS
    SmsContentFlag = 1;
    // EN: Following lines are essentiel to not clear the flag!
    ClearGprsMsg();
    return;
  }
 
  // EN: +CMGR message just before indicate that the following GRPS Shield message 
  //     (this message) will contains the SMS body

  if( SmsContentFlag == 1 ){
    Serial.println( "*** SMS MESSAGE CONTENT ***" );
    Serial.println( msg );
    Serial.println( "*** END OF SMS MESSAGE ***" );
    ProcessSms( msg );
  }
 
  ClearGprsMsg();
  // EN: Always clear the flag

  SmsContentFlag = 0; 
}
```

## The usage of GPS Function
-------------------------

### **Print the GPS(GNSS) data with serial port**

### **AT Commands Examples**

Demo code of get the GPS information:

```
#include <SoftwareSerial.h>
#include<stdio.h>
#include<string.h>
#define DEBUG true


SoftwareSerial mySerial(7,8); 
        
void setup()
{
  Serial.begin(9600);
 mySerial.begin(9600); 
}

void loop()
{
   getgps();
   while(1)
   {
        sendData( "AT+CGNSINF",1000,DEBUG);   
        delay(1000);
        
   }
 
}
void getgps(void)
{
   sendData( "AT+CGNSPWR=1",1000,DEBUG); 
   sendData( "AT+CGNSSEQ=RMC",1000,DEBUG); 
}


String sendData(String command, const int timeout, boolean debug)
{
    String response = "";    
    mySerial.println(command); 
    long int time = millis();   
    while( (time+timeout) > millis())
    {
      while(mySerial.available())
      {       
        char c = mySerial.read(); 
        response+=c;
      }  
    }    
    if(debug)
    {
      Serial.print(response);
    }    
    return response;
}

```

The result of get the GPS information.

![SIM808 GPRS GSM GPS Shield v1.1 GNSS code.jpg](https://wiki.elecrow.com/images/thumb/6/63/SIM808_GPRS_GSM_GPS_Shield_v1.1_GNSS_code.jpg/500px-SIM808_GPRS_GSM_GPS_Shield_v1.1_GNSS_code.jpg){ loading=lazy }

## Resources
---------

[Elecrow Simduino v2.2 eagle file.zip](https://wiki.elecrow.com/images/2/2d/Elecrow_Simduino_v2.2_eagle_file.zip)

## Support
-------

If you have any problem about how to use it, you can connect to us at [the bottom-right of bazzer](http://www.elecrow.com/) or contact to **techsupport@elecrow.com** to get technology support.