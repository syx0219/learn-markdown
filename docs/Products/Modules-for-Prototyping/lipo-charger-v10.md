---
title: Lipo Charger v1.0
---

## Description
-----------

Power your favorite electronic kit with green energy. The LiPo Charger board will Show RED to alarm when the quantity of electricity of battery is less than 60%, or it will show Green. It allows you ride the solar wave to run your favorite 5V device. The LiPo Charger board is the ideal green power solution for your outdoor sensor design. Attach the LiPo Charger board to your sensor board and it can run on solar power forever! It can also be used to charge mobile phone.

The LiPo Charger is extremely affordable and easy to use. No programming is required. Plug it in and it works. The internal charger IC handles all the power flow between the various components. In case solar power is not sufficient, the microUSB port allows you to charge your lithium battery through USB. It can also be used to program your kit without detaching the LiPo Charger board.

Model:[PSB01012B](http://www.elecrow.com/power-supply-c-68/battery-c-68_95/lipo-charger-p-346.html)

![Lipo Charger v1.0.jpg](https://wiki.elecrow.com/images/thumb/e/e3/Lipo_Charger_v1.0.jpg/600px-Lipo_Charger_v1.0.jpg){ loading=lazy }

## Interface
---------

![Interface Lipo Charge.png](https://wiki.elecrow.com/images/thumb/b/b7/Interface_Lipo_Charge.png/600px-Interface_Lipo_Charge.png){ loading=lazy }

## Features
--------

- Maximum 1A load output
- Battery and Solar panel connector is JST 2.0
- Stable 5V USB power supply regardless of source
- Charge/Recharge algorithms built into chip
- Charge Lithium Polymer Battery through solar power or USB
- Stable supply voltage through either lithium battery or USB
- 2 x USB ports let you program your kit while charging your Lithium battery
- LED indications for battery full or charging states
- One red alarm LED and one green status LED

## Application Ideas
-----------------

- Green Power and backup supply for distributed outdoor sensor network
- Charger for Lithium batteries
- Charger for mobile phone

## Cautions
--------

- Live exposed electronic components
- The board may get hot when supplying large loads
- Potential short circuit or electric shock, especially if device gets wet when placed outdoors for solar power collection

## Specification
-------------

<table border="1">
    <tbody>
        <tr>
            <th align="center">Items</th>
            <th align="center">Min</th>
            <th align="center">Norm</th>
            <th align="center">Max</th>
        </tr>
        <tr style="font-size: 90%;">
            <td align="center" width="400">V<sub>in</sub> Solar</td>
            <td align="center" width="200">4.8V</td>
            <td align="center" width="200">5.0V</td>
            <td align="center" width="200">6.5V(10s)</td>
        </tr>
        <tr style="font-size: 90%;">
            <td align="center">I<sub>charge</sub> (R<sub>Iset</sub>=3.9kΩ)</td>
            <td align="center">400mA</td>
            <td align="center">500mA</td>
            <td align="center">600mA</td>
        </tr>
        <tr style="font-size: 90%;">
            <td align="center">I<sub>load</sub></td>
            <td align="center">0mA</td>
            <td align="center"></td>
            <td align="center">1000mA</td>
        </tr>
        <tr style="font-size: 90%;">
            <td align="center">V<sub>batt</sub>(R<sub>x</sub>=0Ω)</td>
            <td align="center" rowspan="1" colspan="3">4.2V</td>
        </tr>
        <tr style="font-size: 90%;">
            <td align="center">V<sub>source USB</sub></td>
            <td align="center" rowspan="1" colspan="3">5.0V</td>
        </tr>
        <tr style="font-size: 90%;">
            <td align="center">V<sub>destination USB</sub></td>
            <td align="center" rowspan="1" colspan="3">5.0V</td>
        </tr>
        <tr style="font-size: 90%;">
            <td align="center">Dimensions</td>
            <td align="center" rowspan="1" colspan="3">50mm*68mm</td>
        </tr>
    </tbody>
</table>

## Usage
-----

### **Application Idea**

#### **1. Outdoor Sensor Device Power Supply**

One important application of the Lipo Charger board is as an affordable power supply for outdoor sensors. The outdoor sensor device will be powered by the lithium battery supplemented by the solar panel. Please note that it is not recommended to run the outdoor sensor ONLY on solar power, as this may vary during the day and may cause the sensor to reset / power down unexpectedly. In this case, the device is running in “USB Mode”.

If a firmware reprogram for the outdoor sensor device is required, simple connect the mini USB port to your PC which will put the device under “Program Mode” as explained above.

#### **2. Charge Lithium Polymer Battery through solar power**

## FAQ
---

Please list your question here, or connect with techsupport@elecrow.com.

## Support
-------

If you have questions or other better design ideas, you can go to our [forum](http://www.elecrow.com/forum) to discuss.

## Additional Idea
---------------

The Additional Idea is the place to write your project ideas about this product, or other usages you've found. Or you can write them on Projects page.

- [Get Lipo rider pro to charge Ipod or Iphone](http://www.seeedstudio.com/forum/viewtopic.php?f=4&t=3575)

## Resources
---------

- [CN3065 Datasheet in PDF](https://wiki.elecrow.com/images/d/d9/DSE-CN3065.pdf)
- [LiPo\_Charger\_1.0 Schematic in PDF](http://www.elecrow.com/wiki/images/1/12/LIpo_Charger_2.0.pdf)

## How to buy
----------

Click [here](http://www.elecrow.com) to buy Lipo Charger ,or other [products](http://www.elecrow.com) you like.

## Licensing
---------

This documentation is licensed under the Creative Commons [Attribution-ShareAlike License 3.0](http://creativecommons.org/licenses/by-sa/3.0/) Source code and libraries are licensed under [GPL/LGPL](http://www.gnu.org/licenses/gpl.html), see source code files for details.

## External Links
--------------

Links to external webpages which provide more application ideas, documents/datasheet or software libraries