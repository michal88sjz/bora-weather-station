# Bora – ESP32 Weather Station 🌬️

**Bora** is a DIY outdoor weather station based on **ESP32** and **ESPHome**.  
It is designed as a **modular, expandable system**, starting from a stable core and evolving toward fully custom DIY sensors.

The station integrates seamlessly with **Home Assistant** and focuses on reliability, clean hardware design, and future extensibility.

---

## 🌟 Features

### Stage 1 – Core (current)
- Temperature, humidity, and pressure (**BME280**)
- Ambient light intensity (**BH1750**)
- Air quality – PM1, PM2.5, PM10 (**PMS5003**)
- Lightning detection (**AS3935**)
- Rainfall measurement (commercial tipping-bucket rain gauge)
- Wi-Fi connectivity
- Native Home Assistant integration (ESPHome)

### Planned (future stages)
- Wind speed measurement
- Wind direction measurement
- DIY rain gauge (replacement for the commercial sensor)
- Custom 3D-printed wind sensors

---

## 🧩 Stage 1 – Core Architecture

Stage 1 defines the **core hardware and power architecture** of the Bora weather station.  
The goal of this stage is to deliver a **fully functional and stable base system**, while already preparing the PCB and firmware for future expansion.

### Implemented in Stage 1
- Environmental sensing (temperature, humidity, pressure)
- Light intensity measurement
- Air quality monitoring (PM1 / PM2.5 / PM10)
- Lightning detection
- Rainfall measurement using a commercial rain gauge
- Stable mains-powered supply
- ESPHome firmware with Home Assistant support

### Prepared but disabled
- Wind speed input
- Wind direction input

No PCB redesign will be required to enable these features in later stages.

---

## 🛠️ Hardware

### Main Controller
- **ESP32-DevKitC** with **ESP32-WROOM-32D**
  - Used as a pluggable development board
  - Mounted on pin headers and inserted into the main Bora PCB
  - No custom ESP32 PCB footprint required

### Sensors
- **BME280** – temperature, humidity, pressure (I²C, 3.3 V)
- **BH1750** – ambient light intensity (I²C, 3.3 V)
- **PMS5003** – particulate matter PM1 / PM2.5 / PM10 (UART, 5 V, TTL)
- **AS3935** – lightning detector (I²C / SPI, 3.3 V)
- **WH-SP-RG** – tipping bucket rain gauge (reed switch)

### Prepared connectors (Stage 2+)
- Anemometer (wind speed)
- Wind vane / encoder (wind direction)

---

## 🔌 Power Supply

- **Hi-Link HLK-5M05** – 230 VAC → 5 V DC (~1 A)
- **MP1584 buck converter** – 5 V → 3.3 V
- Single common **GND** across the entire system

Voltage domains:
- **5 V**: PMS5003, buck converter input
- **3.3 V**: ESP32, BME280, BH1750, AS3935

> ⚠️ PMS5003 requires proper airflow and must not be placed in a sealed enclosure.

---

## 💻 Software

- **ESPHome** – firmware running on ESP32
- **Home Assistant** – dashboards, history, and automations

The firmware is designed to evolve together with the hardware stages.

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
