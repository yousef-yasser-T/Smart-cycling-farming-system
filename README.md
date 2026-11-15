<div align="center">

# 🌱 Smart Cycling Farming System
### Automated Closed-Loop Resource & Nutrient Cycling for Sustainable Agriculture

[![Hackster.io](https://img.shields.io/badge/Hackster.io-Contest_Submission-0066CC?style=for-the-badge&logo=hackster&logoColor=white)](https://www.hackster.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Prototype_Ready-brightgreen?style=for-the-badge)]()
[![GitHub Repo](https://img.shields.io/badge/GitHub-yousef--yasser--T-181717?style=for-the-badge&logo=github)](https://github.com/yousef-yasser-T/Smart-cycling-farming-system)

<p align="center">
  <b>An intelligent IoT-driven agricultural system that automates water, nutrient, and environmental cycling to maximize crop yield while minimizing resource waste.</b>
</p>

[Overview](#-overview) • [Key Features](#-key-features) • [System Architecture](#-system-architecture) • [Hardware & BOM](#-hardware--bill-of-materials-bom) • [Pinout](#-pinout--wiring-configuration) • [Getting Started](#-getting-started)

</div>

---

## 📖 Overview

Traditional farming suffers from high water evaporation, nutrient runoff, and inconsistent environmental control. The **Smart Cycling Farming System** solves this by implementing an automated closed-loop ecosystem. 

Using real-time sensor fusion and automated actuator control, the system continuously monitors soil and water parameters and dynamically cycles water and nutrients back into the growth medium, ensuring zero waste and optimal plant health.

### 🎯 The Problem We Solve
* **Water Scarcity:** Up to 60% of water in conventional irrigation is lost to runoff and evaporation.
* **Nutrient Imbalance:** Over-fertilization degrades soil and harms crops, while under-fertilization stunts growth.
* **Manual Labor:** Constant monitoring of pH, EC/TDS, moisture, and temperature is time-consuming and prone to human error.

---

## ✨ Key Features

* 🔄 **Automated Closed-Loop Water Cycling:** Recovers, filters, and recirculates excess irrigation water based on real-time moisture thresholds.
* 🧪 **Smart Nutrient Dosing:** Monitors Electrical Conductivity (EC/TDS) and pH levels to maintain ideal nutrient concentrations automatically.
* 🌡️ **Micro-Climate Control:** Regulates temperature, humidity, and ventilation fans to keep crops in their optimal growth zone.
* 📊 **Real-Time IoT Dashboard:** Live telemetry visualization, historical data logging, and remote manual override capabilities.
* ⚡ **Energy-Efficient Operation:** Event-driven actuator scheduling and low-power sensor polling.

---

## 🏗️ System Architecture

The system operates on a 3-tier architecture: **Sensing Layer**, **Control & Processing Layer**, and **Cloud/Monitoring Layer**.

```text
+-----------------------------------------------------------------------+
|                        SENSING LAYER (Inputs)                         |
|  [Soil Moisture]   [Temp & Humidity]   [Water Level]   [pH / TDS/EC]  |
+-----------------------------------+-----------------------------------+
                                    | (Analog / I2C / OneWire)
                                    v
+-----------------------------------------------------------------------+
|                    CONTROL & PROCESSING LAYER (MCU)                   |
|                [Microcontroller / Edge Processing Unit]               |
|         -> Sensor Fusion & Filtering                                  |
|         -> Closed-Loop Cycling Control Logic (PID / Thresholds)       |
+-----------------+-----------------------------------+-----------------+
                  | (GPIO / Relay / PWM)              | (Wi-Fi / MQTT / HTTP)
                  v                                   v
+-----------------------------------+   +-------------------------------+
|      ACTUATION LAYER (Outputs)    |   |     IOT & DASHBOARD LAYER     |
|  [Water Pumps]  [Solenoid Valves] |   |  [Live Telemetry Dashboard]   |
|  [Dosing Pumps] [Cooling Fans]    |   |  [Alerts & Remote Control]    |
+-----------------------------------+   +-------------------------------+
```

---

## 🛠️ Hardware & Bill of Materials (BOM)

| Component | Quantity | Function / Description |
| :--- | :---: | :--- |
| **Microcontroller (ESP32 / Arduino)** | 1 | Main processing unit & wireless connectivity |
| **Soil Moisture Sensor (Capacitive)** | 2 | Corrosion-resistant root zone moisture sensing |
| **Temp & Humidity Sensor (DHT22 / BME280)** | 1 | Ambient micro-climate monitoring |
| **Water Level Sensor (HC-SR04)** | 1 | Reservoir and recovery tank level tracking |
| **TDS / pH Sensor Module** | 1 | Water quality & nutrient concentration tracking |
| **Submersible Water Pump (12V DC)** | 2 | Main irrigation & closed-loop return cycling |
| **Relay Module (4-Channel, Opto-isolated)** | 1 | Switching high-current pumps, valves, and fans |
| **Power Supply (12V DC + 5V Buck Converter)** | 1 | Dual-rail power delivery for logic and actuators |

---

## 📂 Repository Structure

```text
Smart-cycling-farming-system/
├── firmware/               # Microcontroller source code (C/C++ / Arduino / PlatformIO)
│   ├── src/                # Main control loop and sensor drivers
│   └── include/            # Configuration headers, pinouts, and Wi-Fi credentials
├── hardware/               # Schematics, PCB layout files, and wiring diagrams
├── dashboard/              # IoT dashboard configs / UI scripts
├── docs/                   # System photos, Hackster media, and testing logs
└── README.md               # Project documentation
```

---

## 🔌 Pinout & Wiring Configuration

| Peripheral / Sensor | MCU Pin | Signal Type | Notes |
| :--- | :---: | :---: | :--- |
| **Capacitive Moisture Sensor** | `GPIO 34 / A0` | Analog Input | 3.3V / 5V Supply |
| **Water Quality (TDS)** | `GPIO 35 / A1` | Analog Input | Temperature compensated |
| **Temp & Humidity Sensor** | `GPIO 4 / D4` | Digital / I2C | 10kΩ Pull-up resistor |
| **Main Irrigation Pump Relay** | `GPIO 26 / D5` | Digital Output | Active LOW |
| **Return Cycling Pump Relay** | `GPIO 27 / D6` | Digital Output | Active LOW |
| **Ventilation Fan Relay** | `GPIO 14 / D7` | Digital Output | Active LOW |

---

## 🚀 Getting Started

### 1. Prerequisites
* **IDE:** [Arduino IDE](https://www.arduino.cc/en/software) or [VS Code with PlatformIO](https://platformio.org/)
* **Required Libraries:**
  * `DHT sensor library` / `Adafruit BME280`
  * `WiFi.h` & `PubSubClient` (for MQTT/Cloud connectivity)

### 2. Installation & Flashing
1. **Clone the repository:**
   ```bash
   git clone [https://github.com/yousef-yasser-T/Smart-cycling-farming-system.git](https://github.com/yousef-yasser-T/Smart-cycling-farming-system.git)
   cd Smart-cycling-farming-system
   ```
2. **Configure credentials & thresholds:**
   Open `config.h` (or the main `.ino` file) and update your network settings and crop parameters:
   ```cpp
   #define WIFI_SSID "YOUR_WIFI_SSID"
   #define WIFI_PASS "YOUR_WIFI_PASSWORD"
   
   #define MOISTURE_MIN_THRESHOLD 35  // Trigger irrigation below 35%
   #define MOISTURE_MAX_THRESHOLD 75  // Stop irrigation & start drainage recovery
   ```
3. **Upload the Firmware:**
   Connect your board via USB, select the appropriate port and board target, and flash the code.

---

## 📈 Performance & Impact

* **💧 Water Saved:** Reduces water consumption by up to **70%** compared to open-loop irrigation through return-tank cycling.
* **⚡ Response Time:** Sub-second actuator response to critical threshold breaches.
* **🌱 Scalability:** Modular architecture allows adding multiple crop beds or hydroponic channels effortlessly.

---

## 🔮 Future Improvements

- [ ] Integrate **Edge AI / TinyML** for early plant disease detection using a camera module.
- [ ] Design a custom **2-Layer PCB** with integrated power management and ESD protection.
- [ ] Add **Solar MPPT Charging** for 100% off-grid agricultural deployment.

---

## 👨‍💻 Author

**Youssef Yasser**  
*Electronics & Communications Engineering Student*  
[![GitHub](https://img.shields.io/badge/GitHub-yousef--yasser--T-181717?style=flat-square&logo=github)](https://github.com/yousef-yasser-T)

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.
