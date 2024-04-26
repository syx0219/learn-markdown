---
title: HC-SR505 Mini PIR Motion Sensor
---

## Introduction
------------

HC-SR505 Mini PIR Motion Sensor is based on infrared technology and it can automatic control by itself with high sensitivity and high reliability. Because of the minimum size and low-power operation mode, it widely used in various of automatic electronic equipment, especially battery-powered automatic products.  
Module:[SPS50506S](http://www.elecrow.com/hcsr505-mini-pir-motion-sensor-p-1382.html)

![HC-SR505 Mini PIR Motion Sensor.jpg](https://wiki.elecrow.com/images/thumb/1/1d/HC-SR505_Mini_PIR_Motion_Sensor.jpg/400px-HC-SR505_Mini_PIR_Motion_Sensor.jpg){ loading=lazy }

## Features
--------

- Automatic Control
- Minimum size
- Repeatable Trigger
- Wide range of operating voltage
- Low-power
- Output high signal

## Specification
-------------

- Operating voltage range: DC4.5-20V
- Quiescent Current: &lt;60uA
- Trigger: reusable trigger (default)
- Delay Time: The default 8S + -30%
- Board Dimensions: 10 \* 23mm
- Induction angle: &lt;100 degrees cone angle
- Sensing distance: 3 meters
- Working temperature: -20 to +80 degrees
- Sensor Lens Dimensions: Diameter: 10mm

## Usage
-----

### **Hardware**

Connect the PIR Motion Sensor to your Arduino/Crowduino power supply pin and digital pins. You can can connect the "s" terminal to any of your arduino Pins,like the "D6" as belows:  
![HC-SR505 Mini PIR Motion Sensor hardware.jpg](https://wiki.elecrow.com/images/thumb/9/99/HC-SR505_Mini_PIR_Motion_Sensor_hardware.jpg/500px-HC-SR505_Mini_PIR_Motion_Sensor_hardware.jpg){ loading=lazy }

### **Programming**

1.Copy the following program to Arduino IDE and upload to your Arduino/Crowduino:

```
void setup()  {
  Serial.begin(9600);
  pinMode(6,INPUT);
  digitalWrite(6,LOW);
}
void loop()  {
    if(digitalRead(6)==HIGH)  {
      Serial.println("Somebody is here.");
    }
    else  {
      Serial.println("Nobody.");
    }
    delay(1000);
}
```

2.Open the Serial moniter , and set the baudrate to 9600, you will see that When somebody is in front of the sensor , the Serial Monitor will output "Somebody is here.".Or, the Serial Monitor output "Nobody."

![HC-SR505 Mini PIR Motion Sensor test result.jpg](https://wiki.elecrow.com/images/a/a1/HC-SR505_Mini_PIR_Motion_Sensor_test_result.jpg){ loading=lazy }