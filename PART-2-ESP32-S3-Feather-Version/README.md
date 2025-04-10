# PART 2 ESP32-S3 Feather Version

## Software 

Open ArduinoIDE and make sure you completed the setup in [Part0](https://github.com/SDSMT-EE120/Digital-Meter-Project/tree/main/Part0-Setup) of Digital-Meter-Project (Starting next week, we will continue with designing the meter, first we want to make sure you understand the difference between the Arduino and ESP32)

You will also need to add the following Libary in order to complete this section. 

To add a new library go to the menu on the left side of the screen and select **Library Manager**.

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

Coming Soon 

## Functionality

- Reads the Temperature sensor value 

- Convert to °C (Review Helpers at the bottom)

- Turns on LED if Temp > 30°C

- Display temperature on TFT screen with graphical icons, color, etc

### TFT Screen Display Functionality

- Change color when Temp > 30°C

- Display warning in red when too hot

## Code: 

The point of this assignment is not to learn how to code in C.  I have provided the code for writing to and using the TFT display.  Before implementing your part, you should review this code and understand how it works.  

Your part is to create the logic of

1. When the temperature is above 30°C turn the LED on 

2. Displays the temperature on the display 

3. Convert sensor data to a Value. 

## Deliverables for Part 1

Demonstrate to the TA or the Professor the system working. (10 PT)

Turn your Microcontroller into the bin at the front of the class to be wiped.

## Helpers 

[TFT Documentation](https://learn.adafruit.com/esp32-s3-reverse-tft-feather/built-in-tft)

[Pins and Use](https://learn.adafruit.com/esp32-s3-reverse-tft-feather/pinouts)

When reading from an analog sensor using a microcontroller, the sensor provides a voltage signal that is interpreted by the microcontroller's analog-to-digital converter (ADC). Most microcontrollers use a 10-bit ADC, which converts the analog voltage into a digital value ranging from 0 to 1023. This value is a representation of the input voltage relative to the reference voltage of the system (usually 5V or 3.3V, depending on the microcontroller).

To calculate the actual voltage output from the sensor, use the following equation:

    V = Sensor_Value * (V_ref / 1023.0)

Where 

- Sensor_Value is the raw analog reading from the microcontroller (0 to 1023)

- V_ref is the reference voltage of the ADC (commonly 5.0V)

- V is the calculated voltage from the sensor

The analog sensor outputs 0.5V at 0°C and increases linearly at 10 mV/°C, you can convert the voltage to temperature using the:

    C = (V - 0.5) * 100

Where 

- V is the voltage calculated from the previous step

- 0.5 is the voltage offset corresponding to 0°C

- 100 scales the voltage change to °C (since 10 mV/°C = 0.01 V/°C, and 1 / 0.01 = 100)

This will yield the temperature in degrees Celsius.