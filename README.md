# Exploration-On-Pothole-Detection-Using-IOT-to-Help-People

A smart embedded system that utilizes **ultrasonic sensors**, an **ESP32 microcontroller**, and a **GSM module (SIM800L)** to detect objects or people falling into open pits and sends emergency SMS alerts to preconfigured numbers.


### Project Overview

This system is particularly useful for:
- Construction zones
- Open manholes
- Deep pits in industrial or municipal settings

###  Components Used

| Component               | Description                              |
|------------------------|------------------------------------------|
| ESP32                  | Microcontroller board (WiFi+BT capable)  |
| Ultrasonic Sensors (3) | Measures distance to detect obstacles    |
| SIM800L Module         | GSM module for sending SMS alerts        |
| Custom PCB             | Mounted all electronics securely         |
| Jumper Wires           | Wiring interconnections                  |
| Power Supply           | 5V regulated power                       |

---

###  Code Breakdown

####  'ultrasonic coding.txt'
- Simple distance measurement using one ultrasonic sensor.
- Prints readings in cm and inches via serial monitor.

####  '3 ultrasonic sensor.txt'
- Controls three ultrasonic sensors connected to ESP32 pins.
- GSM module sends SMS alerts when pit danger conditions are met.
- Alerts are condition-based:
  - Slight obstruction
  - Full obstruction
- Sends message to **two emergency contact numbers**.



###  System Logic

- Continuously measures distances using three ultrasonic sensors.
- Based on thresholds:
  - Sends SMS alert when objects are detected too close.
- Alerts reset after sending, waiting for new detections.


###  Setup Instructions

1. **Connect Hardware**:
   - Wire ultrasonic sensors to designated ESP32 GPIO pins.
   - Connect SIM800L via serial interface (TX/RX).
   - Power via 5V regulated supply.

2. **Upload Code**:
   - Use Arduino IDE with **ESP32 board support**.
   - Install libraries:
     - 'Ultrasonic.h'
   - Upload '3 ultrasonic sensor.txt' or 'ultrasonic coding.txt' based on your setup.

3. **Test**:
   - Open serial monitor at 9600 or 115200 baud (as per sketch).
   - Ensure SIM800L has a working SIM card with SMS balance.


###  Example SMS Alerts

'''
pit not much high, person no problem
pit much high & full closed the person, take action
'''



###  Folder Structure

'''
ultrasonic coding.txt
3 ultrasonic sensor.txt
README.md
'''

