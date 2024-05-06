---
title: Crowtail- Rotation Angle Sensor
---

## Description
-----------

The Crowtail- TPL5111 Reset Enable Timer is a stand-alone breakout that will turn any electronics into low-power electronics! It can be used to activate or deactivate your electronic device via internal timer(The timing time can be up to 2 hours).TPL5111's current consumption is only 35nA，it is very suited for power gating with duty cycle or battery-powered applications. TPL5111 provides optional timing interval, the range of 100ms to 7200s, we provide 6 kinds of timing modes to help you use set the timing time accurately.

**Model:** [CRT00599T](https://www.elecrow.com/crowtail-tpl5111-reset-enable-timer.html)

![Crowtail- TPL5111 Reset Enable Timer.jpg](https://wiki.elecrow.com/images/thumb/9/9d/Crowtail-_TPL5111_Reset_Enable_Timer.jpg/500px-Crowtail-_TPL5111_Reset_Enable_Timer.jpg){ loading=lazy }

## Features
--------

- 6 kinds of timing time

- Timer accuracy: 1% (typical)

- Current consumption 2.5V: 35nA (TPL5111)

- Timing mode: manual/automatic(default automatic)

- Voltage range: 1.8V~5.5V

## **Specification**
-----------------

Dimensions(mm):40.0(L)x20.0(W)x6.8(H)

```
                                 MIN    MAX	         UNIT
 Supply Voltage (VDD-GND)	    -0.3	6.0	          V

 Input Voltage at any pin(3)	-0.3	VDD + 0.3	  V

 Input Current on any pin	    -5	    5	          mA

 Storage Temperature, Tstg	    -65	    150	          °C

 Junction Temperature, TJ(2)		    150	          °C
```

## Usger
-----

Make sure the DIP switch is OFF. Because it does not continuously sample the resistor, it only does it once when power is applied. So set the delay you want, then power up the breakout.

**Hardware Connection**.

![Efhhje1.jpg](https://wiki.elecrow.com/images/thumb/0/0e/Efhhje1.jpg/600px-Efhhje1.jpg){ loading=lazy }


Select the timing time you want, open the Corresponding switch. Now the ENOUT pin will periodically produce a low pulse, you'll see the red led lights flashing along.

On the other hand, you can also change the module to manual timer mode, using a soldering iron to remove the R11 resistor and take it to R10 location. In manual mode， module timing will start from the moment you press the button, When the timing timer comes, the ENOUT pin will produce a low pulse all the time.

## resource
--------

[TPL5111 datasheet](./files/TPL5111-pdf.md)