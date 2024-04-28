---
title: Lesson03 How to Display Pictures on ESP32 Boards
---

## **Project Introduction：**
------

This project aims to demonstrate how to use an ESP32 development board and an RGB display to display images. It will show you how to read images from an SD card using the ESP32 development board and display them on the RGB screen.

## **Introduction to Knowledge Points:**
------

The key knowledge point is the print_img() function, which is used to display bitmap images on the screen. The syntax of this function is as follows:

```
   void LGFX_Sprite::print_img(int32_t SD, int32_t y, int32_t w, int32_t h);
   Where the parameters are defined as follows:
   SD: the SD card
   y: the position of the image
   w: the width of the bitmap
   h: the height of the bitmap
```

By using this function, you can read images from an SD card and display them on the screen. With the ESP32 development board and RGB screen, you can build various image display applications, such as digital photo frames and image galleries.

## **[Sample program](https://www.elecrow.com/wiki/index.php?title=File:ESP-Display-lesson3.zip):**
-------

The following is the basic program flow for ESP32 to read from the SD card and display pictures on the RGB screen:   
1.Import the required libraries. You need to import [LovyanGFX](https://drive.google.com/file/d/1w3Xt00C6rwhlHV74DnlwxJFm1X7UMR0W/view?usp=sharing), [Wire](https://wiki.elecrow.com/images/0/0c/ESP-Display-Wire.zip), [SPI](https://wiki.elecrow.com/images/b/b7/ESP-Display-SPI.zip), FS and [SD](https://wiki.elecrow.com/images/c/cf/ESP-Display-SD.zip) libraries.

```
#define LGFX_USE_V1
#include <LovyanGFX.hpp>
#include <Wire.h>
#include <SPI.h>
#include <SD.h>
#include <FS.h>
```

2.Define the constants used. Constants include SD card selection pins, LCD module pins, etc.

```
int sd_init_flag = 0;
#define SPI_MOSI 2 //1
#define SPI_MISO 41
#define SPI_SCK 42
#define SD_CS 1 //2
#define LCD_CS -1
#define LCD_BLK 46
#define I2C_SCL 39
#define I2C_SDA 38
```

3.Set up the SPI bus. In order to be able to communicate with the SPI bus, you need to define and initialize the SPI bus.

```
class LGFX : public lgfx::LGFX_Device
{
    lgfx::Panel_ILI9488 _panel_instance;
    lgfx::Bus_Parallel16 _bus_instance;
  public:
     //Create a constructor and make various settings here.
     // If the class name is changed, the constructor should also specify the same name.
    LGFX(void)
    {
      { //Set bus control.
        auto cfg = _bus_instance.config(); //Get the structure used for bus settings.
        // 16 bit settings
        cfg.port = 0; // Select which I2S port to use (0 or 1) (using ESP32's I2S LCD mode)
        cfg.freq_write = 20000000; // Send clock (up to 20MHz, 80MHz can be rounded to an integer)
        cfg.pin_wr = 18; // Connect the pin number of WR
        cfg.pin_rd = 48; // Connect the pin number of RD
        cfg.pin_rs = 45; // Connect the pin number of RS (D/C)

        cfg.pin_d0 = 47;
        cfg.pin_d1 = 21;
        cfg.pin_d2 = 14;
        cfg.pin_d3 = 13;
        cfg.pin_d4 = 12;
        cfg.pin_d5 = 11;
        cfg.pin_d6 = 10;
        cfg.pin_d7 = 9;
        cfg.pin_d8 = 3;
        cfg.pin_d9 = 8;
        cfg.pin_d10 = 16;
        cfg.pin_d11 = 15;
        cfg.pin_d12 = 7;
        cfg.pin_d13 = 6;
        cfg.pin_d14 = 5;
        cfg.pin_d15 = 4;

        _bus_instance.config(cfg);              // Reflect the set value on the bus.
        _panel_instance.setBus(&_bus_instance);
      }
      { // Set Display Panel Controls
        auto cfg = _panel_instance.config(); // Get the structure used to set the display panel.
        cfg.pin_cs = -1; // CS to be pulled low
        cfg.pin_rst = -1; // RST is associated with the development board RST
        cfg.pin_busy = -1; // Connect the pin number of BUSY (-1=disable)
        //※The settings below set common initial values on each panel
        cfg.memory_width = 320; // The maximum width supported by the driver IC
        cfg.memory_height = 480; // The maximum height supported by the driver IC
        cfg.panel_width = 320; // actual visible width
        cfg.panel_height = 480; // actual visible height
        cfg.offset_x = 0; // Panel X-direction offset
        cfg.offset_y = 0; // Panel Y offset
        cfg.offset_rotation = 0; // Offset of rotation direction value 0~7 (4~7 reverse up and down)
        cfg.dummy_read_pixel = 8; // Number of virtual read bits before pixel read
        cfg.dummy_read_bits = 1; // The number of dummy read bits before reading non-pixel data
        cfg.readable = true; // Set to true when data can be read
        cfg.invert = false; // Set to true if the panel's light and dark are reversed
        cfg.rgb_order = false; // If the red and blue in the panel are replaced with true
        cfg.dlen_16bit = true; // Set to true in the case of a panel that sends data length in units of 16 bits
        cfg.bus_shared = true; // Set to true when sharing the bus with the SD card (bus control via drawJpgFile etc.)
        _panel_instance.config(cfg);
      }
      setPanel(&_panel_instance); // Sets the panel to use.
    }
};
```

4.Initialize the LCD display. You need to specify the SPI pins and buses used before screen initialization, and perform screen initialization and screen clearing operations.

```
LGFX lcd;
SPIClass SD_SPI;
void setup() {
  // put your setup code here, to run once:
  Serial.begin(115200);

  //display screen
  lcd.init();
  //lcd.setSwapBytes(true);
  lcd.fillScreen(TFT_BLACK);
  delay(500);
  //Backlight pin initialization
  pinMode(LCD_BLK, OUTPUT);
  digitalWrite(LCD_BLK, HIGH);
  if (SD_init() == 0)
  {
    Serial.println("TF card initialized successfully");
    lcd.fillScreen(TFT_BLACK);
    lcd.setCursor(115, 230);
    lcd.println("TF card successfully mounted");
  } else {
    Serial.println("TF card initialization failed");
    lcd.fillScreen(TFT_BLACK);
    lcd.setCursor(115, 230);
    lcd.println("TF card failed to mount");
  }
  lcd.printf("Setup done");
  lcd.setRotation(7);
  lcd.fillScreen(TFT_BLACK);
}
```

5.SD card initialization program, as well as related supporting programs, you can check the source program provided by yourself.

```
int SD_init()
{
  SD_SPI.begin(SPI_SCK, SPI_MISO, SPI_MOSI);
  if (!SD.begin(SD_CS, SD_SPI, 40000000))
  {
    Serial.println("Card Mount Failed");
    return 1;
  }
  uint8_t cardType = SD.cardType();

  if (cardType == CARD_NONE)
  {
    Serial.println("No TF card attached");
    return 1;
  }

  uint64_t cardSize = SD.cardSize() / (1024 * 1024);
  Serial.printf("TF Card Size: %lluMB\n", cardSize);
  listDir(SD, "/", 2);
  return 0;
}
```

6.Load and display images. Loading and displaying images requires reading data from the SD card and sending the data to the display.

```
void loop() {
  print_img(SD, "/1.bmp", 480, 320);//Show SD card photos
  delay(5000);
}
```

**program effect:**    
![3-2.png](https://wiki.elecrow.com/images/thumb/3/3c/3-2.png/192px-3-2.png){ loading=lazy }

## **Expansion:**
------

switch multiple photos (the corresponding photos should be stored in the SD card, and the file names should be consistent).

```
void loop() {
  print_img(SD, "/1.bmp", 480, 320);//Show SD card photos
  delay(5000);
  print_img(SD, "/2.bmp", 480, 320);
  delay(5000);
  print_img(SD, "/3.bmp", 480, 320);
  delay(5000);
  print_img(SD, "/4.bmp", 480, 320);
  delay(5000);
  print_img(SD, "/5.bmp", 480, 320);
  delay(5000);
}
```

**program effect:**    
![3-3.png](https://wiki.elecrow.com/images/thumb/0/0d/3-3.png/191px-3-3.png){ loading=lazy }

## **HMI Display Tutorial Contents**

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- Lesson03 How to Display Pictures on ESP32 Boards
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](./lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- [Lesson09 How to make an analysis report on ESP32 Display](./lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](./lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](../../Tutorials/index.md)** 

## Resources
-----

[LovyanGFX](https://drive.google.com/file/d/1w3Xt00C6rwhlHV74DnlwxJFm1X7UMR0W/view?usp=sharing)  
[lesson3.zip](https://wiki.elecrow.com/images/3/39/ESP-Display-lesson3.zip)  