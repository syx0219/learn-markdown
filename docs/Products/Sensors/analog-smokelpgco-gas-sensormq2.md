---
title: Analog Smoke/LPG/CO Gas Sensor(MQ2)
---

## Description
-----------

The Analog Smoke/LPG/CO Gas Sensor(MQ2) module utilizes an MQ-2 as the sensitive component and has a protection resistor and an adjustable resistor on board. The MQ-2 gas sensor is sensitive to LPG, i-butane, propane, methane, alcohol, Hydrogen and smoke. It could be used in gas leakage detecting equipments in family and industry. The resistance of the sensitive component changes as the concentration of the target gas changes.  
**SKU: SEN90512P [SES28011S](http://www.elecrow.com/analog-smokelpgco-gas-sensormq2-p-486.html)**

![Analog Smoke LPG CO Gas Sensor(MQ2).jpg](https://wiki.elecrow.com/images/thumb/0/05/Analog_Smoke_LPG_CO_Gas_Sensor%28MQ2%29.jpg/400px-Analog_Smoke_LPG_CO_Gas_Sensor%28MQ2%29.jpg){ loading=lazy }

## Features
--------

- Domestic gas leakage detector
- Industrial gas detector
- Portable gas detector

## Application Ideas
-----------------

- Domestic gas leakage detector
- Industrial gas detector
- Portable gas detector

## Usage
-----

### Hardware Installation

| Arduino UNO | Gas Sensor |
|---|---|
| 5V | VCC |
| GND | GND |
| Analog A0 | A0 |

![Gas Sensor(MQ2)3.jpg](https://wiki.elecrow.com/images/thumb/7/78/Gas_Sensor%28MQ2%293.jpg/500px-Gas_Sensor%28MQ2%293.jpg){ loading=lazy }

## Demo cede
---------

1.Put the sensor in a clear air, copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
void setup() {
  Serial.begin(9600);
}
 
void loop() {
  float sensor_volt; 
  float RS_air;                 //  Get the value of RS via in a clear air
  float R0;                     // Get the value of R0 via in H2
  float sensorValue;
 
/*--- Get a average data by testing 100 times ---*/   
    for(int x = 0 ; x < 100 ; x++)
  {
    sensorValue = sensorValue + analogRead(A0);
  }
  sensorValue = sensorValue/100.0;
/*-----------------------------------------------*/
 
  sensor_volt = sensorValue/1024*5.0;
  RS_air = (5.0-sensor_volt)/sensor_volt; // omit *RL
  R0 = RS_air/10.0;                       // The ratio of RS/R0 is 10 in a clear air
 
  Serial.print("sensor_volt = ");
  Serial.print(sensor_volt);
  Serial.println("V");
 
  Serial.print("R0 = ");
  Serial.println(R0);
  delay(1000);
}
```

2.Open the monitor of Arduino IDE, you can see some data are printed, write down the value of R0 and you need to use it in the following program. During this step, you may pay a while time to test the value of R0.

![Gas Sensor(MQ2)1.JPG](https://wiki.elecrow.com/images/thumb/9/96/Gas_Sensor%28MQ2%291.JPG/400px-Gas_Sensor%28MQ2%291.JPG){ loading=lazy }

3.Put the sensor in one gas where the environment you want to test in. <font color="red">However, don't forget to replace the R0 below with value of R0 tested above</font>

```
void setup() {
  Serial.begin(9600);
}
 
void loop() {
 
  float sensor_volt;
  float RS_gas; // Get value of RS in a GAS
  float ratio; // Get ratio RS_GAS/RS_air
  int sensorValue = analogRead(A0);
  sensor_volt=(float)sensorValue/1024*5.0;
  RS_gas = (5.0-sensor_volt)/sensor_volt; // omit *RL
 
  /*-Replace the name "R0" with the value of R0 in the demo of First Test -*/
  ratio = RS_gas/R0;  // ratio = RS/R0 
  /*-----------------------------------------------------------------------*/
  Serial.print("sensor_volt = ");
  Serial.println(sensor_volt);
  Serial.print("RS_ratio = ");
  Serial.println(RS_gas);
  Serial.print("Rs/R0 = ");
  Serial.println(ratio);
  Serial.print("\n\n");
  delay(1000);
}
```

Now, we can get the concentration of gas from the below figure 

![Gas Sensor(MQ2)2.JPG](https://wiki.elecrow.com/images/thumb/c/c6/Gas_Sensor%28MQ2%292.JPG/400px-Gas_Sensor%28MQ2%292.JPG){ loading=lazy }

## Resources
---------

- [Demo code](../../files/Gas-Sensor-MQ2-zip.md)
- [MQ-2.pdf](../../files/MQ-2-pdf.md)