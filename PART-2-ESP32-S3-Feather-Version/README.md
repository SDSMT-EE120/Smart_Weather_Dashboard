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

- Temperature Sensor [Datasheet](https://cdn-learn.adafruit.com/downloads/pdf/tmp36-temperature-sensor.pdf)

- Various Wires 

## Building 

Connect output pin of Temp Sensor to any analog input of the Feather.  Connect to power and ground based off the Datasheet above. 

## Functionality

- Reads the temperature sensor value 

- Convert to °C (review Helpers at the bottom)

- Turns on LED if the measured temperature > 25°C

- Change temperature text color to red if Temp > 25°C

- Change thermometer icon graphic color to
    - **Blue** if the temperature is less than 21°C
    - **Yellow** if the temperature is between 21°C and 25 °C
    - **Red** if the temperature is over 25°C graphic is red 

## Code: 

The point of this assignment is not to learn how to code in C.  Starter code for writing to and using the TFT display is provided in [TFT_Code.c](https://github.com/SDSMT-EE120/Smart_Weather_Dashboard/blob/main/PART-2-ESP32-S3-Feather-Version/TFT_Code.c). Your job is to find the approrpiate sections of code (look for TODO comments) and create the logic to:

1. Convert the incoming sensor data voltage to an integer value. 
2. When the temperature is above 25°C turn the LED on 
3. Update the temperature and the icon color on the TFT display


## Deliverables for Part 1

Demonstrate to the TA or the Professor the system working as described in the Functionality section. (20 PT)

Turn your Microcontroller into the bin at the front of the class to be wiped.

## Helpers 

[TFT Documentation](https://learn.adafruit.com/esp32-s3-reverse-tft-feather/built-in-tft)

[Pins and Use](https://learn.adafruit.com/esp32-s3-reverse-tft-feather/pinouts)

When reading from an analog sensor using a microcontroller, the sensor provides a voltage signal that is interpreted by the microcontroller's analog-to-digital converter (ADC). ADCs are specified by the number of bits they output. An n-bit ADC converts the analog voltage into a digital integer ranging from 0 to 10^n. This value is a representation of the input voltage relative to the reference voltage of the system (usually 5V or 3.3V, depending on the microcontroller).

To calculate the actual voltage output from the sensor, use the following equation:

    V = Sensor_Value * (V_ref / 4096.0)

Where 

- Sensor_Value is the raw integer reading from the microcontroller's 12-bit ADC (0 to 4096)
- V_ref is the reference voltage of the ADC (3.3 Volt)
- V is the calculated voltage from the sensor

The analog sensor outputs 0.5V at 0°C and increases linearly at 10 mV/°C, so you can convert the voltage to temperature using this equation:

    C = (V - 0.5) * 100

Where 

- V is the voltage calculated from the previous step
- 0.5 is the voltage offset corresponding to 0°C
- 100 scales the voltage change to °C (since 10 mV/°C = 0.01 V/°C, and 1 / 0.01 = 100)

This will yield the temperature in degrees Celsius.
