# PART 1: Arduino Uno Version (in TinkerCAD)

## Software

Open TinkerCAD and create a project. 

## Components

- 1 x Arduino Uno 

- 1 x Temperature Sensor (TMP36)

- 1 x LED 

- 1 x 220 Ω resistor

- 1 x 16x2 LCD Display (NOT I2C)

- 1 x Potentiometer 

- 1 x Breadboard

## Building 

Using the components above create the circuit below. To receive full credit your circuit should look identical to the design below.

![TinkerCad Circuit](/PART-1-Arduino-Uno-Version/assets/images/Tinkercad_Circuit.png)

## Functionality: 

- Reads temperature from TMP36

- Convert to °C (Review Helpers at the bottom)

- Turns on LED if temp > 30°C

- Display temperature on external LCD 

## Code: 

The point of this assignment is not to learn how to code in C.  I have provided the code for writing to and using the LCD display.  Before implementing your part, you should review this code and understand how it works.  

Your part is to create the logic of

1. When the temperature is above 30°C, turn the LED on 

2. Displaying the temperature on the LCD 

3. Convert sensor data to a Value. 

## Deliverables for Part 1

Demonstrate to the TA or the Professor the system working. (10 Pt)

In TinkerCAD add to Classes, EE120, Smart Weather Dashboard


## Helpers 

[Programming Guide](https://docs.arduino.cc/programming/) - Can find important Libraries and more. 

[Language Reference](https://docs.arduino.cc/language-reference/) -Can find important functions like pinMode() and the read/write functions.

When reading from an analog sensor using a microcontroller, the sensor provides a voltage signal that is interpreted by the microcontroller's analog-to-digital converter (ADC). Most microcontrollers use a 10-bit ADC, which converts the analog voltage into a digital value ranging from 0 to 1023. This value is a representation of the input voltage relative to the reference voltage of the system (usually 5V or 3.3V, depending on the microcontroller).

To calculate the actual voltage output from the sensor, use the following equation:

    V = Sensor_Value * (V_ref / 1023.0)

Where 

- Sensor_Value is the raw analog reading from the microcontroller (0 to 1023)

- V_ref is the reference voltage of the ADC (5.0V for the Uno)

- V is the calculated voltage from the sensor

The analog sensor outputs 0.5V at 0°C and increases linearly at 10 mV/°C, you can convert the voltage to temperature using the:

    C = (V - 0.5) * 100

Where 

- V is the voltage calculated from the previous step

- 0.5 is the voltage offset corresponding to 0°C

- 100 scales the voltage change to °C (since 10 mV/°C = 0.01 V/°C, and 1 / 0.01 = 100)

This will yield the temperature in degrees Celsius.
