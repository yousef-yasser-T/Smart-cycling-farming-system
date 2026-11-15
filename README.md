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

[Overview](#-overview) • [Key Features](#-key-features) • [System Architecture](#-system-architecture) • [Hardware & BOM](#-hardware--bill-of-materials) • [Getting Started](#-getting-started)

</div>

---

## 📖 Overview

Traditional farming suffers from high water evaporation, nutrient runoff, and inconsistent environmental control. The **Smart Cycling Farming System** solves this by implementing an automated closed-loop ecosystem. 

Using real-time sensor fusion and automated actuator control, the system continuously monitors soil/water parameters and dynamically cycles water and nutrients back into the growth medium, ensuring zero waste and optimal plant health.

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
+-----------------------------------+   +-------------------------------+# Smart-cycling-farming-system
