CODE:
---
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

// ESP32-C3 I2C pin definitions
#define I2C_SDA 5    // GPIO5 for SDA
#define I2C_SCL 6    // GPIO6 for SCL
#define LED_PIN 7    // LED pin (built-in LED on most ESP32-C3 boards)
#define BUZZER_PIN 9    // LED pin (built-in LED on most ESP32-C3 boards)

Adafruit_SSD1306 display(128, 64, &Wire, -1);

void setup() {
  // Initialize LED pin
  pinMode(LED_PIN, OUTPUT);
  pinMode(BUZZER_PIN, OUTPUT);
  digitalWrite(BUZZER_PIN, LOW);
  
  // Initialize I2C with specific pins for ESP32-C3
  Wire.begin(I2C_SDA, I2C_SCL);
  
  // Initialize OLED display
  if(!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) {
    // If display fails, you can add error handling here
    while(1); // Stop if display doesn't work
  }
}

void loop() {
  // Turn LED ON for 5 seconds and display status
  digitalWrite(LED_PIN, LOW);
  digitalWrite(BUZZER_PIN, LOW);
  display.clearDisplay();
  display.setTextSize(2);
  display.setTextColor(SSD1306_WHITE);
  display.setCursor(0, 0);
  display.print("KAMALESP32");
  display.setCursor(0, 25);
  display.print("LED: OFF");
  display.setCursor(0, 50);
  display.print("BUZ:OFF");
  display.display();
  delay(2000);
  
  // Turn LED OFF for 2 seconds and display status
  digitalWrite(LED_PIN, HIGH);
  digitalWrite(BUZZER_PIN, HIGH);
  display.clearDisplay();
  display.setTextSize(2);
  display.setTextColor(SSD1306_WHITE);
  display.setCursor(0, 0);
  display.print("KAMALESP32");
  display.setCursor(0, 25);
  display.print("LED: ON");
  display.setCursor(0, 50);
  display.print("BUZ:BEEP");
  display.display();
  delay(2000);
}
