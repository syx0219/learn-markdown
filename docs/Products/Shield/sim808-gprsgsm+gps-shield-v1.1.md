---
title: SIM808 GPRS/GSM+GPS Shield v1.1
---

## Introduction

SIM808 module is a GSM/GPS/BT three-in-one function module. It is based on the latest GSM/GPS/BT module SIM808 from SIMCOM, supports GSM/GPRS Quad-Band network and combines GPS technology for satellite navigation.It has high GPS receive sensitivity with 22 tracking and 66 acquisition receiver channels. Besides, it supports A-GPS that available for indoor localization， and it also supports for Bluetooth 3.0.

The module is controlled by AT command via UART and supports 3.3V and 5V logical level.

**Model: [ACS80801S](http://www.elecrow.com/sim808-gprsgsmgps-shield-p-1389.html)**  
![GPRS+GSM+GPS Shield.jpg](https://wiki.elecrow.com/images/thumb/f/fc/GPRS%2BGSM%2BGPS_Shield.jpg/500px-GPRS%2BGSM%2BGPS_Shield.jpg){ loading=lazy }
[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/sim808-gprsgsmgps-shield-p-1389.html?wiki)

## Features

- Quad-band 850/900/1800/1900MHz.
- GPRS multi-slot class12 connectivity: max. 85.6kbps(down-load/up-load).
- GPRS mobile station class B.
- Controlled by AT Command (3GPP TS 27.007, 27.005 and SIMCOM enhanced AT Commands).
- Supports Real Time Clock.
- Supply voltage range 5V ~ 12V.
- Supports for Bluetooth 4.0.
- Integrated GPS/CNSS and supports A-GPS.
- Supports 3.0V to 5.0V logic level.
- Low power consumption, 1mA in sleep mode.
- Supports GPS NMEA protocol.
- Standard Micro SIM Card.

## Application Ideas

- M2M (Machine 2 Machine) Applicatoions - To transfer control data using SMS or GPRS between two machines located at two different factories.
- Remote control of appliances - Send SMS while you are at your office to turn on or off your washing machine at home.
- Remote Weather station or a Wireless Sensor Network - Make it with [Crowduino v1.0|Crowduino v1.0] and create a sensor node capable of transferring sensor data (like from a weather station - temperature, humidity etc.) to a web server (like [pachube.com](http://www.pachube.com/)).
- Vehicle Tracking System - Install GPRS+GSM+GPS Shield in your car and publish your location live on the internet. Can be used as a automotive burglar alarm.

## Cautions

- <font color="red">Make sure your SIM card is unlocked.</font>
- <font color="red">The product is provided as is without an insulating enclosure. Please observe ESD precautions specially in dry (low humidity) weather.</font>
- <font color="red">The factory default setting for the GPRS Shield UART is autobaoding. It supports baud rate from 1200 bps to 115200bps. (Can be changed using AT commands).</font>

## Specifications

<table border="1" cellspacing="0" width="70%">
  <tbody>
    <tr>
      <th scope="col" style="width: 30%" align="center"> Item</th>
      <th scope="col" align="center"> Min</th>
      <th scope="col" align="center"> Typical</th>
      <th scope="col" align="center"> Max</th>
      <th scope="col" align="center"> Unit</th>
    </tr>
    <tr>
      <th scope="row"> Voltage</th>
      <td align="center">4.8</td>
      <td align="center">5.0</td>
      <td align="center">12</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row"> Current</th>
      <td align="center">2</td>
      <td align="center">-</td>
      <td align="center">500</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row"> Dimension(with antenna)</th>
      <td align="center" colspan="3"> 76.0(L)x55.0(W)x23.5(H)</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row"> Net Weight</th>
      <td align="center" colspan="3"> 47±2</td>
      <td align="center">g</td>
    </tr>
  </tbody>
</table>

## Interface Function

![GPRS+GSM+GPS Shield interface.jpg](https://wiki.elecrow.com/images/thumb/c/cf/GPRS%2BGSM%2BGPS_Shield_interface.jpg/800px-GPRS%2BGSM%2BGPS_Shield_interface.jpg){ loading=lazy }  
**Power supply** - Vin connected to external 5~9VDC power supply  
**Antenna interface** - connected to external antenna  
**Serial port select** - select either software serial port or hareware serial port to be connected to GPRS+GSM+GPS Shield Shield  
**Hardware Serial** - D0/D1 of Arduino/Crowduino  
**Software serial** - D7/D8 of Arduino/Crowduino  
**Status LED** - tell whether the power of SIM808 is on  
**Net light** - tell the status about SIM808 linking to the net  
**1PPS** - tell the status about SIM808 get the location  
**UART of SIM808** - UART pins breakout of SIM808  
**Microphone** - to answer the phone call  
**Speaker** - to answer the phone call  
**GPIO,PWM and ADC of SIM808** - GPIO,PWM and ADC pins breakout of SIM808  
**Power key** - power up and down for SIM808  

### **Pins usage on Arduino**

**D0** - Unused if you select hardware serial port to communicate with GPRS+GSM+GPS Shield  
**D1** - Unused if you select hardware serial port to communicate with GPRS+GSM+GPS Shield  
**D2** - Unused  
**D3** - Unused  
**D4** - Unused  
**D5** - Unused  
**D6** - Unused  
**D7** - Used if you select software serial port to communicate with GPRS+GSM+GPS Shield  
**D8** - Used if you select software serial port to communicate with GPRS+GSM+GPS Shield  
**D9** - Used for software control the power up or down of the SIM808  
**D10** - Unused  
**D11** - Unused  
**D12** - Unused  
**D13** - Unused  
**D14(A0)** - Unused  
**D15(A1)** - Unused  
**D16(A2)** - Unused  
**D17(A3)** - Unused  
**D18(A4)** - Unused  
**D19(A5)** - Unused  

## Usage

### **Hardware installation**

#### **1.Insert an Micro SIM card to SIM Card Holder**

6 Pin Holder for SIM Cards. Both 1.8 volts and 3.0 volts SIM Cards are supported by SIM808 - the SIM card voltage type is automatically detected.
![Inserting the SIM Card into the holder4.jpg](https://wiki.elecrow.com/images/thumb/3/3a/Inserting_the_SIM_Card_into_the_holder4.jpg/500px-Inserting_the_SIM_Card_into_the_holder4.jpg){ loading=lazy }

#### **2.Connect the Antenna**

A miniature coaxial RF connector is present on the SIM808 GPRS/GSM+GPS Shield board to connect with a GSM Antenna. The connector present on the SIM808 GPRS/GSM+GPS Shield is called a [U.FL connecto](http://en.wikipedia.org/wiki/Hirose_U.FL).The GSM Antenna supplied with the GPRS Shield has an [SMA connector](http://en.wikipedia.org/wiki/SMA_connector) (and not an RP-SMA connector) on it.The connection topology is shown in the diagram below:  
![GPRS+GSM+GPS Shield antenna pad2.jpg](https://wiki.elecrow.com/images/thumb/a/a5/GPRS%2BGSM%2BGPS_Shield_antenna_pad2.jpg/850px-GPRS%2BGSM%2BGPS_Shield_antenna_pad2.jpg){ loading=lazy }  
![GPRS+GSM+GPS Shield antenna pad3.jpg](https://wiki.elecrow.com/images/thumb/e/e7/GPRS%2BGSM%2BGPS_Shield_antenna_pad3.jpg/800px-GPRS%2BGSM%2BGPS_Shield_antenna_pad3.jpg){ loading=lazy }

#### **3.Plug to Arduino/Crowduino**

The GPRS+GSM+GPS Shield, like any other well designed shield, is stackable as shown in the photo below.  
![Plug SIM808 GPRS GSM+GPS to arduino.jpg](https://wiki.elecrow.com/images/thumb/4/4c/Plug_SIM808_GPRS_GSM%2BGPS_to_arduino.jpg/800px-Plug_SIM808_GPRS_GSM%2BGPS_to_arduino.jpg){ loading=lazy }

#### Turn on the SIM808 GPRS/GSM+GPS shield

There is two ways to turn on the SIM808 GPRS/GSM+GPS Shield.  
1. Turn on through Hardware. Press the the 'POWERKEY' for few seconds until Power-on indicator(Green) is on.  
![POWERONkey](https://wiki.elecrow.com/images/thumb/9/96/GPRS%2BGSM%2BGPS_PowerKEY.jpg/800px-GPRS%2BGSM%2BGPS_PowerKEY.jpg){ loading=lazy }  
2. Turn on through Software. If the JP is soldered,run the following code, the SIM808 will POWER on or POWER off.

```
int Powerkey = 9;
void setup() {                
  pinMode(Powerkey, OUTPUT);   // initialize the digital pin as an output.  
  power();                     //power on the sim808 or power down the sim808
}
void loop() 
{

}

void power(void)
{
  digitalWrite(Powerkey, LOW); 
  delay(1000);               // wait for 1 second
  digitalWrite(Powerkey, HIGH);
}
```

#### **Serial Port(UART) Communication**

The SIM808 GPRS/GSM+GPS Shield is used UART protocol to communicate with an Arduino/Arduino clone; Users can use jumpers to connect (RX,TX) of the shield to either Software Serial(D8,D7) or Hardware Serial(D1,D0) of the Arduino.Detailed information is showed as the following picture:

![Coms1.jpg](https://wiki.elecrow.com/images/3/38/Coms1.jpg){ loading=lazy }

**Selectalbe GPRS+GSM+GPS Shield Communication Port**

### **Power Down the GPRS Shield**

The GPRS Shield can be turned off by following ways:

- <font color="red">**1, Normal power down procedure**</font>: Turn off the GPRS shield by using **Hardware Triger**; Press the **ON/OFF Button** about one seconds.

The power down scenarios illustrates as following figure:

![ONd.jpg](https://wiki.elecrow.com/images/7/79/ONd.jpg){ loading=lazy }

**Figure of Timing of turning off GPRS Shield using Hardware Triger**

- <font color="red">**2, Normal power down procedure**</font>: If <font color="red">JP</font> is soldered, then give <font color="red">Digital Pin 9</font> of the Arduino(act as Software Triger) a Turn off Impulse can turn off the GPRS Shield. The power down scenarios illustrates as following figure:

![Pwrd.jpg](https://wiki.elecrow.com/images/1/1a/Pwrd.jpg){ loading=lazy }

**Figure of Timing of turning off GPRS Shield using Software Triger**

<font color="red">The following code is power down subroutine for Arduino if using software triger:</font>

```
int Powerkey = 9;
void setup() {                
  pinMode(Powerkey, OUTPUT);   // initialize the digital pin as an output.  
  power();                     //power on the sim808 or power down the sim808
}
void loop() 
{

}

void power(void)
{
  digitalWrite(Powerkey, LOW); 
  delay(1000);               // wait for 1 second
  digitalWrite(Powerkey, HIGH);
}
```

- <font color="red">**3, Normal power down procedure**</font>: Turn off the GPRS shield by sending AT command **"AT+CPOWD=1"** to SIM808 module.

When GPRS Shield power dowm in **Normal power down procedure**, the procedure lets the SIM808 log off from the network and allows the software to enter into a secure state and save data before completely disconnecting the power supply. Before the completion of the power down procedure the SIM808 will send out result code:

**NORMAL POWER DOWN**

- <font color="red">**4, Over-voltage or Under-voltage Power Down**</font>: The module software monitors VBAT voltage constantly.

①If the voltage ≤ 3.5V, the following URC will be reported:

**UNDER-VOLTAGE WARNNING**

②If the voltage ≥ 4.3V, the following URC will be reported:

**OVER-VOLTAGE WARNNING**

③If the voltage < 3.4V, the following URC will be reported,and the module will be automativally powered down.

**UNDER-VOLTAGE POWER DOWN**

④If the voltage > 4.4V, the following URC will be reported,and the module will be automativally powered down.

**OVER-VOLTAGE POWER DOWN**

- <font color="red">**5, Over-temperature or Under-temperature Power Down**</font>: SIM900 will constantly monitor the temperature of the module.

①If the temperature > +80℃, the following URC will be reported:

**+CMTE:1**

②If the temperature < -30℃, the following URC will be reported:

**+CMTE:-1**

③If the temperature > +85℃, the following URC will be reported,and the module will be automativally powered down.

**+CMTE:2**

④If the temperature < -40℃, the following URC will be reported,and the module will be automativally powered down.

**+CMTE:-2**

When the GPRS Shield encounters POWER DOWN scenario, the AT commands can not be executed. The SIM808 logs off from network and enters the POWER DOWN mode, only the RTC is still active. POWER DOWN can also be indicated by STATUS LED(Blue), which is off in this mode.

<font color="red">Note:</font>

<font color="red">To monitor the temperature, users can use the “**AT+CMTE**” command to read the temperature when GPRS Shield is powered on.</font>

### **Upload Sketch to Arduino**

![Grpsaurduinouart1.jpg](https://wiki.elecrow.com/images/0/09/Grpsaurduinouart1.jpg){ loading=lazy }

**Data Stream among Computer, Arduino and GPRS Shield**

The following sketch configures Arduino/Arduino clone as serial link between PC and the GPRS Shield(<font color="red">Jumpers on SWserial side</font>). PC would need a serial terminal software to communicate with it - Window's built-in HyperTerminal, Arduino IDE's Serial Monitor, [Serial Terminals(sscom32)](http://www.elecrow.com/wiki/images/b/b2/Sscom32E.zip) or [Bray++ Terminal](http://sites.google.com/site/terminalbpp/).

After uploading the sketch to the Arduino board, press the ON/OFF button on the GPRS Shield to turn it on; Now you can see what you get on the serial terminal and the status of the three indicator LEDs, then communicate with your Shield.

```
//Serial Relay - Arduino will patch a 
//serial link between the computer and the GPRS Shield
//at 19200 bps 8-N-1
//Computer is connected to Hardware UART
//GPRS Shield is connected to the Software UART 

#include <SoftwareSerial.h>

SoftwareSerial GSMSerial(7, 8);

void setup()
{
GSMSerial.begin(19200);               // the GPRS/GSM baud rate   
Serial.begin(19200);                 // the GPRS/GSM baud rate   
}

void loop()
{
if(Serial.available())

GSMSerial.print((char)Serial.read());

else  if(GSMSerial.available())

Serial.print((char)GSMSerial.read());
}
```

![SIM808 gprs gsm shield AT.jpg](https://wiki.elecrow.com/images/thumb/0/00/SIM808_gprs_gsm_shield_AT.jpg/500px-SIM808_gprs_gsm_shield_AT.jpg){ loading=lazy } 

<font color="red">Note:</font>

<font color="red">The "AT" or "at" prefix must be set at the beginning of each Command line. To terminate a Command line enter <CR>.</font>

#### **Set Baud and Enable Charging Function**

It is recommended to execute this process when first time to use the module. In the Serial Monitor columns of following tables, input of AT commands are in back, module returns values are in orange.

|                      Serial Monitor                      |                         Description                          |
| :------------------------------------------------------: | :----------------------------------------------------------: |
|                          AT <font color="#F28500">OK</font>                          | Send command “AT” to synchronize baud rate. Serial port of module is by default set at auto-baud mode, and in this mode, it will not output any indications when the module is on. |
|                      AT+IPR=9600 <font color="#F28500">OK</font>                      | Set baud rate at 9600bps, supports baud rate from 1200bps to 115200bps. |
|                     AT+ECHARGE=1 <font color="#F28500">OK</font>                      | Send command “AT+ECHARGE=1” to enable battery charging function. By default the charging function is closed. |
|                         AT&W <font color="#F28500">OK</font>                          |                   Save parameter setting.                    |
|               AT+CPOWD=1 NORMAL POWER DOWN               |                    Power down the module.                    |
| RDY +CFUN: 1 GPS Ready +CPIN: READY Call Ready SMS Ready | Turn on the module again by the power button, it will response status about GPS and GSM. |
|                AT+CBC +CBC: 1,96,4175 <font color="#F28500">OK</font>                 |   Inquire charging status and remaining battery capacity.    |
|                   AT+CSQ +CSQ: 14,0 <font color="#F28500">OK</font>                   |                 Inquire GSM signal quality.                  |

#### Get location with GPS

|                        Serial Monitor                        |                         Description                          |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                       AT+CGPSPWR=1 <font color="#F28500">OK</font>                        |                           Open GPS                           |
|       AT+CGPSSTATUS? <font color="#F28500">+CGPSSTATUS: Location Not Fix OK</font>        | Read GPS fix status, “Location Not Fix” means that positioning is not successful. For the first time to start, it will take at least 30s. ***GPS must be tested by the window or outdoor.*** |
|        AT+CGPSSTATUS? <font color="#F28500">+CGPSSTATUS: Location 3D Fix OK</font>        |                GPS has fixed with 3D status.                 |
| AT+CGPSINF=0 <font color="#F28500">+CGPSINF: 0,2234.931817,11357.122485, 92.461185,20141031041141.000, 88,12,0.000000,0.000000</font> | Get the current GPS location information. Parameters formate: <mode>, <altitude>, <longitude>, <UTC time>, <TTFF>, <num>, <speed>, <course> |
| AT+CGPSOUT=32 <font color="#F28500">OK $GPRMC,043326.000,A, 2234.9414,N,11357.1187,E, 0.000,143.69,311014,,,A*50</font> | Read NMEA $GPRMC data, of which, “2234.9414 N, 11357.1187 E” is the location coordinates. For more details about NMEA sentences, [check this site](http://www.gpsinformation.org/dale/nmea.htm). |
|                       AT+CGPSRST=0 <font color="#F28500">OK</font>                        |                Reset GPS in Cold Start Mode.                 |
|                       AT+CGPSRST=1 <font color="#F28500">OK</font>                        |                 Reset GPS in Hot Start Mode.                 |
|                       AT+CGPSPWR=0 <font color="#F28500">OK</font>                        |                          Close GPS.                          |

#### GNSS AT Command

| AT Command |                      Description                       |
| :--------: | :----------------------------------------------------: |
| AT+CGNSPWR |                  GNSS power conntrol                   |
| AT+CGNSSEQ |       Define the last NMEA sentence that paresed       |
| AT+CGNSINF | GNSS navigation information parsed from NMEA sentences |
| AT+CGNSURC | GNSS navigation, GEO-fences and speed alarm URC report |
| AT+CGNSCMD |                  Send command to GNSS                  |
| AT+CGNSTST |        Send data received from GNSS to AT UART         |

More information you can refer the [SIM800 Series_GNSS_Application Note V1.00](https://wiki.elecrow.com/images/0/05/SIM800_Series_GNSS_Application_Note_V1.00.pdf).

### **Examples**

#### **Sending SMS: using Software UART**

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
