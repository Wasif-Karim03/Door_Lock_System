# RFID-Based Door Lock System

## Overview
This project is an **RFID-based door lock mechanism** designed for controlled access to a lab or secure area. Authorized users can unlock the door using pre-registered RFID cards. The system utilizes an **RFID module, a servo motor for locking and unlocking, an OLED display for status updates, and a buzzer for access notifications**.

## Features
✅ **Secure Access** - Only authorized RFID cards can unlock the door.<br>
✅ **OLED Display** - Displays system status and access messages.<br>
✅ **Buzzer Alerts** - Provides auditory feedback for access granted or denied.<br>
✅ **Servo-Controlled Lock** - Automatically locks the door after a set time.<br>
✅ **Easy Expansion** - Add or remove authorized RFID cards easily in the code.<br>

## Components Used
- **Arduino Board** (e.g., Arduino Uno)
- **MFRC522 RFID Module**
- **Servo Motor** (for door lock mechanism)
- **OLED Display (SSD1306)**
- **Buzzer**
- **Jumper Wires & Breadboard**

## Circuit Diagram
Ensure the components are connected as follows:
- **RFID Module**
  - SS -> Pin 10
  - RST -> Pin 9
  - MOSI -> Pin 11
  - MISO -> Pin 12
  - SCK -> Pin 13
- **Servo Motor** -> Pin 8
- **Buzzer** -> Pin 7
- **OLED Display (I2C)** -> SDA & SCL to Arduino I2C Pins

## How It Works
1. The system initializes and displays "System Ready" on the OLED screen.
2. Users scan their RFID cards.
3. If the card UID matches an **authorized card**, access is granted:
   - OLED displays "Access Granted!"
   - Buzzer beeps twice
   - Servo unlocks the door for 5 seconds, then relocks.
4. If the card is **unauthorized**, access is denied:
   - OLED displays "Access Denied!"
   - Buzzer emits a long beep
5. The system resets and waits for the next scan.

## Code Explanation
- **Authorized RFID Cards**: Stored as an array in the code.
- **RFID Module**: Detects and reads card UID.
- **Servo Control**: Unlocks the door when access is granted.
- **Buzzer Feedback**: Short beeps for success, long beep for failure.
- **OLED Display**: Shows status messages.

## Installation & Setup
1. **Download & Install Required Libraries**:
   - `MFRC522`
   - `Servo`
   - `Adafruit_GFX`
   - `Adafruit_SSD1306`
2. **Upload the code to Arduino** using the Arduino IDE.
3. **Connect the components** as per the circuit diagram.
4. **Power up the system** and test with RFID cards.

## Customization
- To **add a new card**, find its UID in the Serial Monitor and update the `authorizedCards` array.
- Modify the **servo angle** to match your door lock mechanism.
- Adjust the **buzzer sound duration** in the `grantAccess()` and `denyAccess()` functions.

## Future Enhancements
🔹 **WiFi Connectivity** - Log access data online.<br>
🔹 **Keypad Integration** - Backup PIN entry option.<br>
🔹 **Mobile App Control** - Manage access remotely.<br>

## License
This project is open-source and free to use for educational and personal projects.


