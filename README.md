Smart incubator CSI251
This project is a Auto Planting Chamber that automatesmonitoring and control of a garden environment. It uses sensors to measure soil moisture, light , temperature, and humidity, and controls devices like a water pump and LEDs based on the sensor data. The system also integrates with MQTT for remote monitoring and control.

Features
Soil Moisture Monitoring: Measures soil moisture levels and controls a water pump to maintain optimal moisture.

Light Intensity Monitoring: Adjusts LED brightness based on ambient light levels.

Temperature and Humidity Monitoring: Uses a DHT11 sensor to measure environmental conditions.

MQTT Integration: Publishes sensor data to an MQTT broker and subscribes to control topics for remote management.

Manual and Auto Modes: Allows manual control of the pump and LEDs or automatic operation based on sensor readings.

Hardware Requirements
ESP32-S3

Soil Moisture Sensor

DHT11 Temperature and Humidity Sensor

LDR (Light Dependent Resistor)

Water Pump

Relays (for pump and power control)

LEDs

Resistors and connecting wires

Power supply

Pin Configuration
Component	Pin
Soil Moisture Sensor	GPIO5
DHT22 Sensor	GPIO15
LDR Sensor	GPIO7
Water Pump Relay	GPIO12
Main Power Relay	GPIO39
External Power Relay	GPIO38
Red LED	GPIO42
Yellow LED	GPIO41
Green LED	GPIO40
Push Button	GPIO2

Software Requirements
MicroPython firmware
umqtt.simple library for MQTT
dht library for DHT11 sensor
neopixel library 
ssd1306 libraly for OLED
Node red for API connection

Installation
Flash MicroPython:

Download and flash the MicroPython firmware to your ESP32.


Upload Code:

Upload the provided Python script to your ESP32 using a tool like Thonny IDE.

Install Libraries:

Ensure the required libraries are installed on your ESP32.

Configure Wi-Fi:

Update the WIFI_SSID and WIFI_PASS variables in the code with your Wi-Fi credentials.

Configure MQTT:

Update the MQTT_BROKER, MQTT_USER, and MQTT_PASS variables with your MQTT broker details.

Usage
Power On:

Connect the hardware as per the pin configuration and power on the system.

MQTT Topics:

The system publishes sensor data to the following topics:

Soil Moisture: b6710504310/sensor/soil_moisture

Light Intensity: b6710504310/sensor/ldr

Temperature and Humidity: b6710504310/sensor/dht22

The system subscribes to the following control topics:

Pump Control: b6710504310/pump_control

LED Control: b6710504310/led_control

Target Light: b6710504310/target_light

Pump Mode: b6710504310/pump_mode

Light Mode: b6710504310/light_mode

Auto Mode:

In auto mode, the system automatically controls the pump and LEDs based on sensor readings.

Manual Mode:

Use MQTT messages to manually control the pump and LEDs.

MQTT Commands
Pump Control:

Topic: b6710504310/pump_control

Message: 1 (turn on) or 0 (turn off)

LED Control:

Topic: b6710504310/led_control

Message: 1 (turn on) or 0 (turn off)

Target Light:

Topic: b6710504310/target_light

Message: Desired light level (e.g., 500)

Pump Mode:

Topic: b6710504310/pump_mode

Message: auto or manual

Light Mode:

Topic: b6710504310/light_mode

Message: auto or manual

Troubleshooting
No Sensor Data:

Check the wiring and ensure the sensors are properly connected.

Verify that the correct pins are used in the code.

MQTT Connection Issues:

Ensure the Wi-Fi credentials and MQTT broker details are correct.

Check if the MQTT broker is reachable.

Pump/LED Not Working:

Check the relay connections and ensure the relays are functioning.

Verify the control logic in the code.

License
This project is licensed under the MIT License.

Copyright (c) 2025 413_content_too_large

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Acknowledgments
Thanks to MicroPython for the firmware.

Thanks to umqtt.simple for the MQTT library.

