---
title: Digital light Sensor
---

## Introduction
------------

This module is based on the light-to-digital converter BH1750FVI, to transform light intensity to a digital signal. The sensor BH1750FVI is an digital Ambient light sensor IC for I2C bus interface. it is the most suiable to obtain the ambient light data for adjusting LCD and Keypad backlight, it is possible to detect wide range at high resolution, just using this digital light sensor. 

[BH1750FVI](http://www.elecrow.com/sensors-c-111/physical-monitor-c-111_125/digital-light-sensor-bh1750fvi-p-403.html)  
![Digital light sensor1.jpg](https://wiki.elecrow.com/images/thumb/8/8d/Digital_light_sensor1.jpg/400px-Digital_light_sensor1.jpg){ loading=lazy }

## Features
--------

- I2C bus Interface.
- Spectral responsibility is approximately human eye response.
- Illuminance to Digital Converter.
- Wide range and High resolution. ( 1 - 65535 lx ).
- Low Current by power down function.
- 50Hz / 60Hz Light noise reject-function.
- Light source dependency is little. ( ex. Incandescent Lamp. Fluorescent Lamp. Halogen Lamp. White LED. Sun Light).
- It is possible to select 2 type of I2C slave-address.
- Adjustable measurement result for influence of optical window.
- Small measurement variation (+/- 20%).
- The influence of infrared is very small.
- Operating Voltage: 3.3V-5V.
- Dimensions: 0.85\*0.63\*0.13"(21\*16\*3.3mm).

## Specification
-------------

- power supply voltage: +3 to 5Vdc.
- Interface: I2C.
- Wide range and High resolution. ( 1 - 65535 lx ).
- It is possible to select 2 types of I2C slave-address.
- Small measurement variation (+/- 20%).
- Size: 0.85\*0.63\*0.13"(21\*16\*3.3mm).

## Usage
-----

### **Hardware**

Connect digital light sensor to your Arduino/Crowduino I2C wires(SDA:A4, D18;SCL:A5, D19)as below:  
![Digital ligth sensor hard.jpg](https://wiki.elecrow.com/images/3/3f/Digital_ligth_sensor_hard.jpg){ loading=lazy }  
note to connect the address pin to GND to set the I2C address to 0100011  

### **Programming**

Copy the following program to Arduino IDE and upload to your Arduino/Crowduino:

```
/*
 Sample code for the BH1750 Light sensor
 website:www.elecrow.com
 Connection:
 VCC-5v
 GND-GND
 SCL-SCL(analog pin 5)
 SDA-SDA(analog pin 4)
 ADD-NC or GND
 */  
#include <Wire.h> //BH1750 IIC Mode 
#include <math.h> 
int BH1750address = 0x23; //setting i2c address
byte buff[2];
void setup()
{
  Wire.begin();
  Serial.begin(57600);//init Serail band rate
}
 
void loop()
{
  int i;
  uint16_t val=0;
  BH1750_Init(BH1750address);
  delay(200);
 
  if(2==BH1750_Read(BH1750address))
  {
    val=((buff[0]<<8)|buff[1])/1.2;
    Serial.print(val,DEC);     
    Serial.println("[lx]"); 
  }
  delay(150);
}
int BH1750_Read(int address) //
{
  int i=0;
  Wire.beginTransmission(address);
  Wire.requestFrom(address, 2);
  while(Wire.available()) //
  {
    buff[i] = Wire.read();  // receive one byte
    i++;
  }
  Wire.endTransmission();  
  return i;
} 
void BH1750_Init(int address) 
{
  Wire.beginTransmission(address);
  Wire.write(0x10);//1lx reolution 120ms
  Wire.endTransmission();
}
```

Open the Sscom32 terminal or the Serial moniter , and set the baudrate to 57600, you will see the output changing with light density.    
![Digital Light Sensor Score Picture.jpg](https://wiki.elecrow.com/images/thumb/b/b0/Digital_Light_Sensor_Score_Picture.jpg/300px-Digital_Light_Sensor_Score_Picture.jpg){ loading=lazy }

### **Resource**

[BH1750FVI datasheet](https://wiki.elecrow.com/images/4/40/BH1750FVI.pdf)  
[A Demo Video for Digital Light Sensor](http://v.youku.com/v_show/id_XMjYwMzg5Mzky.html)