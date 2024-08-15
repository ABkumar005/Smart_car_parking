# Arduino Parking System with LCD and Servo

# Overview
This project implements a parking management system using an Arduino, an LCD display, a servo motor, and infrared (IR) sensors. The system monitors parking slots and controls a gate mechanism based on slot availability. The LCD provides user feedback, and the servo operates as the gate.

# Components Used

Arduino Board: Any Arduino board (e.g., Arduino Uno, Nano)

LCD Display: 16x2 I2C LCD

Servo Motor: Standard servo motor

IR Sensors: Two infrared sensors for detecting vehicle presence

Resistors: For IR sensors

Wiring and Connectors: For connecting components

# Circuit Diagram

IR Sensors:

IR1: Connected to Arduino pin 2

IR2: Connected to Arduino pin 3

Servo Motor:

Control Pin: Connected to Arduino pin 4

LCD Display:

SDA Pin: Connected to Arduino A4 (for Uno)

SCL Pin: Connected to Arduino A5 (for Uno)

# Code Explanation

Libraries

Wire.h: Provides I2C communication support.

LiquidCrystal_I2C.h: Controls the LCD display.

Servo.h: Controls the servo motor.'

# Pin Definitions
IR1: Pin for the first IR sensor (detects entry).

IR2: Pin for the second IR sensor (detects exit).

Slot: Tracks the total number of available parking slots.

Setup Function

Initializes the LCD display.

Sets up IR sensors as inputs.

Attaches and positions the servo motor.

Loop Function

Entry Detection:


When the first IR sensor (IR1) detects a vehicle and parking slots are available, it opens the gate (moves the servo to 0 degrees) and decreases the available slots.
If no slots are available, it displays a "Parking Full" message on the LCD.
Exit Detection:

When the second IR sensor (IR2) detects a vehicle and there are vehicles in the parking lot, it opens the gate and increases the available slots.
Reset:

After processing an entry or exit, the servo moves back to its default position (100 degrees), and flags are reset.
LCD Display:

Continuously displays the number of available slots.
Usage
Upload the Code: Load the provided Arduino code onto your Arduino board using the Arduino IDE.

Connect Components: Wire the components according to the circuit diagram.

Power the System: Ensure the Arduino and all components are powered correctly.

Run the System: The parking system will start monitoring the parking slots and update the LCD display accordingly.

# Troubleshooting

LCD Not Displaying: Check the wiring connections and ensure the I2C address of the LCD is correct.

Servo Not Working: Verify the servo connection and power supply.

IR Sensors Not Responding: Ensure the sensors are aligned correctly and check for any wiring issues.

# Code Customization

Adjust Slot Count: Modify the Slot variable in the code to set the initial number of parking slots.

Change Servo Positions: Modify myservo.write() values to adjust the servo positions for opening and closing the gate.

# References

Arduino Servo Library Documentation

LiquidCrystal_I2C Library Documentation

# License

This project is licensed under the MIT License. See the LICENSE file for details.
