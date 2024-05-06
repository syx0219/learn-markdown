---
title: Crowbits-WiFi
---

## Description
-----------

The Crowbits-WiFi module based on ESP-12, which is an ultra-low power UART-WiFi module. It has excellent dimensions and ULP technology compared to other similar modules. The module is a special design for mobile devices and the Internet of things. For example, you can use this module transmit date with its serial port. It is easy to communicate with others device

![Crowbits-Wifi-1.jpg](https://wiki.elecrow.com/images/thumb/d/d3/Crowbits-Wifi-1.jpg/600px-Crowbits-Wifi-1.jpg){ loading=lazy }

## Features
--------

- WiFi module
- Easy to use

## Specification
-------------

- Interface Type: UART
- Operating Voltage: 3.3V DC
- imensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the D2 and D3 interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-WiFi-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/6/6c/Crowbits-WiFi-Wiki_1.JPG/600px-Crowbits-WiFi-Wiki_1.JPG){ loading=lazy }

3.Upload the following code to the Crowbits-UNO board.

```
#include <SoftwareSerial.h>
 
#define DEBUG true
 
SoftwareSerial esp8266(2,3); // make RX Arduino line is pin 2, make TX Arduino line is pin 3.
                             // This means that you need to connect the TX line from the esp to the Arduino's pin 2
                             // and the RX line from the esp to the Arduino's pin 3
void setup()
{
  Serial.begin(115200);
  esp8266.begin(115200); // your esp's baud rate might be different
  sendData("AT+RST\r\n",2000,DEBUG); // reset module
  sendData("AT+CWMODE=2\r\n",1000,DEBUG); // configure as access point
  sendData("AT+CIFSR\r\n",1000,DEBUG); // get ip address
  sendData("AT+CIPMUX=1\r\n",1000,DEBUG); // configure for multiple connections
  sendData("AT+CIPSERVER=1,80\r\n",1000,DEBUG); // turn on server on port 80
}
 
void loop()
{
  if(esp8266.available()) // check if the esp is sending a message 
  {
    /*
    while(esp8266.available())
    {
      // The esp has data so display its output to the serial window 
      char c = esp8266.read(); // read the next character.
      Serial.write(c);
    } */
    
    if(esp8266.find("+IPD,"))
    {
     delay(1000);
 
     int connectionId = esp8266.read()-48; // subtract 48 because the read() function returns 
                                           // the ASCII decimal value and 0 (the first decimal number) starts at 48
     
     String webpage = "<h1>Hello World!</h1>";
     String cipSend = "AT+CIPSEND=";
     cipSend += connectionId;
     cipSend += ",";
     cipSend +=webpage.length();
     cipSend +="\r\n";
     
     sendData(cipSend,1000,DEBUG);
     sendData(webpage,1000,DEBUG);
 
     String closeCommand = "AT+CIPCLOSE="; 
     closeCommand+=5; // append connection id
     closeCommand+="\r\n";    
     sendData(closeCommand,3000,DEBUG);
    }
  }
}
 
 
String sendData(String command, const int timeout, boolean debug)
{
    String response = "";
    
    esp8266.print(command); // send the read character to the esp8266
    
    long int time = millis();
    
    while( (time+timeout) > millis())
    {
      while(esp8266.available())
      {      
        // The esp has data so display its output to the serial window 
        char c = esp8266.read(); // read the next character.
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

![Crowbits-WiFi-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/3/3d/Crowbits-WiFi-Wiki_2.jpg/600px-Crowbits-WiFi-Wiki_2.jpg){ loading=lazy }

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 115200. The serial port will display wireless network related information.

![Crowbits-WiFi-Wiki 3.jpg](https://wiki.elecrow.com/images/thumb/a/a0/Crowbits-WiFi-Wiki_3.jpg/600px-Crowbits-WiFi-Wiki_3.jpg){ loading=lazy }