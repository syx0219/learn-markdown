---
title: Crowbits-Air Quality Sensor
---

## Description
-----------

This sensor is designed for a comprehensive monitor over indoor air condition. It's responsive to a wide scope of harmful gases, as carbon monoxide, alcohol, acetone, thinner, formaldehyde and so on. Due to the measuring mechanism, this sensor can’t output specific data to describe target gases' concentrations quantitatively. But it's still competent enough to be used in applications that require only qualitative results, like auto refresher sprayers and auto air cycling systems.

![Crowbits-Air-Quality-1.jpg](https://wiki.elecrow.com/images/thumb/9/91/Crowbits-Air-Quality-1.jpg/600px-Crowbits-Air-Quality-1.jpg){ loading=lazy }

## Features
--------

- Cost efficient
- Responsive to a wide scope of target gases

Specification
-------------

- Interface Type: Analog input
- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the A2 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-Air Quality Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/5/5c/Crowbits-Air_Quality_Sensor-Wiki_1.JPG/600px-Crowbits-Air_Quality_Sensor-Wiki_1.JPG){ loading=lazy }

3\. Download the library “AirQuality”. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
/*
  AirQuality Demo V1.0.
  connect to A0 to start testing. it will needs about 20s to start 
* By: http://www.seeedstudio.com
*/
#include"AirQuality.h"
#include"Arduino.h"
AirQuality airqualitysensor;
int current_quality =-1;

void setup()
{
    Serial.begin(9600);
    airqualitysensor.init(14);
}
void loop()
{
    current_quality=airqualitysensor.slope();
    if (current_quality >= 0)// if a valid data returned.
    {
        if (current_quality==0)
            Serial.println("High pollution! Force signal active");
        else if (current_quality==1)
            Serial.println("High pollution!");
        else if (current_quality==2)
            Serial.println("Low pollution!");
        else if (current_quality ==3)
            Serial.println("Fresh air");
    }
}

ISR(TIMER1_OVF_vect)
{
	if(airqualitysensor.counter==61)//set 2 seconds as a detected duty
	{

			airqualitysensor.last_vol=airqualitysensor.first_vol;
			airqualitysensor.first_vol=analogRead(A2);
			airqualitysensor.counter=0;
			airqualitysensor.timer_index=1;
			PORTB=PORTB^0x20;
	}
	else
	{
		airqualitysensor.counter++;
	}
}
```

5.After the upload is successful, open the serial port monitor, the baud rate is set to 9600. The serial port will print out the current air quality related information.

![Crowbits-Air Quality Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/3/3d/Crowbits-Air_Quality_Sensor-Wiki_2.jpg/600px-Crowbits-Air_Quality_Sensor-Wiki_2.jpg){ loading=lazy }