---
title: How to export gerber files from Proteus ARES
---

It's really appreciated that @Christophe HAMON to share the method that how to configurate proteus ARES for Elecrow PCB. The following is the content that he shared with us.

This document explains how to generate correct Gerber files for Elecrow pcb.

## **ARES Design Rules**
---------------------

The following specifications are the minimum specifications you have to consider. You can of course increase the trace style (T25, T40…Etc.), Pad – Pad Clearance…

- Design Rules Tab

![Design rule 1.png](https://wiki.elecrow.com/images/f/f3/Design_rule_1.png){ loading=lazy }

1. Pad – Pad Clearance =12th
2. Pad – Trace Clearance = 8th
3. Trace – Trace Clearance = 6th
4. Graphics Clearance = 10th
5. Edge/Slot Clearance =20th

- Net Classes Tab

![Net classes.png](https://wiki.elecrow.com/images/4/48/Net_classes.png){ loading=lazy }

1. Trace Style = (6th)
2. The minimum value in ARES is 8th (T8)
3. Via Style =DEFAULT
4. Mini via: 
    1. Hole:12th
    2. Ring: 6th

## **Gerber Export**
-----------------

1. Click on Ouput -&gt;Generate Gerber/Excellon Files
2. Select all the layers to export. At least all selected on the following picture:

![Gerber export.png](https://wiki.elecrow.com/images/d/db/Gerber_export.png){ loading=lazy }

**Be sure to select “RS274X” for the Gerber Format.**

After pressing OK button ARES will generate a ZIP file containing several .TXT files. This is the package you have to send to Elecrow.


It's really appreciated to share your method to export gerber file for other PCB design software. Please feel free to contact David@elecrow.com to share with us.

## Relate Links
------------

Order [PCB Service](http://www.elecrow.com/services-c-73.html) Elecrow online