---
title: 32u4 with A7 GPRS/GSM
---

## Introduction
------------

The 32U4 with A7 GPS+GSM/GPRS Board is based on Mega32U4 and A7 GPS+GSM/GPRS module. It can be used to make a call, send text messages and get GPS positioning. Also it has one analog interface, one IIC interface and two digital interface, which you can connect to other expansion modules. It is very easy for you to make a GPS Tracker by using this board.

**Model: (Discontinued）**
![32U4 with GSM GPS.jpg](https://wiki.elecrow.com/images/thumb/c/cc/32U4_with_GSM_GPS.jpg/600px-32U4_with_GSM_GPS.jpg){ loading=lazy }

## Features
--------

- ATMEGA32U4+A7.
- Work voltage: 3.3V to 5V.
- Operating temperature： -30 ℃ to + 80 ℃.
- Three kinds of interface.
- Equipped with 3.5mm headphone jack.
- 3.7V Battery power supply.
- Standby average current 3ma or less.
- Support the GSM / GPRS Quad-band, including 850,900,1800,1900MHZ.
- Support China Mobile and China Unicom's 2G GSM network worldwide.
- GPRS Class 10.
- Sensitivity &lt; -105.
- Support GPS Positioning.
- Support for voice calls.
- Support for SMS text messaging.
- Support GPRS data business, the maximum data rate: download 85.6Kbps, upload 42.8Kbps.
- Supports standard GSM07.07, 07.05 AT commands and Ai-Thinker extended commands.
- Supports two serial ports, a serial port to download an AT command port.
- Support for Global Positioning System.
- Horizontal positioning accuracy of less than 2.5m.
- AT command supports the standard AT and TCP / IP command interface.
- Support digital audio and analog audio support for HR, FR, EFR, AMR speech coding.
- Support ROHS, FCC, CE, CTA certification.

## Specifications
--------------

- Quad-band: 850/900/1800/1900 MHz.
- GPRS multi-slot: 12, 1 to 12 can be configured.
- GPRS mobile station: Class B.
- Compatible with GSM Phase 2/2 +: Class 4 (2W @ 850/900 MHz) Class 1 (1W @ 1800 / 1900MHz).
- Current consumption: 1.3mA @ DRX = 5; 1.2mA @ DRX = 9.
- AT command control: Standard GSM07.07, 07.05 AT commands and Ai-Thinker extended commands.
- SIM Application Toolkit.
- GPRS Class 10: Up 85.6 kbps (upstream) &amp; 42.8Kbps (downlink).
- Dynamic Conditions Altitude &lt;18,000 meters (60,000 feet).
- Speed &lt;515 m / s (1000 nautical miles), acceleration &lt;4 g.
- PBCCH support.
- Coding scheme: CS 1, 2, 3, 4.
- Support CSD: Up 14.4 kbps.
- Support USSD.
- Stack: PPP / TCP / UDP / HTTP / FTP / SMTP / MUX.
- Dimensions(mm):50.0(L)x36.5(W)x9.6(H)

## Cautions
--------

- <font color="red">Make sure your SIM card is locked.</font>
- <font color="red">This product is supplied as is, without an insulated housing. In high humidity weather, pay special attention to ESD precautions.</font>
- <font color="red">It just supports baud rate 115200bps.</font>

## Interface
---------

![The interface.png](https://wiki.elecrow.com/images/thumb/b/b0/The_interface.png/600px-The_interface.png){ loading=lazy }
![Exampsgdg.jpg](https://wiki.elecrow.com/images/thumb/e/e1/Exampsgdg.jpg/600px-Exampsgdg.jpg){ loading=lazy }

## Usage
-----

1\. Install the antenna.

Two miniature coaxial RF connector is present on the back of the 32U4 with A7 GPRS/GSM/GPS Board to connect with a GSM antenna or a GPS antenna . The connector present on the 32U4 with A7 GPRS/GSM/GPS is called a [U.FL connector](http://en.wikipedia.org/wiki/Hirose_U.FL).The GSM Antenna supplied with the GPRS Shield has an [SMA connector](http://en.wikipedia.org/wiki/SMA_connector) (and not an RP-SMA connector) on it.The connection topology is shown in the diagram below:

![Install the GPS antenna.jpg](https://wiki.elecrow.com/images/thumb/7/7c/Install_the_GPS_antenna.jpg/250px-Install_the_GPS_antenna.jpg){ loading=lazy } 
![Install the GPRS GSM antenna.jpg](https://wiki.elecrow.com/images/thumb/c/c4/Install_the_GPRS_GSM_antenna.jpg/250px-Install_the_GPRS_GSM_antenna.jpg){ loading=lazy }

2\. Insert the Micro SIM card into the SIM card holder.

There is a SIM card holder on the back of the board. Both 1.8 volts and 3.0 volts SIM Cards are supported by this board, the SIM card voltage type is automatically detected.

![Insert the SIM card.jpg](https://wiki.elecrow.com/images/thumb/0/0d/Insert_the_SIM_card.jpg/400px-Insert_the_SIM_card.jpg){ loading=lazy }

3\. Connect the battery.

Because the PC USB port output current is not enough，so you should connedct an 3.7V lithium battery to the battery port.

![Perfect.jpg](https://wiki.elecrow.com/images/thumb/9/9e/Perfect.jpg/400px-Perfect.jpg){ loading=lazy }

4\. Upload the code

Open your Arduino IDE, choose the file, choose the Arduino Leonardo Board.
You can refer to this test code and upload it to your board: [32U4\_with\_A7\_test](./files/32U4-with-A7-test-zip.md)

```
/*
 * Created by Keen
 * Modified by Keen 
 * Date: 11/04/2017
 */
#include<stdio.h>
#include<string.h>
#define DEBUG true
String target_phone = "+861**********6"; // Your phone number, not number of 32U4 with A7/GSM/GPS.

void setup()
{
  Serial.begin(115200);
  Serial1.begin(115200);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(8,OUTPUT);
  digitalWrite(5, HIGH); 
  digitalWrite(4, LOW); 
  digitalWrite(8, LOW); 
  Serial.println("After 2s, test begin!!");
  delay(2000);
  funtion_test();
}

void loop()
{
  if (Serial1.available()>0) {
    Serial.write(Serial1.read());
  }
  if (Serial.available()>0) {
    Serial1.write(Serial.read());
  }
}

void funtion_test(){
   Serial.println("Test begin!!");
   digitalWrite(8, HIGH); 
   delay(3000);       
   digitalWrite(8, LOW); //Power ON..
   Serial.println("A7 Power ON!");
   Serial.println("You may receive the AT   OK"); 
   sendData( "AT",1000,DEBUG);
   delay(500);
   digitalWrite(5, LOW);  //Sleep
   Serial.println("A7 go to sleep now!");
   delay(3000);
   Serial.println("test GPS function");
   testGPS();          //no call, A7 sleeping   
   sendData( "AT",1000,DEBUG);
   delay(500);
   Serial.println("if you receive GPS data,the sleep test failed!");
   digitalWrite(5, HIGH);   // wake up
   delay(1000);
   Serial.println("A7 WAKE UP!"); 
   Serial.println("test whether wake up or not, if OK, A7 wake up"); 
   sendData( "AT",1000,DEBUG);
   delay(500);     
   digitalWrite(4, HIGH); // power off A6
   Serial.println("A7 power off!");
   delay(3000);
   digitalWrite(4, LOW);
   Serial.println("print AT and you not receive OK"); 
   sendData( "AT",1000,DEBUG);
   delay(500); 
   Serial.println("A7 not Respond"); 
   digitalWrite(8, HIGH);           //POWER UP
   delay(3000);       
   digitalWrite(8, LOW);
   delay(3000);
   Serial.println("A7 Power ON!"); 
   Serial.println("................................."); 
   sendData( "AT",1000,DEBUG); //
   delay(1000);
   Serial.println("The funtion is Get GPS..."); 
   testGPS();
   Serial.println("The funtion is Dial Voice Call..."); 
   delay(1000);
   DialVoiceCall();
   Serial.println("The funtion is Send SMS ..."); 
   delay(1000);
   SendTextMessage();
   Serial.println("This function is submit a HTTP request...");
   delay(1000);
   TCP_GPRS();
   Serial.println("All the test of 32U4 with A7 is complete!");
}

void testGPS(void){
  sendData("AT+GPS=1",1000,DEBUG);     
  sendData("AT+GPSRD=1",3000,DEBUG);
  sendData("AT+GPS=0",10000,DEBUG);
}

void TCP_GPRS(){
   sendData("AT+CREG?",5000,DEBUG); //Query network registration
   delay(100);
   sendData("AT+CGATT=1",5000,DEBUG);
   delay(100); 
   sendData("AT+CGDCONT=1,\"IP\",\"CMNET\"",2000,DEBUG);//setting PDP parameter 
   delay(100); 
   sendData("AT+CGACT=1,1",10000,DEBUG); //Activate PDP, open Internet service
   delay(100);  
   sendData("AT+CIPSTART=\"TCP\",\"www.baidu.com\",80",10000,DEBUG);
   delay(100);
   sendData("AT+CIPSEND=5,\"12345\"",2000,DEBUG); //Send string "12345" 
   delay(100); 
   sendData("AT+CIPCLOSE",2000,DEBUG);     //Close TCP
   delay(100); 
   /*
     sendData("AT+CREG?",3000,DEBUG);     
     sendData("AT+CGATT=1",1000,DEBUG);
     sendData("AT+CGDCONT=1,\"IP\",\"CMNET\"",1000,DEBUG);
     sendData("AT+CGACT=1,1",1000,DEBUG);
     sendData("AT+CIPSTART=\"TCP\",\"google.com\",80",3000,DEBUG);
     sendData("AT+CIPSEND=80",1000,DEBUG);
     sendData("GET http://www.google.com HTTP/1.0\r\n",100,DEBUG);
     */
}

void SendTextMessage()
{ 
  sendData("",2000,DEBUG);
  sendData("AT+CMGF=1",2000,DEBUG);//Because we want to send the SMS in text mode
  delay(100);
  sendData("AT+CMGS="+target_phone,2000,DEBUG);//send sms message, be careful need to add a country code before the cellphone number
  delay(100);
  sendData("GSM test message!",2000,DEBUG);//the content of the message
  delay(100);
  Serial1.println((char)26);//the ASCII code of the ctrl+z is 26
  delay(100);
}

void DialVoiceCall()
{
   sendData("AT+SNFS=0",5000,DEBUG);
   delay(100);
   sendData("ATD"+target_phone,5000,DEBUG);// "ATD+86137xxxxxxxx"dial the number
   delay(100);
}


String sendData(String command, const int timeout, boolean debug)
{
    String response = "";    
    Serial1.println(command); 
    long int time = millis();
    while( (time+timeout) > millis())
    {
      while(Serial1.available())
      {       
        char c = Serial1.read(); 
        response+=c;
      }  
    }    
    if(debug)
    {
      Serial.print(response);
    }    
    return response;
}

void httpRec(const int timeout){
    String response = "";    
    long int time = millis();
    while( (time+timeout) > millis())
    {
      while(Serial1.available())
      {       
        char c = Serial1.read(); 
        response+=c;
      }  
    }    
    Serial.print(response); 
}


```

After you complete download the code, open the Serial monitor, you will see some information as bellow:

![Choose the Board.png](https://wiki.elecrow.com/images/thumb/9/9e/Choose_the_Board.png/400px-Choose_the_Board.png){ loading=lazy }
![32U4 with A7 test.png](https://wiki.elecrow.com/images/thumb/0/0d/32U4_with_A7_test.png/400px-32U4_with_A7_test.png){ loading=lazy }

## Get and send the location information to your phone by SMS
----------------------------------------------------------

This example is how to get the GPS location information and send it to your cellphone.In the code,we need to change the target phone. And the Lithium Batteries must be used. When the board gets the 30 times location information successfully and the information will be send by SMS.

```
/*
 * Created by Keen
 * Modified by Keen 
 * Date: 15/07/2017
 * Please note:
 * 1.You need to change the "target_phone". 
 * 2.Lithium batteries must be used.
 * 3.The GPS and GSM antenna must be used.
 * Please open your "Serial Monitor" and you will get the debug information. 
 */
#define DEBUG true

char byteGPS=-1;
char linea[300] = "";
char comandoGPR[7] = "$GPRMC";
int cont=0;
int bien=0;
int conta=0;
int indices[13];

int GPS_time=30;                        // When the board gets the 30 times location information successfully and the location information will be send by sms.      
String target_phone = "+861************6"; // Your phone number,be careful need to add a country code before the cellphone number

String GPS_position="";
int GPS_position_count=0;

void setup()
{
  Serial.begin(115200);
  Serial1.begin(115200);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(8,OUTPUT);
  digitalWrite(5, HIGH); 
  digitalWrite(4, LOW); 
  digitalWrite(8, LOW); 
  delay(2000);
  digitalWrite(8, HIGH); 
  delay(3000);       
  digitalWrite(8, LOW);
  Serial.println("A7 Power ON!");
  sendData("AT+GPS=0",3000,DEBUG);     //Close GPS
  for(int i=0;i<2;i++){                //Make sure the GPS has been turned on
    sendData("AT+GPSRD=1",1000,DEBUG);
    Serial1.println("AT+GPS=1");
  }
  Serial.println("*********************************************************");
  Serial.println("**If don`t display 'GPS positioning....',please reboot.**");
  Serial.println("*********************************************************");
}

void loop()
{
    testgps();
}

void testgps(){
  while(Serial1.available()){
   byteGPS=Serial1.read();  
  // Read a byte of the serial port
   if (byteGPS == -1) {       
    // See if the port is empty yet
   } 
   else {
     // note: there is a potential buffer overflow here!
     linea[conta]=byteGPS;        // If there is serial port data, it is put in the buffer
     conta++;                      
     //Serial.print(byteGPS);    //If you delete '//', you will get the all GPS information
     if (byteGPS==13){
      // If the received byte is = to 13, end of transmission
      // note: the actual end of transmission is <CR><LF> (i.e. 0x13 0x10)
      cont=0;
      bien=0;
      // The following for loop starts at 1, because this code is clowny and the first byte is the <LF> (0x10) from the previous transmission.
       for (int i=1;i<7;i++){     // Verifies if the received command starts with $GPR
         if (linea[i]==comandoGPR[i-1]){
           bien++;
         }
       }
       if(bien==6){ 
        // If yes, continue and process the data
        //Data Partitioning
         for (int i=0;i<300;i++){
           if (linea[i]==','){    // check for the position of the  "," separator
             // note: again, there is a potential buffer overflow here!
             indices[cont]=i;
             cont++;
           }
           if (linea[i]=='*'){    // ... and the "*"
             indices[12]=i;
             cont++;
           }
         }
         //panel data, for example:Direction (E/W):Longitude-Direction(N/S):Latitude<--->E:11350.51872-N:2236.40687        
         for(int i=5;i>1;i--){
           for (int j=indices[i];j<(indices[i+1]-1);j++){
             GPS_position+=linea[j+1];
           }
           if((i==5)||(i==3)){
             GPS_position+=":";  
           }else if(i==4){
             GPS_position+="-";   
           }
         }
         //If the return ":-:", it means empty data, continue positioning 
         if(GPS_position==":-:"){
          Serial.println("GPS positioning....");
         }else{
            Serial.println(GPS_position);
            GPS_position_count++;
            //When GPS_position_count is equivalent to GPS_time, stop positioning and start to send sms messages
            if(GPS_position_count==GPS_time){
            GPS_position_count=0;          //Reset count
            sendData("AT+GPS=0",1000,DEBUG);
            delay(1000); 
            SendTextMessage(GPS_position);
            sendData("AT+GPS=1",1000,DEBUG); 
           }
                  
         }
       }
       GPS_position="";
       conta=0;                    // Reset the buffer
       for (int i=0;i<300;i++){    //  
       linea[i]=' ';             
       }                
     }
   }  
   }
}

void SendTextMessage(String message)
{ 
  sendData("AT+CMGF=1",5000,DEBUG);            //Set the SMS in text mode
  delay(100);
  sendData("AT+CMGS="+target_phone,2000,DEBUG);//send sms message to the cellphone , be careful need to add a country code before the cellphone number
  delay(100);
  sendData(message,2000,DEBUG);                //the content of the message
  delay(100);
  Serial1.println((char)26);                  //the ASCII code of the ctrl+z is 26
  delay(100);
  sendData("",1000,DEBUG);                     //Clear serial data
  delay(100);
}

void sendData(String command, const int timeout, boolean debug)
{
    String response = "";    
    Serial1.println(command); 
    long int time = millis();   
    while( (time+timeout) > millis()){
      while(Serial1.available()){       
        response += (char)Serial1.read(); 
      }  
    }    
    if(debug){
      Serial.print(response);
    }    
}

```

## Resource
--------

- [32u4 with A7 GPRS/GSM+GPS eagle file](./files/32u4-with-A7-GPRS-GSM-GPS-eagle-file-zip.md)
- [A7\_(GSM+GPRS+GPS+AGPS)\_module\_Hardware\_introduction](./files/A7-(GSM%2BGPS%2BGPRS%2BGPRS)-module-Hardware-introduction-pdf.md)