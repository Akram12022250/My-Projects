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
