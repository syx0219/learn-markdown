---
title: IMX219-83 Stereo Camera
---

## **Introduction**
----------------

This is a 3D stereo camera module which features dual IMX219 cameras onboard, 8Megapixels on each camera. It is suitable for AI vision applications like depth vision and stereo vision. Also, you can experience better quality video capture from this camera and build more demanding projects! The module supports Jetson Nano and NVIDIA Jetson Xavier NX, as well as Raspberry Pi CM3/CM3+ expansion boards like Compute Module IO Board Plus, Compute Module POE Board, etc.

**Model: [RPA20902A](https://www.elecrow.com/imx219-83-8mp-3d-stereo-camera-module-for-jetson-nano-xavier-nx.html)**

![IMX219-83 8MP 3D Stereo Camera Module for Jetson Nano Xavier NX 1.jpg](https://wiki.elecrow.com/images/thumb/7/7b/IMX219-83_8MP_3D_Stereo_Camera_Module_for_Jetson_Nano_Xavier_NX_1.jpg/600px-IMX219-83_8MP_3D_Stereo_Camera_Module_for_Jetson_Nano_Xavier_NX_1.jpg){ loading=lazy }

## **Specification**
-----------------

- POE input voltage: 37V ~ 57V DC
- POE output voltage: 5V 2.5A DC
- Network standard: 802.3af PoE
- OLED control interface: I2C
- OLED size: 0.91 inches
- OLED resolution: 128×32
- OLED driver chip: SSD1306
- OLED resolution: 65.0x56.5mm
- OLED display color: white
- OLED viewing angle: greater than 160°
- GPIO expansion interface: I2C
- GPIO expansion chip: PCF8574

## **Usager**
----------

- **1.Hardware connection**

1)Insert the two camera cables with the metal surface facing the heat sink into the camera interface on the Jetson Nano development kit 2)Start Jetson Nano

![IMX219-83 8MP 3D Stereo Camera Module for Jetson Nano Xavier NX 2.jpg](https://wiki.elecrow.com/images/thumb/e/ea/IMX219-83_8MP_3D_Stereo_Camera_Module_for_Jetson_Nano_Xavier_NX_2.jpg/600px-IMX219-83_8MP_3D_Stereo_Camera_Module_for_Jetson_Nano_Xavier_NX_2.jpg){ loading=lazy }

- **2.Test camera**

1\) Open the terminal (press Ctrl+ALT+T on the keyboard to open the terminal), enter the following command to see if the device is recognized normally.

```
ls / dev / video *
```

It is normal if video0 and video1 appear

2\) Test video0

```
DISPLAY=:0.0 gst-launch-1.0 nvarguscamerasrc sensor-id=0 ! 'video/x-raw(memory:NVMM), width=3280, height=2464, format=(string)NV12, framerate=(fraction)20/1' ! nvoverlaysink -e
```

3\) Test video1

```
DISPLAY=:0.0 gst-launch-1.0 nvarguscamerasrc sensor-id=1 ! 'video/x-raw(memory:NVMM), width=3280, height=2464, format=(string)NV12, framerate=(fraction)20/1' ! nvoverlaysink -e
```

If the camera shooting effect is reddish, you can follow the steps below: 1) Download the camera-override.isp file and unzip it to a specific folder

```
wget http://www.waveshare.net/w/upload/e/eb/Camera_overrides.tar.gz
tar zxvf Camera_overrides.tar.gz 
sudo cp camera_overrides.isp /var/nvidia/nvcam/settings/
```

2\) Installation files:

```
sudo chmod 664 /var/nvidia/nvcam/settings/camera_overrides.isp
sudo chown root:root /var/nvidia/nvcam/settings/camera_overrides.isp
```

- **Note**

1\) The 12 of NV12 is a number instead of a letter. 2) The test screen is output to the HDMI or DP screen, so you must first connect the screen to Jetson Nano when testing. 3) To test the sensor, connect the SDA and SCL pins of the camera to pins 3 and 5 of Jetson Nano, respectively 4)Open the terminal, download the sample program, and test

```
wget http://www.waveshare.net/w/upload/a/a4/D219-9dof.tar.gz
tar zxvf D219-9dof.tar.gz
cd D219-9dof/07-icm20948-demo
make
./ ICM20948 – Demo
```

Try rotating the camera to see the output value change.