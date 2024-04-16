---
title: Analog CO/Combustible Gas Sensor(MQ9)
---

## Description
-----------

The Analog CO/Combustible Gas Sensor(MQ9) module is useful for gas leakage detecting, it used the sensitive material SnO2, which with lower conductivity in clean air. It make detection by method of cycle high and low temperature, and detect CO when low temperature (heated by 1.5V). The sensors conductivity is more higher along with the gas concentration rising. When high temperature (heated by 5.0V), it detects Methane, Propane etc combustible gas and cleans the other gases adsorbed under low temperature. MQ-9 gas sensor has high sensitity to Carbon Monoxide, Methane and LPG. The sensor could be used to detect different gases contains CO and combustible gases, it is with low cost and suitable for different application.  
**SKU: SEN90512P [SES90101S](http://www.elecrow.com/analog-cocombustible-gas-sensormq9-p-485.html)**

![Analog CO Combustible Gas Sensor(MQ9).jpg](https://wiki.elecrow.com/images/thumb/9/9a/Analog_CO_Combustible_Gas_Sensor%28MQ9%29.jpg/400px-Analog_CO_Combustible_Gas_Sensor%28MQ9%29.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/analog-cocombustible-gas-sensormq9-p-485.html?wiki "Title text")

## Features
--------

- High sensitivity to Methane, Propane and CO
- Long life and low cost
- Simple drive circuit

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

![Gas Sensor(MQ9)1.jpg](https://wiki.elecrow.com/images/thumb/6/6b/Gas_Sensor%28MQ9%291.jpg/500px-Gas_Sensor%28MQ9%291.jpg){ loading=lazy }

Demo cede
---------

1.Put the sensor in a clear air, copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
void setup() {
  Serial.begin(9600);
}
 
void loop() {
  float sensor_volt; 
  float RS_air; //  Get the value of RS via in a clear air
  float R0;  // Get the value of R0 via in LPG
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
  R0 = RS_air/9.9; // The ratio of RS/R0 is 9.9 in LPG gas
  
  Serial.print("sensor_volt = ");
  Serial.print(sensor_volt);
  Serial.println("V");
  
  Serial.print("R0 = ");
  Serial.println(R0);
  delay(1000);

}
```

2.Open the monitor of Arduino IDE, you can see some data are printed, write down the value of R0 and you need to use it in the following program. During this step, you may pay a while time to test the value of R0.

![Gas Sensor(MQ9)2.JPG](https://wiki.elecrow.com/images/c/c7/Gas_Sensor%28MQ9%292.JPG){ loading=lazy }

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

![Gas Sensor(MQ9)4.JPG](https://wiki.elecrow.com/images/5/55/Gas_Sensor%28MQ9%294.JPG){ loading=lazy }

## Resources
---------

- [Demo code](../../files/Gas-Sensor-MQ9-zip.md)
- [MQ-9.pdf](../../files/MQ-9-pdf.md)