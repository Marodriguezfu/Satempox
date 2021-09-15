# Satempox Prototype – Biomedical Variables Meter (2021)

This repository contains the **Satempox Prototype**, a biomedical device developed as part of the course **Electrónica Digital I** at the **Universidad Nacional de Colombia** (2021).  
The system integrates multiple hardware modules (FPGA, ESP32, sensors, LCD) to measure, process, and display biomedical variables such as **temperature**, **oxygen saturation**, and **heart rate**.

---

## 📖 Project Overview

The project aimed to design and implement a modular biomedical device capable of:
- Measuring biomedical variables in real time.
- Using **FPGA hardware description** to process and transmit data.
- Implementing communication protocols (UART, SPI, I²C).
- Integrating external devices (Bluetooth, RFID, LCD) for user-friendly interaction.

---

## 🛠️ Features

- **RFID + Transponder**: User identification via RFID tags linked to patient records.  
- **MAX30102 Sensor**: Captures heart rate, SpO₂, and temperature data.  
- **ESP32 Bluetooth (Master/Slave)**: Handles wireless data transmission via UART.  
- **FPGA**: Central controller for data reception, packaging, and display logic.  
- **LCD 16x2 Display**: Real-time visualization of biomedical measurements.  
- **I²C Implementation**: FSM-based design for sensor communication.  

---

## 📂 Repository Structure

```
satempox-prototype/
├── FPGA code/ # FPGA HDL code and state machine implementations
├── ESP code/ # ESP32 firmware for Bluetooth and UART
├── README.md
└── .gitignore
```

---

## ⚙️ Hardware & Software Requirements

- **Hardware**
  - FPGA board (compatible with Quartus)
  - ESP32 development board
  - MAX30102 (heart rate and SpO₂ sensor)
  - LM75 (temperature sensor, I²C)
  - RFID reader + tags
  - Bluetooth HC-05 module
  - LCD 16x2 display
  - Resistors (1k), jumpers, prototyping board

- **Software**
  - Intel Quartus (for FPGA design)
  - Arduino IDE (ESP32 firmware)
  - Serial monitor / Bluetooth terminal

---

## 🚀 Implementation Highlights

1. **RFID + ESP32**: User validation before enabling biomedical measurements.  
2. **MAX30102 Sensor**: Sends patient vitals to ESP32 (UART).  
3. **ESP32 Bluetooth**: Master receives sensor data and transmits it to the slave → FPGA.  
4. **FPGA**: Implements UART and I²C FSMs to process incoming data and update the display.  
5. **LCD**: Displays static labels and dynamic values (temperature, SpO₂, BPM).  

---

## 📊 Results

- Successful integration of **FPGA + ESP32 + sensors** into a modular biomedical prototype.  
- Displayed real-time vitals (temperature, SpO₂, BPM) on LCD after RFID user authentication.  
- Highlighted the importance of FSM design for communication protocols (UART, I²C, Bluetooth).  
- Demonstrated feasibility of FPGA-based biomedical devices.  

---

## 🧩 Challenges

- Synchronization of UART/I²C protocols across multiple modules.  
- Limited documentation for certain module integrations.  
- Complex FSM implementation for I²C due to bidirectional SDA line.  

---

## 👥 Authors

- **Daniel Felipe Torres Robles**  
- **Miguel Ángel Rodríguez Fuentes**  
- **Sergio Felipe Rodríguez Mayorga**  