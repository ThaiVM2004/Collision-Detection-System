# Collision Detection System

This project implements a **collision detection and warning system** based on the STM32F103C8T6 microcontroller.  
The system measures distances using ultrasonic sensors, evaluates potential collision risks, and issues alerts via LEDs and a buzzer.  
Additionally, all processed data is transmitted over the **CAN bus** using an MCP2551 transceiver for integration with other automotive systems.

---

## 🚗 Features
- Real-time collision detection using **3x JSN-SR04 ultrasonic sensors**
- Central control with **STM32F103C8T6 (Blue Pill)**
- Visual and audible alerts using **LEDs and buzzer**
- Data transmission over **CAN bus (MCP2551 transceiver)**
- Stable 1 Hz measurement cycle
- Reliable operation with noise filtering and threshold detection (3.5 m safety limit)

---

## 🔧 Hardware Components
- **STM32F103C8T6** (ARM Cortex-M3 MCU)
- **JSN-SR04 ultrasonic sensors** × 3
- **MCP2551 CAN transceiver**
- **LED indicators** × 2
- **Buzzer** × 1
- Supporting components: resistors, capacitors, voltage regulator, PCB

---

## 💻 Software
- Developed in **C** using **ArduinoIDE**
- Functions implemented:
  - Trigger ultrasonic sensors sequentially
  - Capture and process Echo signals
  - Calculate distances using time-of-flight method
  - Compare with safety threshold (3.5 m)
  - Trigger LED and buzzer alerts
  - Send data packets over CAN bus (CAN 2.0 protocol)

---

## 📐 System Design
- **Central Processing Block**: STM32 core handling all sensor and control logic
- **Communication Block**: MCP2551 transceiver for CAN bus communication
- **Warning Block**: LEDs and buzzer for real-time alerts

---

## ⚙️ Setup & Usage
1. Assemble the hardware according to the provided schematic and PCB layout.
2. Connect the **ST-Link** programmer to flash the firmware into STM32.
3. Power the system with 5V (regulated).
4. Place obstacles within **2.5 – 3.5 m** to test collision detection.
5. Observe LED and buzzer activation, and verify CAN messages using a **CAN analyzer**.

Note: in /lib has a small library file for can bus. let you to download and import that file into code

How to add library in ArduinoIDE?

Step1:<img width="935" height="460" alt="image" src="https://github.com/user-attachments/assets/5c8d1dea-0039-4d2e-960a-6528d86a70b2" />


Step2 (select zip file): <img width="736" height="102" alt="image" src="https://github.com/user-attachments/assets/ac72b799-3f64-46e8-a3a8-660aa5f1173c" />

Step3: and wait 
 
---

## 📊 Results
- Stable operation with 1 Hz measurement frequency
- Average processing time: **<200 ms**
- Clear and reliable alerts when objects are detected below the safety threshold
- CAN messages successfully transmitted and validated with CAN analyzer tools

---

## 🚀 Future Improvements
- Extend detection range for higher-speed scenarios
- Add more sensors for 360° monitoring
- Integrate advanced filtering (Kalman, AI-based object detection)
- Provide graphical interface (LCD or PC dashboard)
- Enable autonomous actions (auto braking, steering assist)

---

## 📷 Project Images
*(Replace with your actual images)*

### Hardware Setup
<img width="960" height="1280" alt="image" src="https://github.com/user-attachments/assets/81023ccd-2d6b-4269-b37c-a41cdb7bfdd6" />


### Software Testing
<img width="685" height="372" alt="image" src="https://github.com/user-attachments/assets/7edf0383-636f-4830-82ea-abc735444d48" />

