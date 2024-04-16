---
title: APM2.5 Airspeed Breakout Board MPXV7002DP
---

## Description
-----------

The MPXV7002 series piezoresistive transducer in the small outline package (SOP) is a state-of-the-art monolithic silicon pressure sensor designed for a wide range of applications, but particularly those employing a microcontroller or microprocessor with A/D inputs. This patented, single element transducer combines advanced micromachining techniques, thin-film metallization, and bipolar processing to provide an accurate, high level analog output signal that is proportional to the applied pressure.  
The MPXV7002 is designed to measure positive and negative pressure. In addition, with an offset specifically at 2.5V instead of the conventional 0V, this new series allows to measure pressure up to 7kPa through each port for pressure sensing but also for vacuum sensing (refer to the transfer function in the data sheet for more detailed information).  
**Model:[SLF0025APM](http://www.elecrow.com/apm25-airspeed-breakout-board-mpxv7002dp-p-1368.html)**

![APM2.5 Airspeed Breakout Board MPXV7002DP.jpg](https://wiki.elecrow.com/images/thumb/8/86/APM2.5_Airspeed_Breakout_Board_MPXV7002DP.jpg/400px-APM2.5_Airspeed_Breakout_Board_MPXV7002DP.jpg){ loading=lazy }

## Features
--------

- -2 to 2 kPa (-0.3 to 0.3 psi)
- 0.5 to 4.5 V Output
- Size:22x18x11mm

## Usage
-----

1.Hardware Installation


![APM2.5 Airspeed Breakout Board MPXV7002DP hardware.jpg](https://wiki.elecrow.com/images/thumb/e/e7/APM2.5_Airspeed_Breakout_Board_MPXV7002DP_hardware.jpg/500px-APM2.5_Airspeed_Breakout_Board_MPXV7002DP_hardware.jpg){ loading=lazy }


2.copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
int sensorPin = A0;   
int sensorValue = 0; 
float Vout=0;
float P=0;
void setup() {

  // declare the ledPin as an OUTPUT:
   Serial.begin(9600); 
}

void loop() {
    int i=0;
    int sum=0;
    int offset=0;
    Serial.println("init...");
    for(i=0;i<10;i++)
    {
         sensorValue = analogRead(sensorPin)-512;
         sum+=sensorValue;
    }
    offset=sum/10.0;
    Serial.println("Ok");
    while(1)
    {
       sensorValue = analogRead(sensorPin)-offset; 
       Vout=(5*sensorValue)/1024.0;
       P=Vout-2.5;           
       Serial.print("Presure = " );                       
       Serial.print(P*1000); 
       Serial.println("Pa");
       delay(1000);   
    }
}
```

3.Open the monitor of Arduino IDE,then blow the air to the MPXV7002DP, you can see the test result like flow.

![APM2.5 Airspeed Breakout Board MPXV7002DP test resullt.JPG](https://wiki.elecrow.com/images/b/b1/APM2.5_Airspeed_Breakout_Board_MPXV7002DP_test_resullt.JPG){ loading=lazy }

## Resources
---------

- [Datasheet](../../files/MPXV7002-pdf.md)