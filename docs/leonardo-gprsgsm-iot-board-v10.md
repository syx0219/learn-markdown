---
title: Leonardo GPRS/GSM IOT Board v1.0
---

## Description
-----------

The Leonardo GPRS/GSM IOT Board to provide your project a way of convenient remote control, It’s widely used in remote control, telemetry, communication, automatic control and so on. It can receive phone calls and text message to control the relay ON or OFF. What more, this boards have four relay so that it can control several appliances at the same time.

Meanwhile, this boards serves as the main control system applied to smart home. Not only that, it has a mobile phone card that used to realize the idea of furniture anywhere and anytime easily. It can also be used an Arduino/Crowduino to realize the operation of other modules.

**Model: [WCW07517B](https://www.elecrow.com/leonardo-gprs-gsm-iot-board.html)**  
![Leonardo.jpg](https://wiki.elecrow.com/images/thumb/0/0b/Leonardo.jpg/400px-Leonardo.jpg){ loading=lazy }

## Features
-----------

- GPRS/GSM function
- Standard Micro SIM Card
- Power Interface：USB,DC
- Working Frequency: 16MHz
- Compliant to GSM phase 2/2+
- Supports 3.0V to 5.0V logic level
- Microcontroller: ATmega32u4,8-bit AVR MCU
- Low power consumption, 1mA in sleep mode
- Supports load: DC/AD maximum current:2A AC:100~240V
- Controlled by AT Command (3GPP TS 27.007, 27.005 and SIMCOM enhanced AT Commands).
- Quad-Band 850 / 900/ 1800 / 1900 MHz - would work on GSM networks in all countries across the world.
- Class 4 (2 W @ 850 / 900 MHz)
- Class 1 (1 W @ 1800 / 1900MHz)

## Specifications
-----------
<table border="1" cellspacing="0" width="100%">
  <tbody>
    <tr>
      <th scope="col" align="center"> Item</th>
      <th scope="col" align="center"> Min</th>
      <th scope="col" align="center"> Typical</th>
      <th scope="col" align="center"> Max</th>
      <th scope="col" align="center"> Unit</th>
    </tr>
    <tr>
      <th scope="row"> USB</th>
      <td align="center">5</td>
      <td align="center">5</td>
      <td align="center">5</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row"> External power</th>
      <td align="center">7</td>
      <td align="center">-</td>
      <td align="center">12</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row"> Current</th>
      <td align="center">40</td>
      <td align="center">40</td>
      <td align="center">40</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row"> Dimensions(with antenna)</th>
      <td align="center" colspan="3"> 107.0 x 65.0 x 24.0</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row"> Temperature</th>
      <td align="center" colspan="3">-30~+85</td>
      <td align="center">°C</td>
    </tr>
  </tbody>
</table>

## Interface Function
-----------

![Leonardo GPRS GSM IOT Board-V1.1.png](https://wiki.elecrow.com/images/thumb/9/99/Leonardo_GPRS_GSM_IOT_Board-V1.1.png/900px-Leonardo_GPRS_GSM_IOT_Board-V1.1.png){ loading=lazy }

**Net Status** - tell the status about SIM808 linking to the net  
**Antenna** - connected to external antenna  
**External Power** - Vin connected to external 5~9VDC power supply  
**USB Power** - connected to computer and power supply  
**ISP** - Burn bootloader  
**Rst Key** - Restart system  
**Power key** - power up and down for SIM808 **Power Status** - tell whether sys power  
**Work Status** - tell whether the power of SIM808 is on  
**Relay1-4** - relay channel,normall off  

## Cautions
-----------

Make sure your SIM card is unlocked.The product is provided as is without an insulating enclosure. Please observe ESD precautions specially in dry (low humidity) weather.

## Hardware installtion
-----------

1.Insert an Micro SIM card to SIM Card Holder 6 Pin Holder for SIM Cards. Both 1.8 volts and 3.0 volts SIM Cards are supported by SIM808 - the SIM card voltage type is automatically detected.

![Card.jpg](https://wiki.elecrow.com/images/thumb/f/fe/Card.jpg/400px-Card.jpg){ loading=lazy }

2.Make sure the antenna pad buckled properly - A miniature coaxial RF connector is present on the GPRS Shield board to connect with a GSM Antenna. The connector present on the GPRS Shield is called a U.FL connecto. The GSM Antenna supplied with the GPRS Shield has an SMA connector (and not an RP-SMA connector) on it. A patch cord is also supplied with the GPRS Shield to interface the antenna to the board. The connection topology is shown in the diagram below:Auto power on but if cannot open and that you can open it manual opration below this picture

![Connect antenna.jpg](https://wiki.elecrow.com/images/thumb/8/84/Connect_antenna.jpg/400px-Connect_antenna.jpg){ loading=lazy }

3.Upload the following code.

[File:SMS control relay.zip](./files/SMS-control-relay-zip.md)

```
/*
 * Author: Elecrow Keen
 * Date:6/30/2017
 * IDE V1.8.2 
 * Email:keen@elecrow.com    
 * Function: SMS control relay
 * Please note:
    When the the board receive "R1O" by SMS, the relay 1 will be open and the "R1C" that it will be close. 
    
    "R1O"/""R1C" means:
      R ->  Relay
      1 ->  Relay 1 
      O ->  Open
      C ->  Close
      
    It also used Relay2,Relay3 and Relay4.
 */

#define DEBUG true    //Open the debug information 

 // the number of the Relay pin
const int Relay1 = 3;
const int Relay2 = 2;
const int Relay3 = 4;
const int Relay4 = 5;
/*
R1O means open  relay 1
R1C means close relay 1
The same as others 
*/
String R1O = "R1O";
String R1C = "R1C";
String R2O = "R2O";
String R2C = "R2C";
String R3O = "R3O";
String R3C = "R3C";
String R4O = "R4O";
String R4C = "R4C";

char target[] ="+CMTI";  
int sms_no;
String get_message = "";   

void setup() {  
      Serial.begin(19200); 
      Serial1.begin(19200); 
      for(int i=2;i<6;i++){ // initialize the Relay pins as an output:
        pinMode(i,OUTPUT);
      }
      for(int i=2;i<6;i++){// initialize the Relay pins status:
        digitalWrite(i,LOW);
      }
      //Power on the SIM800C
      pinMode(9,OUTPUT);
      digitalWrite(9,HIGH);
      delay(3000);
      digitalWrite(9,LOW);
      delay(1000);
      sendData("AT",2000,DEBUG);
      sendData("AT+CMGF=1",1000,DEBUG);        //Set the SMS in text mode
} 

void loop() { 
       if(Serial1.available()>0){    
          if(Serial1.find(target)){                  //If receive a new SMS
             sms_no = Serial1.parseInt();            //Get the SMS ID        
             get_message = "AT+CMGR="+(String)sms_no; //The command of the content of the SMS
             Serial.println("******************** Print the relay status *********************" );
             Data_handling(get_message,500,DEBUG);    //Get the content of the SMS 
             Serial.println("*****************************END*********************************" );
         } 
     }
     while(Serial1.read() >= 0){}                     // Clear serial buffer   
}

void Data_handling(String command, const int timeout, boolean debug)  //data handling function
{
    String response = "";    
    Serial1.println(command); 
    long int time = millis();
    while( (time+timeout) > millis()){
      while(Serial1.available()){       
        response += (char)Serial1.read(); 
      }  
    }    
   if (response.indexOf(R1O)>=0) {
    digitalWrite(Relay1,HIGH);
    if(debug){
    Serial.println("Open Relay 1");
    }
    }
   else if (response.indexOf(R1C)>=0) {
    digitalWrite(Relay1,LOW);
    if(debug){
    Serial.println("Close Relay 1");
    }
   }
   else if(response.indexOf(R2O)>=0) {
    digitalWrite(Relay2,HIGH);
    if(debug){
    Serial.println("Open Relay 2");
    }
   }
   else if(response.indexOf(R2C)>=0) {
    digitalWrite(Relay2,LOW);
    if(debug){
    Serial.println("Close Relay 2");
    }
   }
   else if (response.indexOf(R3O)>=0) {
    digitalWrite(Relay3,HIGH);
    if(debug){
    Serial.println("Open Relay 3");
    }
   }
   else if(response.indexOf(R3C)>=0) {
    digitalWrite(Relay3,LOW);
    if(debug){
    Serial.println("Close Relay 3");
    }
   }
   else if(response.indexOf(R4O)>=0) {
    digitalWrite(Relay4,HIGH);
    if(debug){
    Serial.println("Open Relay 4");
    }
   }
   else if(response.indexOf(R4C)>=0) {
    digitalWrite(Relay4,LOW);
    if(debug){
    Serial.println("Close Relay 4");
    }
   }else
   Serial.println("....Error message....");
}

void sendData(String command, const int timeout, boolean debug)  //Send command function
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

![Download.jpg](https://wiki.elecrow.com/images/thumb/6/65/Download.jpg/400px-Download.jpg){ loading=lazy }

4.Power supply for GPRS shield - Select power source with the switch on board, you can select the 5V power supply from arduino or exteral power.Select the 5V source from Arduino as the following picture:

5.Turn on the GSM/GPRS Board Turn on through Hardware. Press the the 'POWERKEY' for few seconds until Power-on indicator(Green) is on

![Workon.jpg](https://wiki.elecrow.com/images/thumb/4/48/Workon.jpg/400px-Workon.jpg){ loading=lazy }

6.Running the Sketches In each serial monitor window, you can see a ‘s’ and then Send a text message to the test card; if the light turn on that it normally. For example, you can send ‘R1O’ to this than first light turn on and send ‘R1C’ to it then turn off.

![Success.jpg](https://wiki.elecrow.com/images/thumb/7/70/Success.jpg/400px-Success.jpg){ loading=lazy }

## Debug through computer
-----------

## Resource
-----------

[File:Leonardo.zip](https://wiki.elecrow.com/images/8/8e/Leonardo.zip)