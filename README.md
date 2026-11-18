# Smart Product Storage Monitoring Using KiwisIoT

## Project Overview
This project monitors temperature and humidity inside product storage areas using a NodeMCU ESP8266 and DHT11 sensor. It collects environmental readings, checks them against configured limits, and sends the data to the KiwisIoT platform for remote monitoring.

## Hardware Components
- NodeMCU ESP8266
- DHT11 Temperature and Humidity Sensor
- Jumper Wires
- Power Supply

## Software Requirements
- Arduino IDE
- ESP8266 Board Package
- KiwisIoT Arduino Library
- DHT Sensor Library

## Circuit Connections

| DHT11 Sensor | NodeMCU ESP8266 |
|---|---|
| VCC | 3.3V |
| GND | GND |
| DATA | D2 |

For a bare DHT11 sensor, connect an appropriate pull-up resistor between DATA and VCC.

## Working Principle
The DHT11 sensor measures the surrounding temperature and humidity. The ESP8266 reads the values every 3 seconds and compares them with the configured limits.

If temperature exceeds 30°C or humidity exceeds 70%, the storage status becomes ALERT. Otherwise, it remains NORMAL. The readings and status are uploaded to KiwisIoT.

## KiwisIoT Dashboard

| Channel | Data |
|---|---|
| Channel 0 | Temperature (°C) |
| Channel 1 | Humidity (%) |
| Channel 2 | Storage Status (NORMAL / ALERT) |

## Configuration
Update your Wi-Fi credentials and KiwisIoT Topic ID in the Arduino code:

```cpp
const char* ssid = "YOUR_WIFI_NAME";
const char* pass = "YOUR_WIFI_PASSWORD";
const char* topic = "YOUR_TOPIC_ID";
```

You can customize the monitoring limits:

```cpp
const float TEMP_LIMIT = 30.0;
const float HUMIDITY_LIMIT = 70.0;
```

Upload the code to the NodeMCU ESP8266 and monitor storage conditions through the KiwisIoT dashboard.

**Note:** The temperature and humidity limits are example values. Adjust them according to the products being stored.

## Applications
- Warehouse monitoring
- Food product storage
- Electronic component storage
- Pharmaceutical storage monitoring
- Agricultural product storage
- Inventory management

## Project Blog
[Read the full project on Hackster.io](https://www.hackster.io/kirusokumar/iot-based-product-storage-monitoring-using-kiwisiot-1a792e)

## Recommended Platform
[KiwisIoT – IoT Monitoring Platform](https://www.kiwisiot.in/)

**Arduino Library:** https://github.com/Kiwistron/KiwisIoT

**Example Projects:** https://github.com/Kiwistron/KiwisIoT-Projects/tree/main

---
**Author:** Kirusokumar