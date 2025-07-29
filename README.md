RFID Student Attendance System
Project Description
This Arduino project implements a basic RFID-based student attendance system. It uses an MFRC522 RFID reader to scan student ID cards, validates their Unique Identifiers (UIDs) against a predefined list, and displays the student's name and attendance status ("Present") on a 16x2 I2C LCD. All scanned UIDs and attendance events are also logged to the Serial Monitor for debugging and record-keeping.

Features
Reads RFID card UIDs using the MFRC522 module.

Authenticates scanned UIDs against a pre-programmed list of valid student UIDs.

Displays "Scan ID card" prompt, student names, and "Present" status on a 16x2 I2C LCD.

Provides detailed UID information and attendance status on the Serial Monitor.

Indicates "ID doesn't match" on the LCD for unrecognized cards.

Manages a list of student names corresponding to valid UIDs.

Hardware Requirements
Arduino Uno (or compatible board like Nano, Mega)

1x MFRC522 RFID Reader Module

1x 16x2 I2C LCD Display (with PCF8574 I2C adapter)

RFID Cards/Tags (at least 5 for the predefined students, plus any others for testing)

Breadboard (optional, for easier connections)

Jumper Wires (Male-to-Male, Male-to-Female as needed)

USB Cable (for connecting Arduino to PC)

Software Requirements
Arduino IDE (Version 1.8.19 or newer recommended)

Libraries:

SPI.h (Standard Arduino library, usually pre-installed)

Wire.h (Standard Arduino library for I2C communication, usually pre-installed)

MFRC522.h by UIPEthernet (or similar MFRC522 library)

To install: In Arduino IDE, go to Sketch > Include Library > Manage Libraries.... Search for "MFRC522" and install the one by "UIPEthernet" (or the most popular/compatible one).

LiquidCrystal_I2C.h by Frank de Brabander

To install: In Arduino IDE, go to Sketch > Include Library > Manage Libraries.... Search for "LiquidCrystal I2C" and install the one by "Frank de Brabander".

Installation and Setup
Clone the Repository:
Open your Git Bash or terminal and navigate to your desired directory. Then clone this repository:

git clone https://github.com/Tejasai120603/RFID-Attendance-System)
cd RFID-Attendance-System

Open in Arduino IDE:

Navigate to the RFID-Attendance-System folder.

Open the sketch_may1a.ino file in the Arduino IDE.

Install Libraries:

Ensure the MFRC522 and LiquidCrystal_I2C libraries are installed in your Arduino IDE as described in the "Software Requirements" section.

Connect Hardware:

MFRC522 RFID Reader Module Wiring:

SDA (SS) to Arduino Digital Pin 10

SCK to Arduino Digital Pin 13

MOSI to Arduino Digital Pin 11

MISO to Arduino Digital Pin 12

IRQ (optional, not used in this sketch) - Leave unconnected

GND to Arduino GND

RST to Arduino Digital Pin 9

3.3V to Arduino 3.3V

16x2 I2C LCD Display Wiring:

VCC to Arduino 5V

GND to Arduino GND

SDA to Arduino Analog Pin A4

SCL to Arduino Analog Pin A5
(Note: The I2C address 0x27 is common, but some LCDs might use 0x3F. If your LCD doesn't work, try changing 0x27 to 0x3F in the LiquidCrystal_I2C lcd(0x27, 16, 2); line.)

Upload to Arduino:

Connect your Arduino board to your computer via USB.

In the Arduino IDE, go to Tools > Board and select your specific Arduino board (e.g., "Arduino Uno").

Go to Tools > Port and select the COM port corresponding to your Arduino board.

Click the "Upload" button (right arrow icon) in the Arduino IDE to compile and upload the sketch to your board.

Usage
Power On: Once the sketch is uploaded and the Arduino is powered, the LCD will display "Scan ID card".

Scan Card: Present an RFID card to the MFRC522 reader.

Valid Card:

If the card's UID matches one of the validUIDs in the code, the LCD will display the corresponding student's name on the first line and "~ Present" on the second line for approximately 3 seconds.

The Serial Monitor will also show the scanned UID and the student's name.

Invalid Card:

If the card's UID does not match any of the validUIDs, the LCD will display "ID doesn't match" for 2 seconds.

The Serial Monitor will still show the scanned UID, but no student name will be associated.

Next Scan: After displaying the status, the LCD will clear and return to "Scan ID card", ready for the next scan.

Serial Monitor: Open the Serial Monitor in the Arduino IDE (Tools > Serial Monitor) and set the baud rate to 9600 to view the UID and attendance logs.

Contributing
Contributions are welcome! If you have suggestions for improvements or find bugs, please open an issue or submit a pull request.

📞 Contact
For inquiries or collaboration, feel free to reach out at tejasairavikumar@gmail.com.
