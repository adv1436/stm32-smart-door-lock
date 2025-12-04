# STM32-Based Smart Door Lock

## Overview
This project implements an RFID and keypad-based smart door lock system using the STM32F103C8T6 microcontroller. It uses dual-layer authentication, where both an RFID tag and a password must be verified before access is granted. The system was developed as part of the course "Microprocessor, Microcontroller and Interfacing Techniques (21ECC301P)".

## Hardware Components
- STM32F103C8T6 (Blue Pill) microcontroller
- RC522 RFID module
- RFID tags/cards
- 4x4 matrix keypad
- SG90 servo motor (lock/unlock mechanism)
- Red and green LEDs (status indication)
- Buzzer (audio feedback)
- 5 V power supply / mobile power bank
- Breadboard and jumper wires

## System Operation
1. On power-up, STM32 initializes all peripherals (RFID, keypad, servo, LEDs, buzzer).
2. The RC522 RFID module scans an RFID tag and sends its UID to STM32 over SPI.
3. If the UID matches a stored authorized ID, the system prompts the user to enter a password via the keypad.
4. The entered password is compared with a stored reference in memory.
5. If both RFID and password are correct:
   - Green LED turns ON
   - Buzzer gives a short beep
   - Servo motor rotates to the unlock position (e.g., 90°)
6. If either RFID or password is incorrect:
   - Red LED turns ON
   - Buzzer gives a long beep
   - Servo remains in the locked position (0°)
7. After a short delay, the system auto re-locks and returns to idle for the next user.

## Software & Tools
- Arduino IDE (with STM32 board support)
- MFRC522 library for RFID tag reading
- Keypad library for 4x4 keypad scanning
- Servo library for PWM-based servo control
- SPI and GPIO for peripheral communication
- ST-LINK V2 (for programming and debugging)

## Features
- Dual-factor authentication (RFID + password)
- Real-time control with low power consumption
- Visual (LED) and audio (buzzer) feedback for access status
- Auto re-locking after successful entry
- Prototype validated with multiple valid/invalid test cases

## Applications
- Smart home access control
- Office and laboratory door security
- Educational demonstration of embedded security systems

## Documentation
- Full project report: `RFID_Keypad_Smart_Door_Lock_STM32_Report.pdf`

## Author
Advait Madhusudan

