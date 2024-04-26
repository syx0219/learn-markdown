---
title: Crowtail- Rotary Angle Sensor
---

## Description
-----------

Rotary angle sensor for crowduino.The angular range is 300 degrees with a linear change in value. The resistance value is 10k ohms, perfect for crowduino use. This may also be known as a “potentiometer ”.

**Model: [CT0053RAS](http://www.elecrow.com/crowtail-rotary-angle-sensor-p-1514.html)**

![CT0053RAS-01.jpg](https://wiki.elecrow.com/images/thumb/e/ea/CT0053RAS-01.jpg/600px-CT0053RAS-01.jpg){ loading=lazy }

## Specification
-------------

- Measurement angle range:0-300 degrees
- Easy to use
- Crowtail base module
- Work voltage:4.75v-5.25v
- Dimensions(mm):21.3(L)x20.0(W)x21.6(H)

## Usage
-----

1.Hardware Connection
The Rotary angle sensor is connecting to analog port A0 of Crowtail - Base Shield. A LED connecting to D5.

![Rotary Angle Sensor11.jpg](https://wiki.elecrow.com/images/thumb/6/6c/Rotary_Angle_Sensor11.jpg/600px-Rotary_Angle_Sensor11.jpg){ loading=lazy }

2.Download [Crowtail\_\_Rotary\_Angle\_Sensor library](../../files/Crowtail-Rotary-Angle-Sensor-zip.md) for Arduino boards with 16MHz XTAL; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;

3\. Open the code and upload it into your Arduino board

```
#define ROTARY_ANGLE_SENSOR A0
#define LED 5//the Crowtial- LED is connected to D5 of Arduino
#define ADC_REF 5//reference voltage of ADC is 5v.If the Vcc switch on the Crowduino
#define Crowtail_VCC 5//VCC of the grove interface is normally 5v
#define FULL_ANGLE 300//full value of the rotary angle is 300 degrees
void setup() 
{
	Serial.begin(9600);
        pinMode(ROTARY_ANGLE_SENSOR, INPUT);
	pinMode(LED,OUTPUT);
}

void loop() 
{
	int degrees=0;
	degrees = getDegree();
	Serial.println("The angle between the mark and the starting position:");
	Serial.println(degrees);	
	int brightness;
	/*The degrees is 0~300, should be converted to be 0~255 to control the*/
	/*brightness of LED													  */
	brightness = map(degrees, 0, FULL_ANGLE, 0, 255); 
	analogWrite(LED,brightness); /*The range of brightness is 0~255	*/	
	delay(500);
}

/************************************************************************/
/*Function: Get the angle between the mark and the starting position	*/	
/*Return:	-int,the range of degrees is 0~300 */
int getDegree()
{
	int sensor_value = analogRead(ROTARY_ANGLE_SENSOR);
	float voltage;
	voltage = (float)sensor_value*ADC_REF/1023;
	float degrees = (voltage*FULL_ANGLE)/Crowtail_VCC;
	return degrees;
}
```

4\. open the serial monitor to observe the change of angle data. And pay attention to the LED's brightness.

![123.png](https://wiki.elecrow.com/images/8/81/123.png){ loading=lazy }

## Resource
--------

- [Rotary Angle Sensor Program](../../files/Rotary-Angle-sensor-zip.md)
- [Crowtail- Rotary Angle Sensor](../../files/Crowtail-Rotary-Angle-Sensor-zip.md)