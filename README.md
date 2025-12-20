# Bora – ESP32 Weather Station 🌬️

**Bora** is a DIY outdoor weather station based on ESP32 and ESPHome.  
It measures a full set of environmental parameters and integrates seamlessly with Home Assistant.

---

## 🌟 Features

- Temperature, humidity, and pressure (BME280)  
- Light intensity (BH1750)  
- Air quality – PM1, PM2.5, PM10 (PMS5003)  
- Wind speed and direction  
- Rainfall (tipping bucket rain gauge)  
- Lightning detection (AS3935)  
- Home Assistant integration  
- Alerts and data visualization in HA dashboards

---

## 🛠️ Hardware

- **ESP32-WROOM-32D**  
- **BME280** – temperature, humidity, pressure  
- **BH1750** – light intensity  
- **PMS5003** – particulate matter PM1/PM2.5/PM10  
- **AS3935** – lightning detector  
- **Anemometer + wind vane** – wind speed and direction  
- **Tipping bucket rain gauge** – rainfall

---

## 🔌 Power Supply

- ESP32: 3.3 V regulated  
- PMS5003: 5 V (dedicated step-down recommended, ≥1A)  

> Note: PMS5003 requires airflow and cannot be enclosed in a sealed box.

---

## 💻 Software

- **ESPHome** – firmware for ESP32  
- **Home Assistant** – dashboard, charts, and automations

---

## 📁 Repository Structure

```text
bora-weather-station/
├── README.md
├── docs/
│   ├── overview.md
│   ├── hardware.md
│   └── sensors.md
├── esphome/
│   ├── bora.yaml
│   └── secrets.yaml.example
├── schematics/
│   └── bora-block-diagram.png
├── images/
│   └── bora-mounted.jpg
└── LICENSE
