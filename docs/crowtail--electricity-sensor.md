---
title: Crowtail- Electricity Sensor
---

## Description
-----------

The Electricity sensor module is a member of Crowtail. It is based on the TA12-200 current transformer which can transform the large AC into small amplitude. You can use it to test large alternating current up to 5A.

**Model: [CT010593E](https://www.elecrow.com/crowtail-electricity-sensor-p-1670.html)**

![Crowtail- Electricity Sensor.jpg](https://wiki.elecrow.com/images/thumb/e/e5/Crowtail-_Electricity_Sensor.jpg/600px-Crowtail-_Electricity_Sensor.jpg){ loading=lazy }

## Features
--------

- Crowtail compatible interface
- Maximum 5A input
- High accuracy
- Small size

## Specification
-------------

Dimensions(mm):40.0(L)x20.0(W)x21.7(H)

| Items | Min | Norm | Max | Unit |
|---|---|---|---|---|
| Transformation ratio | - | 2000:1 | - | - |
| Input Current | 0 | - | 5 | A |
| Output Current | 0 | - | 2.5 | mA |
| Sampling Resistance | - | 800 | - | Ω |
| Sampling Voltage | 0 | - | 2 | V |
| Working Frequency | 20 | - | 20K | HZ |
| Nonlinear scale | - | - | 0.2% | - |
| Phase Shift | - | - | 5' | - |
| Operating Temperature | -55 | - | 85 | ℃ |
| Dielectric strength | - | 6 | - | KVAC/1min |

## Usage
-----

### **With Arduino**

The following sketch demonstrates a simple application of measuring the amplitude of the alternating voltage.The SIG pin will output a alternating voltage based on the alternating current being measured. You can measure the value using ADC.

Connect the module to the analog A0 of Crowtail- Base board Put the alternating current wire through the hole of the current transformer.

![Electric sensor0021.jpg](https://wiki.elecrow.com/images/thumb/b/bf/Electric_sensor0021.jpg/600px-Electric_sensor0021.jpg){ loading=lazy }

1.Copy and paste code as below to a your Arduino sketch.

```
/****************************************************************************/	
//	Function: Measure the amplitude current of the alternating current and 
//			  the effective current of the sinusoidal alternating current.
//	Hardware: Crowtail - Electricity Sensor		
//	Date: 	 June 2,2016
//	by www.elecrow.com
#define ELECTRICITY_SENSOR A0 // Analog input pin that sensor is attached to

float amplitude_current;               //amplitude current
float effective_value;       //effective current 

void setup() 
{
	Serial.begin(9600); 
	pins_init();
}
void loop() 
{
	int sensor_max;
	sensor_max = getMaxValue();
	Serial.print("sensor_max = ");
	Serial.println(sensor_max);
	//the VCC on the Crowtail interface of the sensor is 5v
	amplitude_current=(float)sensor_max/1024*5/800*2000000;
	effective_value=amplitude_current/1.414;//minimum_current=1/1024*5/800*2000000/1.414=8.6(mA) 
						//Only for sinusoidal alternating current
	Serial.println("The amplitude of the current is(in mA)");
	Serial.println(amplitude_current,1);//Only one number after the decimal point
	Serial.println("The effective value of the current is(in mA)");
	Serial.println(effective_value,1);
}
void pins_init()
{
	pinMode(ELECTRICITY_SENSOR, INPUT);
}
/*Function: Sample for 1000ms and get the maximum value from the SIG pin*/
int getMaxValue()
{
	int sensorValue;             //value read from the sensor
	int sensorMax = 0;
	uint32_t start_time = millis();
	while((millis()-start_time) < 1000)//sample for 1000ms
	{
		sensorValue = analogRead(ELECTRICITY_SENSOR);
		if (sensorValue > sensorMax) 
		{
			/*record the maximum sensor value*/
			sensorMax = sensorValue;
		}
	}
	return sensorMax;
}
```

Note: The minimum effective current that can be sensed by the code can be calculated using the equation below. minimum\_current=1/1024\*5/800\*2000000/1.414=8.6(mA).

2.Open the serial monitor, The results is as follows：

![Electric sensor2.png](https://wiki.elecrow.com/images/7/7f/Electric_sensor2.png){ loading=lazy }

## Resource
--------

- [Crowtail- Electricity Sensor eagle file](https://wiki.elecrow.com/images/4/4f/Crowtail-_Electricity_Sensor_eagle_file.zip)