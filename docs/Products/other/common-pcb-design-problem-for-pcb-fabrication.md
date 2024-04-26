---
title: Common PCB design problem for PCB fabrication
---

## Common PCB design problem for PCB fabrication
-----

There are some frequent **PCB Gerber files problems** before PCB production, the most common problems are listed below. You can check gerber file online. There is a lot of online gerber viewer. This gerber viewer is good. http://www.gerber-viewer.com/ If there’s any question about **PCB design** or **fabrication**, please feel free to contact PCB@elecrow.com

## **Part A: Excalation**

A list of necessary files for a 2 sided PCB:

image1:

![List of necessary files.png](https://wiki.elecrow.com/images/e/e8/List_of_necessary_files.png){loading=lazy}  
a.No Drill file

We need NC data in format excellon.txt, it is necessary normally. Shown as “sample.TXT” in image 1.

b.No Copper layer

In format “RS-274-X”, named as “GTL”&”GBL” in a general way. One of them when 1 sided PCB, or you could put no copper layers in your gerber unless you do not need any circuit.

c.No Solder Mask layer

Color-coded resist for protecting the copper, named as “GTS” and “GBS”. The solid parts in these layers mean opening of pads (exposed). Please fill all the area of solder mask layer when you want bare copper.

d.No Mechanical layer (Outline)

Outline is necessary for fabrication through fair and foul, named as “GML” or “GKO”. Certainly you can add outline to any other layer (except drill file), then no need for a separate mechanical layer.

## **Part B: Forgot to upload the gerber file**
-----

If you find that you forgot to upload the gerber file when place the order, you can send the update gerber file to PCB@elecrow.com with Elecrow order number.

To **avoid** possible delay, when you place the order, please pay attention to the following notes:  
* **1)Lack of the gerber files problems.**  
* **2)1-layer PCB solder mask mis-understanding problem.**  
* **3)Forget to upload the gerber file.**  

## **Part C: Stack-up of 4 sided PCB**
-----

Copper layers of a 4 sided PCB should be named as “GTL”, “G1”, “G2” and “GBL”, then we know the stack-up from top to bottom is “GTL-G1-G2-GBL”. Please indicate the correct sequence in the comment if other naming.

## **Part D: Panelization**
-----

“x-y copies” means a scope of the number of boards in one panel, it depends on the actual dimension of your PCB and the max size you choose. “x different sub-pcbs” means the number of different designs in your gerber.

## **Part E: Acceptable format**
-----

Gerber “RS-274-X” is the sole format for fabrication, but we can help you to output gerber from other formats, they are “BRD”, “PCBdoc”, “LAY6”.

If there’s any question, please feel free to contact PCB@elecrow.com