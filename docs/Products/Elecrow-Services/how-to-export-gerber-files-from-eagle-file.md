---
title: How to export gerber files from Eagle file
---

## Design rule
-----------

[Elecrow_PCB_eagle_rule.zip](https://www.elecrow.com/download/Elecrow_PCB_eagle_rule.zip) This design rule is to help check whether the width, drills meet the manufacturing ability or not.

## Resource Needed（CAM file download)
----------------------------------

- For 2 layers board,you need to download [Elecrow\_Gerber\_Generater\_DrillAlign.zip](https://www.elecrow.com/download/Elecrow_Gerber_Generater_DrillAlign.zip).
- For 4 layers board,you need to download [Elecrow\_Gerber\_Generater\_4-layer\_1-2-15-16.zip](https://www.elecrow.com/download/Elecrow_Gerber_Generater_4-layer_1-2-15-16.zip)

## Operation steps
---------------

1\. unzip the CAM file you download and add it to you eagle CAM folder.

2\. Open you PCBname.brd with eagle software. Here used the Crowduino as an example.

![1-open brdfile.png](https://wiki.elecrow.com/images/0/04/1-open_brdfile.png){ loading=lazy }

3.**Display all the layers of the PCB.** It's very important to avoid missing some layers in the gerber file.

![2-Display all the layers.png](https://wiki.elecrow.com/images/8/8a/2-Display_all_the_layers.png){ loading=lazy }

4.**Right-Click the CAM button**

![3-PressCAMprecessor.png](https://wiki.elecrow.com/images/f/f6/3-PressCAMprecessor.png){ loading=lazy }

5.**Right-Click File/Open/Job.**

6\. Choose Elecrow\_Gerber\_Generater\_DrillAlign.CAM and OPEN it. If the PCB is 4 layer, select the 4 layer CAM file.

![5-OpenCAMfile.png](https://wiki.elecrow.com/images/b/be/5-OpenCAMfile.png){ loading=lazy }

7.**Right-Click the *Processing Job* Button**

![4-CAMFILE-Processing.png](https://wiki.elecrow.com/images/0/04/4-CAMFILE-Processing.png){ loading=lazy }

8.Copy all the needed files to one folder and zip it.

Top layer: pcbname.GTL

Bottom layer: pcbname.GBL

Solder Stop Mask top: pcbname.GTS

Solder Stop Mask Bottom: pcbname.GBS

Silk Top: pcbname.GTO

Silk Bottom: pcbname.GBO

NC Drill: pcbname.TXT

Mechanical layer : pcbname.GML


For Stencil, the GTP and GBP layer is also needed.

**Now, What you need to do is [order PCB online](https://www.elecrow.com/pcb-manufacturing.html) ,and wait to get the PCB boards.**