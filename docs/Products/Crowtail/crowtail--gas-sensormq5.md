---
title: Crowtail- Gas Sensor(MQ5)
---

## Description
-----------

The Crowtail- Gas Sensor(MQ5) module is useful for gas leakage detection (in home and industry). It is suitable for detecting <font color="blue">H2, LPG, CH4, CO, Alcohol</font>. Due to its high sensitivity and fast response time, measurements can be taken as soon as possible. The sensitivity of the sensor can be adjusted by using the potentiometer. 

**Model: [CT0044GSF](http://www.elecrow.com/crowtail-gas-sensormq5-p-1492.html)**

![Crowtail- Gas Sensor(MQ5).JPG](https://wiki.elecrow.com/images/thumb/6/68/Crowtail-_Gas_Sensor%28MQ5%29.JPG/600px-Crowtail-_Gas_Sensor%28MQ5%29.JPG){ loading=lazy }

## Features
--------

- Wide detecting scope
- Stable and long life
- Fast response and High sensitivity

## Specification
-------------

Dimensions(mm):40.0(L)x20.0(W)x27.4(H)

| Item | Parameter | Min | Typical | Max | Unit |
|---|---|---|---|---|---|
| VCC | Working Voltage | 4.9 | 5 | 5.1 | V |
| PH | Heating consumption | 0.5 | - | 800 | mW |
| RL | Load resistance |  | adjustable |  |  |
| RH | Heater resistance | - | 31±10% | - | Ω |
| Rs | Sensing Resistance | 10 | - | 60 | kΩ |
| Scope | Detecting Concentration | 200 | - | 10000 | ppm |

## Application Ideas
-----------------

- Gas leakage detection.
- Toys.

## Hardware Overview
-----------------

This is a Analog output sensor. This needs to be connected to any one Analog socket in [Base Shield](http://www.seeedstudio.com/wiki/index.php?title=Base_shield_v2&uselang=en). The examples used in this tutorial makes uses of A0 analog pin. Connect this module to the A0 port of Base Shield.

It is possible to connect the Crowtail module to Arduino directly by using jumper wires by using the connection as shown in the below table:

| Arduino | Gas Sensor |
|---|---|
| 5V | VCC |
| GND | GND |
| NC | NC |
| Analog A0 | SIG |


The output voltage from the Gas sensor increases when the concentration of gas increases. Sensitivity can be adjusted by varying the potentiometer. Please note that the best preheat time for the sensor is above 24 hours. For detailed information about the MQ-5 sensor, please refer to the data-sheet provided in resource section.

## Getting Started
---------------

Connect the Crowtail- Gas Sensor(MQ5) to A0 port as shown in the above picture.  
![Gas Sensor(MQ5)hardwareconnect1.jpg](https://wiki.elecrow.com/images/thumb/f/f0/Gas_Sensor%28MQ5%29hardwareconnect1.jpg/600px-Gas_Sensor%28MQ5%29hardwareconnect1.jpg){ loading=lazy }

### **Gas Detection : Basic Example**

In this example, the sensor is connected to A0 pin. The voltage read from the sensor is displayed. This value can be used as a threshold to detect any increase/decrease in gas concentration.

```
<syntaxhighlight lang="Arduino">
void setup() {
  Serial.begin(9600);
}
 
void loop() {
  float sensor_volt; 
  float sensorValue;

  sensorValue = analogRead(A0);
  sensor_volt = sensorValue/1024*5.0;
 
  Serial.print("sensor_volt = ");
  Serial.print(sensor_volt);
  Serial.println("V");
  delay(1000);
}

</syntaxhighlight>
```

### **Measurement : Approximation**

This examples demonstrates a way to know the approximate concentration of Gas. As per the data-sheet of the MQ5 sensors, these equations are tested for standard conditions and are not calibrated. It may vary based on change in temperature or humidity.

1.Keep the Gas Sensor in clean air environment. Upload the below program.

```
<syntaxhighlight lang="Arduino">
void setup() {
  Serial.begin(9600);
}
 
void loop() {
  float sensor_volt; 
  float RS_air; //  Get the value of RS via in a clear air
  float R0;  // Get the value of R0 via in H2
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
  R0 = RS_air/6.5; // The ratio of RS/R0 is 6.5 in a clear air from Graph (Found using WebPlotDigitizer)
  
  Serial.print("sensor_volt = ");
  Serial.print(sensor_volt);
  Serial.println("V");
  
  Serial.print("R0 = ");
  Serial.println(R0);
  delay(1000);

}

</syntaxhighlight>
<br>
```

2\. Then, open the serial monitor of Arduino IDE. Write down the value of R0 and this needs to be used in the next program. Please node down the R0 after the reading stabilizes.


<font color="red">Replace the R0 below with value of R0 tested above</font>. Expose the sensor to any one of the gas listed above.

```
 
<syntaxhighlight lang="Arduino">
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
</syntaxhighlight>
<br>
```

Now, we can get the concentration of gas from the below figure

![Gas Sensor 4.png](https://wiki.elecrow.com/images/3/35/Gas_Sensor_4.png){ loading=lazy }

According to the figure, we can see that the minimum concentration we can test is 200ppm and the maximum is 10000ppm, in a other word, we can get a concentration of gas between 0.02% and 1%. However, we can't provide a formula because the relation between ratio and concentration is nonlinear.

## Resources
---------

- [MQ-5 datasheet](http://www.elecrow.com/download/MQ-5.pdf)