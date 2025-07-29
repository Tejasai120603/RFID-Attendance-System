🎓 RFID Student Attendance System
This Arduino-based system offers a streamlined solution for student attendance management. By leveraging an MFRC522 RFID reader, it efficiently scans student ID cards, authenticates their unique identifiers (UIDs) against a pre-configured database, and provides instant feedback on a 16x2 I2C LCD. All attendance events and scanned UIDs are meticulously logged to the Serial Monitor, ensuring robust record-keeping and facilitating debugging.

✨ Key Features
RFID Card Authentication: Reads and validates RFID card UIDs using the MFRC522 module against a predefined list.

Interactive LCD Display: Provides clear prompts ("Scan ID card"), displays student names, and confirms "Present" status on a 16x2 I2C LCD.

Real-time Serial Monitoring: Outputs detailed UID information and attendance status to the Serial Monitor for comprehensive logging and oversight.

Error Feedback: Clearly indicates "ID doesn't match" on the LCD for any unrecognized or invalid RFID cards.

Student Roster Management: Integrates a manageable list of student names directly correlated with their valid UIDs.

⚙️ Hardware Requirements
Arduino Uno (or a compatible board like Nano, Mega)

1x MFRC522 RFID Reader Module

1x 16x2 I2C LCD Display (with PCF8574 I2C adapter)

RFID Cards/Tags (minimum 5 for the pre-defined students, plus extras for testing)

Breadboard (optional, for organized prototyping)

Jumper Wires (Male-to-Male, Male-to-Female as required)

USB Cable (for connecting the Arduino to your PC)

💻 Software Requirements
Arduino IDE (Version 1.8.19 or newer recommended)

Essential Libraries:

SPI.h (Standard Arduino library, typically pre-installed)

Wire.h (Standard Arduino library for I2C communication, typically pre-installed)

MFRC522.h by UIPEthernet

Installation: In the Arduino IDE, navigate to Sketch > Include Library > Manage Libraries.... Search for "MFRC522" and install the library by "UIPEthernet" (or a widely compatible alternative).

LiquidCrystal_I2C.h by Frank de Brabander

Installation: In the Arduino IDE, go to Sketch > Include Library > Manage Libraries.... Search for "LiquidCrystal I2C" and install the library by "Frank de Brabander".

🚀 Setup and Installation
To get the project running locally, follow these steps:

Clone the repository:
Open your Git Bash or preferred terminal/command prompt. Navigate to your desired local directory and clone the project repository:

git clone https://github.com/Tejasai120603/RFID-Attendance-System.git
cd RFID-Attendance-System


Open in Arduino IDE:

Browse to the RFID-Attendance-System folder you just cloned.

Open the sketch_may1a.ino file within the Arduino IDE.

Install Libraries:

Ensure that both the MFRC522 and LiquidCrystal_I2C libraries are correctly installed in your Arduino IDE, as detailed in the "Software Requirements" section above.

Connect Hardware:

MFRC522 RFID Reader Module Wiring:

SDA (SS) ➡️ Arduino Digital Pin 10

SCK ➡️ Arduino Digital Pin 13

MOSI ➡️ Arduino Digital Pin 11

MISO ➡️ Arduino Digital Pin 12

IRQ (optional, not used in this sketch) - Leave unconnected

GND ➡️ Arduino GND

RST ➡️ Arduino Digital Pin 9

3.3V ➡️ Arduino 3.3V

16x2 I2C LCD Display Wiring:

VCC ➡️ Arduino 5V

GND ➡️ Arduino GND

SDA ➡️ Arduino Analog Pin A4

SCL ➡️ Arduino Analog Pin A5
(Important Note: The I2C address 0x27 is commonly used, but some LCDs might require 0x3F. If your LCD doesn't display anything, try changing 0x27 to 0x3F in the LiquidCrystal_I2C lcd(0x27, 16, 2); line within the code.)

▶️ How to Run
Upload to Arduino:

Connect your Arduino board to your computer using a USB cable.

In the Arduino IDE, go to Tools > Board and select your specific Arduino board (e.g., "Arduino Uno").

Then, go to Tools > Port and select the correct COM port corresponding to your connected Arduino board.

Click the "Upload" button (the right arrow icon) in the Arduino IDE to compile and transfer the sketch to your board.

Power On: Once the sketch is successfully uploaded and the Arduino board is powered, the LCD will illuminate and display "Scan ID card".

Scan Card: Gently present an RFID card or tag to the MFRC522 reader module.

Valid Card Recognition:

If the scanned card's UID matches one of the validUIDs defined in the Arduino code, the LCD will display the corresponding student's name on the first line and "~ Present" on the second line for approximately 3 seconds.

Simultaneously, the Serial Monitor will log the scanned UID and the associated student's name.

Invalid Card Indication:

If the scanned card's UID does not match any of the validUIDs, the LCD will display "ID doesn't match" for 2 seconds.

The Serial Monitor will still log the scanned UID, but no student name will be associated.

Ready for Next Scan: After displaying the attendance status (or error message), the LCD will automatically clear and revert to "Scan ID card", preparing for the next RFID scan.

Monitor Logs: To view detailed UID and attendance logs, open the Serial Monitor in the Arduino IDE (Tools > Serial Monitor) and ensure the baud rate is set to 9600.

👥 Authors
This project was developed by:

Teja Sai Yallamelli

📞 Contact
For inquiries or collaboration, feel free to reach out at:

tejasairavikumar@gmail.com

🤝 Contributing
We welcome contributions to enhance this project! If you have suggestions for improvements, new features, or discover any bugs, please feel free to:

Open an issue on GitHub.

Submit a pull request with your proposed changes.

📄 License
This project is open-source and licensed under the MIT License. For full details, please refer to the LICENSE file in the repository.
