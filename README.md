# PROJECT 1: MEASURING SOIL MOISTURE CONTENT USING INTEL GALILEO GEN 2 


This project automates plant watering based on soil moisture levels using the Intel Galileo Gen 2 board. When the soil is dry, the system activates a water pump to irrigate the plants automatically.

## Components

- **Intel Galileo Gen 2 Board**
- **Soil Moisture Sensor**
- **Relay Module**
- **Water Pump with Motor**
- **Breadboard**
- **Jumper Wires**
- **Battery for the Motor**

## Project Overview

The soil moisture monitoring system reads the moisture levels in the soil using the sensor and compares it with a predefined threshold. If the moisture is below the threshold, it triggers the relay to turn on the water pump.

### Circuit Diagram

1. **Moisture Sensor:**
    - VCC: Galileo **5V**
    - GND: Galileo **GND**
    - A0: Galileo **Analog Pin A0**

2. **Relay Module:**
    - VCC: Galileo **5V**
    - GND: Galileo **GND**
    - IN: Galileo **Digital Pin D7**

3. **Water Pump:**
    - Connected to the relay's **NO** contact and powered by the battery.

4. **Power Supply:**
    - **Galileo**: Powered via USB or an external adapter.
    - **Pump**: Powered by a battery.

## Code

```cpp
// Define pin numbers
const int moistureSensorPin = A0; // Analog pin for moisture sensor
const int relayPin = 7;            // Digital pin for relay control

// Moisture threshold
const int moistureThreshold = 600; // Adjust based on calibration

void setup() {
  Serial.begin(9600);          // Initialize serial communication
  pinMode(relayPin, OUTPUT);   // Set relay pin as output
  digitalWrite(relayPin, HIGH); // Ensure pump is off initially (assuming relay is active LOW)
}

void loop() {
  int moistureLevel = analogRead(moistureSensorPin); // Read moisture level
  Serial.print("Moisture Level: ");
  Serial.println(moistureLevel);
  
  if (moistureLevel < moistureThreshold) {
    // Soil is dry, activate pump
    digitalWrite(relayPin, LOW); // Turn pump ON
    Serial.println("Pump ON");
  } else {
    // Soil is wet, deactivate pump
    digitalWrite(relayPin, HIGH); // Turn pump OFF
    Serial.println("Pump OFF");
  }
  
  delay(60000); // Wait for 60 seconds before next reading
}

