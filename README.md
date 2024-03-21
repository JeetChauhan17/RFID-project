install dependencies: 
-  In order to install it, go to Sketch -> Include Libraries -> Manage libraries. Search for MFRC522 and install it. We also need the Adafruit SSD1306 library and the Adafruit GFX library for the display.
-  The Adafruit SSD1306 library needs a small modification. Go to the Arduino -> Libraries folder, open the Adafruit SSD1306 folder and edit the Adafruit_SSD1306.h library. Comment line 70 and uncomment line 69. Our display has a resolution of 128x64, that’s what we are defining here.
-  declare the card id here: int code[] = {69,141,8,136}; //This is the stored UID
