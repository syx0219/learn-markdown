---
title: Crowtail- BMP180 Barometer
---

## Description
-----------

The BMP180 offers a pressure measuring range of 300 to 1100 hPa with an accuracy down to 0.02 hPa in advanced resolution mode. It’s based on piezo-resistive technology for high accuracy, ruggedness and long term stability. These come factory-calibrated, with the calibration coefficients already stored in ROM. What makes this sensor great is that it is nearly identical to its former rev, the BMP085!

**Model: [CT0017BMP](http://www.elecrow.com/crowtail-bmp180-barometer-p-1249.html)**

![Crowtail-BMP180 Barometer.JPG](https://wiki.elecrow.com/images/thumb/5/5c/Crowtail-BMP180_Barometer.JPG/400px-Crowtail-BMP180_Barometer.JPG){ loading=lazy }

## Features
--------

- Digital two wire (I2C) interface
- Wide barometric pressure range
- Flexible supply voltage range
- Ultra-low power consumption
- Low noise measurement
- Factory-calibrated
- -40 to +85°C operational range, ±2°C temperature accuracy
- I2C address: 0x77

## Specifications
--------------

Dimensions(mm):40.0(L)x20.0(W)x6.8(H)

| Item | Min | Typical | Max | Unit |
|:-:|:-:|:-:|:-:|:-:|
| Voltage | 3 | 5.0 | 5.5 | VDC |
| Current | 1.1 | / | 20 | uA |
| Pressure Range | 300 | / | 1100 | hPa |
| Faster I2C data transfer | / | / | 3.4 | MHZ |

## Usage
-----

Barometric condition is one of the criteria used to predict coming change in weather and deduce altitude above sea level. Here is a demo to show you how to read the barometric data from this Crowtail - Barometer Sensor (BMP180).

1.Hardware connection

Connect it to IIC port of Crowduino.

![BMP180hardware1.jpg](https://wiki.elecrow.com/images/thumb/c/c7/BMP180hardware1.jpg/600px-BMP180hardware1.jpg){ loading=lazy }

2.Download [the library](https://wiki.elecrow.com/images/d/df/SFE_BMP180.zip);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

```
// Your sketch must #include this library, and the Wire library.
// (Wire is a standard library included with Arduino.):  
#include <SFE_BMP180.h>
#include <Wire.h> 
// You will need to create an SFE_BMP180 object, here called "pressure": 
SFE_BMP180 pressure;
#define ALTITUDE 1655.0 
void setup()
{
 Serial.begin(9600);
 Serial.println("REBOOT"); 
 // Initialize the sensor (it is important to get calibration values stored on the device).
 if (pressure.begin())
   Serial.println("BMP180 init success");
 else
 {
   // Oops, something went wrong, this is usually a connection problem,
   // see the comments at the top of this sketch for the proper connections.
   Serial.println("BMP180 init fail\n\n");
   while(1); // Pause forever.
 }
} 
void loop()
{ 
 char status;
 double T,P,p0,a; 
 // Loop here getting pressure readings every 10 seconds. 
 // If you want sea-level-compensated pressure, as used in weather reports,
 // you will need to know the altitude at which your measurements are taken.
 // We're using a constant called ALTITUDE in this sketch:  
 Serial.println();
 Serial.print("provided altitude: ");
 Serial.print(ALTITUDE,0);
 Serial.print(" meters, ");
 Serial.print(ALTITUDE*3.28084,0);
 Serial.println(" feet");  
 // If you want to measure altitude, and not pressure, you will instead need
 // to provide a known baseline pressure. This is shown at the end of the sketch. 
 // You must first get a temperature measurement to perform a pressure reading.  
 // Start a temperature measurement:
 // If request is successful, the number of ms to wait is returned.
 // If request is unsuccessful, 0 is returned.
  status = pressure.startTemperature();
 if (status != 0)
 {
   // Wait for the measurement to complete:
   delay(status);
   // Retrieve the completed temperature measurement:
   // Note that the measurement is stored in the variable T.
   // Function returns 1 if successful, 0 if failure.
   status = pressure.getTemperature(T);
   if (status != 0)
   {
     // Print out the measurement:
     Serial.print("temperature: ");
     Serial.print(T,2);
     Serial.print(" deg C, ");
     Serial.print((9.0/5.0)*T+32.0,2);
     Serial.println(" deg F");
      
     // Start a pressure measurement:
     // The parameter is the oversampling setting, from 0 to 3 (highest res, longest wait).
     // If request is successful, the number of ms to wait is returned.
     // If request is unsuccessful, 0 is returned.
     status = pressure.startPressure(3);
     if (status != 0)
     {
       // Wait for the measurement to complete:
       delay(status);
       // Retrieve the completed pressure measurement:
       // Note that the measurement is stored in the variable P.
       // Note also that the function requires the previous temperature measurement (T).
       // (If temperature is stable, you can do one temperature measurement for a number of pressure measurements.)
       // Function returns 1 if successful, 0 if failure.
       status = pressure.getPressure(P,T);
       if (status != 0)
       {
         // Print out the measurement:
         Serial.print("absolute pressure: ");
         Serial.print(P,2);
         Serial.print(" mb, ");
         Serial.print(P*0.0295333727,2);
         Serial.println(" inHg");
         // The pressure sensor returns abolute pressure, which varies with altitude.
         // To remove the effects of altitude, use the sealevel function and your current altitude.
         // This number is commonly used in weather reports.
         // Parameters: P = absolute pressure in mb, ALTITUDE = current altitude in m.
         // Result: p0 = sea-level compensated pressure in mb 
         p0 = pressure.sealevel(P,ALTITUDE); // we're at 1655 meters (Boulder, CO)
         Serial.print("relative (sea-level) pressure: ");
         Serial.print(p0,2);
         Serial.print(" mb, ");
         Serial.print(p0*0.0295333727,2);
         Serial.println(" inHg"); 
         // On the other hand, if you want to determine your altitude from the pressure reading,
         // use the altitude function along with a baseline pressure (sea-level or other).
         // Parameters: P = absolute pressure in mb, p0 = baseline pressure in mb.
         // Result: a = altitude in m.

         a = pressure.altitude(P,p0);
         Serial.print("computed altitude: ");
         Serial.print(a,0);
         Serial.print(" meters, ");
         Serial.print(a*3.28084,0);
         Serial.println(" feet");
       }
       else Serial.println("error retrieving pressure measurement\n");
     }
     else Serial.println("error starting pressure measurement\n");
   }
   else Serial.println("error retrieving temperature measurement\n");
 }
 else Serial.println("error starting temperature measurement\n"); 
 delay(5000);  // Pause for 5 seconds.
}
```

3.Create a new Arduino sketch and paste the codes below to it or open the code directly by the path:File -&gt; Example -&gt;SFE\_BMP180\_example-&gt;SFE\_BMP180\_example.

4.Open the serial monitor.You should see the data from BMP0180.

![Bmp180result.jpg](https://wiki.elecrow.com/images/thumb/d/da/Bmp180result.jpg/400px-Bmp180result.jpg){ loading=lazy }

## Resource
--------

- [BMP180 Barometer Program](https://wiki.elecrow.com/images/d/df/SFE_BMP180.zip)
- [Crowtail- BMP180 Barometer eagle files](https://wiki.elecrow.com/images/6/66/Crowtail-BMP180_Barometer_eagle_files.zip)