---
title: Crowtail- PH Sensor
---

## Description
-----------

The Crowtail-PH sensor is a module that can measure aqueous solution PH(with combination PH electrode). It can output signal which corresponding to the hydrogen ion concentration that measured by PH electrode. Because it can be directly connected to controller,and then you can observe the PH value at any time.

Model: [CRT14016P](https://www.elecrow.com/crowtail-ph-sensor.html)

![PH Sensor.jpg](https://wiki.elecrow.com/images/thumb/3/3f/PH_Sensor.jpg/500px-PH_Sensor.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-ph-sensor.html?wiki "Title text")

## Features
--------

- Range of measurement: (0-14) pH
- Measuring temperature: (0-60) C
- Response time: less than 2min
- The plastic barrier protection of the fragile part of the electrode can not be broken and can be used as a stirring rod when measuring
- Strong anti-interference performance: the electrode is full screen type to prevent interference of external electric field when measuring

## Specification
-------------

Board demensions(mm):58.8(L)x20.0(W)x27.0(H)

| Item | Description |
|:-:|:-:|
| LED Control Mode | Analog Pin of Arduino |
| Working Voltage | 5V |
| Supply Mode | Crowtail Interface |
| Range of measurement | 0-14 pH |
| Measuring temperature | 0-60 C |

## Usage
-----

1\. Connect PH sensor to Crowtail sensor and connect the Crowtail sensor to Base Shield's analog port A0 with Crowtail Cable.

![Phconnect1.jpg](https://wiki.elecrow.com/images/thumb/c/c0/Phconnect1.jpg/500px-Phconnect1.jpg){ loading=lazy }

2\. Plug it onto the Arduino/Crowduino.

3.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
#define Vref 4.95
unsigned long int avgValue;     //Store the average value of the sensor feedback
int i=0;
void setup()
{
    Serial.begin(9600);
    pinMode(A0, INPUT);
    pinMode(A1, OUTPUT);
}
void loop()
{
    float sensorValue;
    int m;
    long sensorSum;
    int buf[10];                //buffer for read analog
  for(int i=0;i<10;i++)       //Get 10 sample value from the sensor for smooth the value
  { 
    buf[i]=analogRead(A0);//Connect the PH Sensor to A0 port
    delay(10);
  }
  for(int i=0;i<9;i++)        //sort the analog from small to large
  {
    for(int j=i+1;j<10;j++)
    {
      if(buf[i]>buf[j])
      {
        int temp=buf[i];
        buf[i]=buf[j];
        buf[j]=temp;
      }
    }
  }
       avgValue=0;
 
      for(int i=2;i<8;i++)                      //take the average value of 6 center sample
      avgValue+=buf[i];
    
     sensorValue =   avgValue/6;
     Serial.print(sensorValue);
     Serial.println(" ");

    Serial.print(" the PH value is");
    Serial.print(7-1000*(sensorValue-365)*Vref/59.16/1023,2);
    Serial.println(" ");
    delay(1000);

}
```

4.First, put the electrode assembly pH in the neutral solution.

5.You can open the monitor and see the data from Arduino,as below:

![Phneutralshow.png](https://wiki.elecrow.com/images/thumb/e/ef/Phneutralshow.png/500px-Phneutralshow.png){ loading=lazy }

6.Sencond,put the PH sensor into the acidic solution.

7.You can open the monitor and observe the data,as below:

![Phacidicshow.png](https://wiki.elecrow.com/images/thumb/8/8d/Phacidicshow.png/500px-Phacidicshow.png){ loading=lazy }

## Resource
--------

- [ph sensor code](../../files/Ph-sensor-code-zip.md)
- [ph sensor schematic](../../files/Ph-sensor-schematic-zip.md)