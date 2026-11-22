# ESP32-project-code-
ESP32 Based Industrial Machine Health Monitoring System

Project Description

This project is designed to monitor the health and operating conditions of an electric motor using an ESP32 microcontroller. It uses temperature, current, and vibration sensors to collect real-time motor data.

The measured values are displayed on a 16x2 LCD and uploaded to the ThingSpeak IoT cloud platform using Wi-Fi. A buzzer provides an alert when abnormal motor conditions are detected.

The ESP32 also provides a local web server API to access live sensor readings in JSON format.

Components Used

- ESP32 Development Board
- DS18B20 Temperature Sensor
- ADXL345 Accelerometer (Vibration Sensor)
- ACS712 Current Sensor
- 16x2 I2C LCD Display
- Buzzer
- Jumper Wires
- Power Supply

Hardware Connections

Component| ESP32 Pin
DS18B20 Data| GPIO 4
ADXL345 SDA| GPIO 21
ADXL345 SCL| GPIO 22
LCD SDA| GPIO 21
LCD SCL| GPIO 22
ACS712 OUT| GPIO 34
Buzzer| GPIO 18
I2C VCC| 3.3V
GND| GND


Software and Tools Used

- Arduino IDE
- ESP32 Board Package
- Basic C programming
- ThingSpeak IoT Platform
- Wi-Fi Communication
  
Library used

- OneWire Library
- DallasTemperature Library
- Adafruit Sensor Library
- Adafruit ADXL345 Library
- LiquidCrystal_I2C Library
- HTTPClient Library
- WebServer Library

Working Principle

1. ESP32 initializes all connected sensors and the LCD.
2. DS18B20 measures the motor temperature.
3. ACS712 measures the motor current.
4. ADXL345 detects motor vibration and acceleration.
5. ESP32 processes the sensor readings.
6. The LCD displays temperature, current, vibration, and motor health status.
7. The ESP32 checks sensor values against predefined safety limits.
8. If abnormal conditions are detected, the buzzer turns ON.
9. ESP32 uploads sensor data to ThingSpeak through Wi-Fi every 20 seconds.
10. ThingSpeak displays the uploaded readings through real-time graphs.

ThingSpeak IoT Cloud Monitoring

ThingSpeak is used as the cloud platform for remote motor monitoring.

ThingSpeak Channel Fields

Field| Parameter
Field 1| Temperature (°C)
Field 2| Current (A)
Field 3| Vibration (m/s²)

ThingSpeak Features

- Real-time sensor data monitoring.
- Graphical representation of sensor readings.
- Cloud-based data storage.
- Remote motor monitoring through the internet.
- Monitoring of motor alarm and sensor error status.

Local Web Server API

The ESP32 also runs a local web server on port 80.

API Endpoint:
"http://ESP32_IP_ADDRESS/data"

It provides sensor readings in JSON format, including:

- Temperature
- Current
- Vibration
- Temperature sensor error


Motor Health Monitoring and Safety Limits

The program uses the following predefined thresholds:

Parameter| Maximum Limit
Temperature| 60°C
Current| 3A
Vibration| 8 m/s²

If any limit is exceeded, or a sensor error is detected, the buzzer turns ON and the motor status changes to WARNING.


Main Features

- Real-time temperature monitoring.
- Motor current monitoring.
- Vibration monitoring.
- LCD-based data display.
- Automatic abnormal-condition detection.
- Buzzer-based warning system.
- Wi-Fi connectivity.
- ThingSpeak cloud integration.
- Local web server API.
- Remote monitoring of motor parameters.

Applications

- Industrial motor health monitoring.
- Predictive maintenance.
- Electrical machine monitoring.
- Industrial automation.
- Machine condition monitoring.

Future Scope

- Automatic motor shutdown using a suitable protection circuit.
- AI-based predictive maintenance.
- Mobile application integration.
- SMS and email alerts.
- Advanced fault detection.

Conclusion

The ESP32-based Industrial Machine Health Monitoring System provides real-time monitoring of motor temperature, current, and vibration. By integrating ThingSpeak, the system uploads sensor readings to the cloud for graphical visualization and remote monitoring. The buzzer provides an alert when abnormal operating conditions are detected, helping identify potential motor problems and supporting preventive maintenance.

Author

ENTC Engineering Project
