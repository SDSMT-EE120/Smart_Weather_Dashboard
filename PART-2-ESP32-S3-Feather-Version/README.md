# PART 2 ESP32-S3 Feather Version

## Software 

Open ArduinoIDE and make sure you completed setup in [Part0](https://github.com/SDSMT-EE120/Digital-Meter-Project/tree/main/Part0-Setup) of Digital-Meter-Project (Starting next week, we will continue with designing the meter, first we want to make sure you understand the difference between the Arduino and ESP32)

You will also need to add the following Libary in order to complete this section. 

To add a new libary go to the menu on the left side of the screen and select **Library Manager**.

![Library Manager](/PART-2-ESP32-S3-Feather-Version/assets/images/IDE_Libaray.png)

In the search box enter the following and click install.

- Adafruit_GFX

- Adafruit_ST7789

- Adafruit_NeoPixel

![Library Search](/PART-2-ESP32-S3-Feather-Version/assets/images/IDE_Library_Search.png)


## Components

- 1x Adafruit ESP32-S3 REV TFT

- Temperature Sensor [Datasheet]()

- Various Wires 

## Building 

Comming Soon 

## Functionality

- Reads the Temperature sensor value 

- Convert to °C (Review Helpers at the bottom)

- Turns on LED if Temp > 30°C

- Display temperature on TFT screen with graphical icons, color, etc

### TFT Screen Display Functionality

- Change color when Temp > 30°C

- Display warning in red when too hot

## Code: 

As the point of this assignment is not to learn how to code in C.  I have provided the code for writing to and using the TFT display.  Before implementing your part, you should review this code and understand how it works.  

Your part is to create the logic of

1. When tempature is above 30°C turns LED on 

2. Displays the tempature on the display 

3. Convert sensor data to a Value. 

## Deliverables for Part 1

Demonstrate to the TA of Professor the system working.

Turn your Microcontroller into the bin at the front of the class to be wiped.