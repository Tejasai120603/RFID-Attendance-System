🎓 RFID Student Attendance System
An Arduino-based system to streamline student attendance management using RFID technology. It utilizes an MFRC522 RFID reader to authenticate ID cards, display student info on a 16x2 I2C LCD, and logs all activity via Serial Monitor for easy tracking and debugging.

✨ Key Features
✅ RFID Card Authentication
Scans and validates RFID UIDs using the MFRC522 module against a pre-defined database.

💬 Interactive LCD Display
Shows messages like "Scan ID card", student names, and "Present" status on a 16x2 I2C LCD.

🖥️ Real-time Serial Monitoring
Logs UID and attendance status to the Serial Monitor for transparency and debugging.

⚠️ Error Feedback
Displays "ID doesn't match" for unrecognized RFID cards on the LCD.

📋 Student Roster Management
Maps student names to their valid UIDs within the Arduino code.

⚙️ Hardware Requirements
Component	Quantity	Notes
Arduino Uno / Nano / Mega	1	Any compatible board
MFRC522 RFID Reader	1	For UID scanning
16x2 I2C LCD (PCF8574)	1	For display
RFID Cards/Tags	5+	For valid/invalid testing
Breadboard	Optional	For cleaner wiring
Jumper Wires	As needed	Male-to-Male / Male-to-Female
USB Cable	1	For Arduino connection

💻 Software Requirements
Arduino IDE (v1.8.19 or newer)

🔌 Required Libraries
Library	Author	Installation
SPI.h	Arduino	Pre-installed
Wire.h	Arduino	Pre-installed
MFRC522.h	UIPEthernet	Sketch > Include Library > Manage Libraries
LiquidCrystal_I2C.h	Frank de Brabander	Sketch > Include Library > Manage Libraries

🚀 Setup & Installation
1. 🔁 Clone the Repository
bash
Copy
Edit
git clone https://github.com/Tejasai120603/RFID-Attendance-System.git
cd RFID-Attendance-System
2. 🧠 Open in Arduino IDE
Launch Arduino IDE.

Open the sketch_may1a.ino file from the cloned directory.

3. 📚 Install Required Libraries
Ensure both MFRC522 and LiquidCrystal_I2C libraries are installed.

🔌 Hardware Wiring
🟢 MFRC522 RFID Reader → Arduino
RFID Pin	Arduino Pin
SDA (SS)	D10
SCK	D13
MOSI	D11
MISO	D12
RST	D9
GND	GND
3.3V	3.3V
IRQ	Not Used

🔵 16x2 I2C LCD → Arduino
LCD Pin	Arduino Pin
VCC	5V
GND	GND
SDA	A4
SCL	A5

📝 Note: Default I2C address is 0x27. If the LCD doesn't work, try 0x3F in this line:

cpp
Copy
Edit
LiquidCrystal_I2C lcd(0x27, 16, 2);
▶️ How to Run
Connect Arduino to your PC via USB.

In Arduino IDE:

Go to Tools > Board and select your board (e.g., Arduino Uno).

Go to Tools > Port and select the correct COM port.

Click the Upload (▶️) button to compile and flash the code.

🎯 Using the System
✅ Valid Card
LCD: Shows student name and "~ Present" for 3 seconds.

Serial Monitor: Logs UID and student name.

❌ Invalid Card
LCD: Shows "ID doesn't match" for 2 seconds.

Serial Monitor: Logs UID with no name.

🔁 Ready for Next Scan
After display, LCD resets to "Scan ID card" for the next input.

📟 To view logs: Open Serial Monitor (Tools > Serial Monitor) and set baud rate to 9600.

👥 Authors
Teja Sai Yallamelli

📞 Contact
Feel free to reach out for queries or collaboration:

📧 tejasairavikumar@gmail.com

🤝 Contributing
We welcome enhancements, suggestions, and contributions!
You can:

💡 Open an issue

📥 Submit a pull request

🛠 Suggest a new feature or fix

📄 License
This project is licensed under the MIT License.
See the LICENSE file for details.

