# RFID Card Door Lock System with Arduino and OLED Display

This project implements a simple RFID card-based door lock system using Arduino, an OLED display, and a servo motor. It reads the Unique ID (UID) of each RFID tag placed close to the reader and displays it on the OLED display. If the UID of the tag matches a predefined value stored in Arduino's memory, an "Unlocked" message is displayed on the OLED display, granting access. If the UID does not match the predefined value, the "Unlocked" message won't appear.

## Parts Required

The following components are needed to build this project:
- Arduino Uno
- RFID Reader (RC522)
- OLED Display
- Small breadboard
- Wires

## Making Process

### Step 1: Get All the Parts

Ensure you have all the necessary components listed above.

### Step 2: The RC522 RFID Reader

Each RFID tag has a unique number (UID) that identifies it. This project uses the UID to identify specific cards.

### Step 3: The OLED Display

The OLED display used in this project has a resolution of 128x64 pixels and low power consumption. It communicates via the I2C interface, requiring only a few connections.

### Step 4: Connect All the Parts

Connect the RFID reader and OLED display to the Arduino as per the following connections:

#### RFID Reader - Arduino
- RST -> Digital Pin 9
- IRQ -> Unconnected
- MISO -> Digital Pin 12
- MOSI -> Digital Pin 11
- SCK -> Digital Pin 13
- SDA -> Digital Pin 10

#### OLED Display - Arduino
- Vcc -> 3.3V
- GND -> GND
- SCL -> Analog Pin 5
- SDA -> Analog Pin 4

**Note:** The RFID reader must be connected to the 3.3V output of the Arduino Uno to avoid damage.

## Usage

1. Connect all the components as described above.
2. Install the required libraries:
   - MFRC522 (for RFID reader)
   - Adafruit SSD1306 (for OLED display)
   - Adafruit GFX (required by SSD1306)
3. Upload the provided Arduino sketch (`RFID_Project.ino`) to your Arduino board.
4. Power up the project and place an RFID card close to the reader.
5. If the UID matches the predefined value, the OLED display will show an "Unlocked" message, granting access.


## install dependencies: 
-  In order to install it, go to Sketch -> Include Libraries -> Manage libraries. Search for MFRC522 and install it. We also need the Adafruit SSD1306 library and the Adafruit GFX library for the display.
-  The Adafruit SSD1306 library needs a small modification. Go to the Arduino -> Libraries folder, open the Adafruit SSD1306 folder and edit the Adafruit_SSD1306.h library. Comment line 70 and uncomment line 69. Our display has a resolution of 128x64, that’s what we are defining here.
-  declare the card id here: int code[] = {69,141,8,136}; //This is the stored UID


## Code

The Arduino sketch (`code.ino`) provided in this repository contains the code for the RFID card door lock system. It initializes the RFID reader and OLED display, reads RFID tags, compares the UID with a predefined value, and displays the access status on the OLED display.

## License

This project is licensed under the [MIT License](LICENSE).
