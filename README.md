# Fire Detection and Alert System

This Arduino-based project detects fire through temperature (LM35) and smoke (MQ-2) sensors and sends SMS alerts with GPS coordinates using a GSM module. The system also activates alarms and displays real-time status on an LCD.

## Features

- Detects fire based on temperature and smoke levels.
- Alerts through visual indicators (LEDs) and an audible alarm (speaker).
- Sends SMS alerts with GPS location to pre-configured phone numbers.
- Displays real-time status on an LCD.
- Servo motor control for additional physical responses (e.g., unlocking emergency exits).

## Components

- Arduino (UNO or similar)
- LM35 temperature sensor
- MQ-2 smoke sensor
- Servo motor
- 16x2 LCD display
- GPS module (TinyGPS library used)
- GSM module for SMS alerts
- LED indicators (Red, Yellow)
- Buzzer/Speaker
- Relay module
- Jumper wires
- Breadboard or custom PCB

## Pin Configuration

| Component        | Pin Connection |
|------------------|----------------|
| LM35 Sensor      | A0             |
| MQ-2 Sensor      | A1             |
| Servo Motor      | 13             |
| LCD Display      | 12, 11, 5, 4, 3, 2 |
| GPS (RX, TX)     | 9, 10          |
| GSM Module       | Serial (TX, RX)|
| Speaker          | 6              |
| LED Red          | 7              |
| LED Yellow       | 10             |
| Relay            | 7              |

## How It Works

1. **Sensors**: The system continuously reads data from the LM35 and MQ-2 sensors.
2. **Threshold Check**: If the temperature exceeds 50°C or the smoke level is above the preset threshold, the system:
   - Activates a relay (e.g., to trigger an external system).
   - Turns on the red and yellow LEDs.
   - Moves the servo motor.
   - Displays a "FIRE ALERT" message on the LCD.
   - Sounds an audible alarm.
3. **SMS Alert**: An SMS containing a fire alert and GPS coordinates is sent to the configured phone number using the GSM module.
4. **Normal State**: If no fire is detected, the system displays "NO FIRE" on the LCD, and all outputs remain off.

## Prerequisites

- **Arduino IDE**: Download and install the [Arduino IDE](https://www.arduino.cc/en/Main/Software).
- **Libraries**: Install the following libraries:
  - `Servo.h`
  - `LiquidCrystal.h`
  - `TinyGPS.h`
  - `SoftwareSerial.h`

### Library Installation

1. Open the Arduino IDE.
2. Go to `Sketch` > `Include Library` > `Manage Libraries`.
3. Search for the libraries (`Servo`, `LiquidCrystal`, `TinyGPS`, `SoftwareSerial`) and click `Install`.

## Code

```cpp
// Complete source code is available in the repository
#include <Servo.h>
#include <LiquidCrystal.h>
#include <TinyGPS.h>
#include <SoftwareSerial.h>

// Additional code...
