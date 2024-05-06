---
title: Crowtail- 3-Axis Digital Compass
---

## Description
-----------

Crowtail-3-Axis Compass module, a member of Crowtail family uses I²C based Honeywell HMC5883L digital compass. This ASIC is equipped with high resolution HMC118X magneto-resistive sensors and a 12-bit ADC. It provides compass heading accuracy up to 1° to 2°. Signal conditioning like amplification, automatic degaussing strap drivers and offset cancellation are inbuilt. This grove module also includes a MIC5205-3.3 for power supply requirement. Hence user can connect any 3.3V to 6V DC power supply.

**Model: [CT0059ADC](http://www.elecrow.com/crowtail-3axis-digital-compass-p-1520.html)**

![Crowtail- 3-Axis Digital Compass2.JPG](https://wiki.elecrow.com/images/thumb/8/81/Crowtail-_3-Axis_Digital_Compass2.JPG/400px-Crowtail-_3-Axis_Digital_Compass2.JPG){ loading=lazy }

## Specification
-------------

- Crowtail compatible interface
- 3-Axis Magneto-resistive type sensors
- I²C serial interface
- 2.0cm x 2.0cm Crowtail module
- 1° to 2° Degree heading accuracy
- Up to 116 Hz Maximum output rate
- Built-In self test
- Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

## Usage
-----

This demo is going to show you how to read raw data, how to calibrate the data with your local magnetic declination angle and how to get heading angle. First off, before any action you are going to take, you need to prepare a parameter you are going to use in your demo. That's your local magnetic declination.You can find it out in degree via [the magnetic declination webpage](http://www.magnetic-declination.com/). For example, mine is -2°37’, which is -2.617 degree. Then transfer it from degree to radians, and there you get the "declinationAngle". For example, in my case, declinationAngle = -2.617 / （2\*π）= -0.0456752665 rad. Three significant figures are enough. So I would shorten it into -0.0456 rad. And this is the parameter you are going to replace the value of "declinationAngle" in the domo code with.

1\. Plug it onto the I2C port of your [Crowtail- Base Shield](http://www.elecrow.com/crowtail-base-shield-p-1264.html).
![Crowtail- 3-Axis Digital Compass51.jpg](https://wiki.elecrow.com/images/thumb/1/10/Crowtail-_3-Axis_Digital_Compass51.jpg/600px-Crowtail-_3-Axis_Digital_Compass51.jpg){ loading=lazy }

2\. Download the [Crowtail- 3-Axis Digital Compass Program](./files/Crowtail-3-Axis-Digital-Compass-zip.md) and unpack it into arduino-1.0\\libraries in your Arduino installation folder.

3\. Open the demo code directly by the path:File -&gt; Example -&gt;Digital Compass -&gt;HMC5883L\_Example.

```
// Reference the I2C Library
#include <Wire.h>
// Reference the HMC5883L Compass Library
#include <HMC5883L.h>

//#include "Streaming.h"

// Store our compass as a variable.
HMC5883L compass;
// Record any errors that may occur in the compass.
int error = 0;

MagnetometerScaled valueOffset;


// Out setup routine, here we will configure the microcontroller and compass.
void setup()
{
  // Initialize the serial port.
  Serial.begin(9600);
  delay(2000);
  Serial.println("Starting the I2C interface.");
  Wire.begin(); // Start the I2C interface.

  Serial.println("Constructing new HMC5883L");
    
  Serial.println("Setting scale to +/- 1.3 Ga");
  error = compass.setScale(1.3); // Set the scale of the compass.
  if(error != 0) // If there is an error, print it out.
    Serial.println(compass.getErrorText(error));
  
  Serial.println("Setting measurement mode to continous.");
  error = compass.setMeasurementMode(MEASUREMENT_CONTINUOUS); // Set the measurement mode to Continuous
  if(error != 0) // If there is an error, print it out.
    Serial.println(compass.getErrorText(error));
    
  compassCalibrate();
}

// calibrate offset of x, y and z
void compassCalibrate(void)
{
  //Serial << ">>>> calibrate the compass\n";
  Serial.println("calibrate the compass");
  MagnetometerScaled valueMax = {0, 0, 0};
  MagnetometerScaled valueMin = {0, 0, 0};

  // calculate x, y and z offset
  
  //Serial << "please rotate the compass" << endl;
  Serial.println("please rotate the compass");
  int xcount = 0;
  int ycount = 0;
  int zcount = 0;
  boolean xZero = false;
  boolean yZero = false;
  boolean zZero = false;
  MagnetometerScaled value;
  while (xcount < 3 || ycount < 3 || zcount < 3) {
    value = compass.readScaledAxis();
    if ((fabs(value.XAxis) > 600) || (fabs(value.YAxis) > 600) || (fabs(value.ZAxis) > 600)) {
      continue;
    }
    
    if (valueMin.XAxis > value.XAxis) {
      valueMin.XAxis = value.XAxis;
    } else if (valueMax.XAxis < value.XAxis) {
      valueMax.XAxis = value.XAxis;
    }
    
    if (valueMin.YAxis > value.YAxis) {
      valueMin.YAxis = value.YAxis;
    } else if (valueMax.YAxis < value.YAxis) {
      valueMax.YAxis = value.YAxis;
    }
    
    if (valueMin.ZAxis > value.ZAxis) {
      valueMin.ZAxis = value.ZAxis;
    } else if (valueMax.ZAxis < value.ZAxis) {
      valueMax.ZAxis = value.ZAxis;
    }
    
    
    if (xZero) {
      if (fabs(value.XAxis) > 50) {
        xZero = false;
        xcount++;
      }
    } else {
      if (fabs(value.XAxis) < 40) {
        xZero = true;
      }
    }
    
    if (yZero) {
      if (fabs(value.YAxis) > 50) {
        yZero = false;
        ycount++;
      }
    } else {
      if (fabs(value.YAxis) < 40) {
        yZero = true;
      }
    }
    
    if (zZero) {
      if (fabs(value.ZAxis) > 50) {
        zZero = false;
        zcount++;
      }
    } else {
      if (fabs(value.ZAxis) < 40) {
        zZero = true;
      }
    }
    
    delay(30);
  }
  
  valueOffset.XAxis = (valueMax.XAxis + valueMin.XAxis) / 2;
  valueOffset.YAxis = (valueMax.YAxis + valueMin.YAxis) / 2;
  valueOffset.ZAxis = (valueMax.ZAxis + valueMin.ZAxis) / 2;
#if 0 
  Serial << "max: " << valueMax.XAxis << '\t' << valueMax.YAxis << '\t' << valueMax.ZAxis << endl;
  Serial << "min: " << valueMin.XAxis << '\t' << valueMin.YAxis << '\t' << valueMin.ZAxis << endl;
  Serial << "offset: " << valueOffset.XAxis << '\t' << valueOffset.YAxis << '\t' << valueOffset.ZAxis << endl;
  
  Serial << "<<<<" << endl;
#endif  
  Serial.print("max: ");
  Serial.print(valueMax.XAxis);
  Serial.print(valueMax.YAxis);
  Serial.println(valueMax.ZAxis);
  Serial.print("min: ");
  Serial.print(valueMin.XAxis);
  Serial.print(valueMin.YAxis);
  Serial.println(valueMin.ZAxis);
  Serial.print("offset: ");
  Serial.print(valueOffset.XAxis);
  Serial.print(valueOffset.YAxis);
  Serial.println(valueOffset.ZAxis);
}

// Our main program loop.
void loop()
{
  // Retrive the raw values from the compass (not scaled).
  MagnetometerRaw raw = compass.readRawAxis();
  // Retrived the scaled values from the compass (scaled to the configured scale).
  MagnetometerScaled scaled = compass.readScaledAxis();
  
  scaled.XAxis -= valueOffset.XAxis;
  scaled.YAxis -= valueOffset.YAxis;
  scaled.ZAxis -= valueOffset.ZAxis;
  
  // Values are accessed like so:
  int MilliGauss_OnThe_XAxis = scaled.XAxis;// (or YAxis, or ZAxis)

  // Calculate heading when the magnetometer is level, then correct for signs of axis.
  float yxHeading = atan2(scaled.YAxis, scaled.XAxis);
  float zxHeading = atan2(scaled.ZAxis, scaled.XAxis);
  
  float heading = yxHeading;
  
  // Once you have your heading, you must then add your 'Declination Angle', which is the 'Error' of the magnetic field in your location.
  // Find yours here: http://www.magnetic-declination.com/
  // Mine is: -2��37' which is -2.617 Degrees, or (which we need) -0.0456752665 radians, I will use -0.0457
  // If you cannot find your Declination, comment out these two lines, your compass will be slightly off.
  float declinationAngle = -0.0457;
  heading += declinationAngle;
  
  // Correct for when signs are reversed.
  if(heading < 0)
    heading += 2*PI;
    
  // Check for wrap due to addition of declination.
  if(heading > 2*PI)
    heading -= 2*PI;
   
  // Convert radians to degrees for readability.
  float headingDegrees = heading * 180/M_PI; 
  
  float yxHeadingDegrees = yxHeading * 180 / M_PI;
  float zxHeadingDegrees = zxHeading * 180 / M_PI;

  // Output the data via the serial port.
  // Output(raw, scaled, heading, headingDegrees);
  
//  Serial << scaled.XAxis << ' ' << scaled.YAxis << ' ' << scaled.ZAxis << endl;
//  Serial << "arctan y/x: " << yxHeadingDegrees << " \tarctan z/x: " << zxHeadingDegrees << endl;
  
  Serial.print(scaled.XAxis);
  Serial.print(scaled.YAxis);
  Serial.println(scaled.ZAxis);
  
  Serial.print("arctan y/x: ");
  Serial.print(yxHeadingDegrees);
  Serial.print("arctan z/x: ");  
  Serial.print(zxHeadingDegrees);
  
  // Normally we would delay the application by 66ms to allow the loop
  // to run at 15Hz (default bandwidth for the HMC5883L).
  // However since we have a long serial out (104ms at 9600) we will let
  // it run at its natural speed.
  delay(1000);//of course it can be delayed longer.
}

// Output the data down the serial port.
void Output(MagnetometerRaw raw, MagnetometerScaled scaled, float heading, float headingDegrees)
{
   Serial.print("Raw:\t");
   Serial.print(raw.XAxis);
   Serial.print("   ");   
   Serial.print(raw.YAxis);
   Serial.print("   ");   
   Serial.print(raw.ZAxis);
   Serial.print("   \tScaled:\t");
   
   Serial.print(scaled.XAxis);
   Serial.print("   ");   
   Serial.print(scaled.YAxis);
   Serial.print("   ");   
   Serial.print(scaled.ZAxis);

   Serial.print("   \tHeading:\t");
   Serial.print(heading);
   Serial.print(" Radians   \t");
   Serial.print(headingDegrees);
   Serial.println(" Degrees   \t");
}
```


4\. Upload the code and open the serial monitor.

5\. Open the serial monitor to check the result.
 ![3-Axis Digital Compass.jpg](https://wiki.elecrow.com/images/0/0b/3-Axis_Digital_Compass.jpg){ loading=lazy }

## Resource
--------

- [Crowtail- 3-Axis Digital Compass Program](./files/Crowtail-3-Axis-Digital-Compass-zip.md)
- [Crowtail- 3-Axis Digital Compass eagle files](./files/Crowtail-3-Axis-Digital-Compass-eagle-files-zip.md)