# Project Q-Link: Quantum-Safe Secure Drone Communication

This project provides an open-source framework for implementing **Post-Quantum Cryptography (PQC)** on low-cost microcontrollers to secure drone-to-transmitter RF links. It is designed to be a practical, budget-friendly prototype for securing unmanned systems against interception, decoding, or disruption from both AI and quantum computing threats.

---

##  Project Overview
Standard drone RF links are often unencrypted or use legacy protocols vulnerable to modern "brute-force" or AI-driven signal analysis.**Project Q-Link** implements a "Quantum-Safe" security layer. It focuses on:
* **Indigenous Security:** Building a secure communication stack from the ground up using open-source tools
* **Resilience:** Protecting the RF control signals (Throttle, Yaw, Pitch, Roll) using lightweight lattice-based cryptography
  

---

##  Features
* **Lattice-Based Handshake:** Uses a simplified version of the Kyber algorithm for secure key exchange between the transmitter and the drone.
* **Real-time RF Encryption:** Encrypts control packets in under 10ms to ensure no noticeable flight latency.
* **Signal Masking:** Implements basic frequency hopping to prevent simple signal jamming and disruption
* **No Prior Drone Experience Required:** Designed as a modular "plug-and-play" security layer for existing Arduino/ESP32 flight controllers

---

##  System Architecture
The system consists of two primary nodes:
1.  **Ground Control Station (GCS):** An ESP32-based transmitter that encrypts user inputs.
2.  **Airborne Node (Drone):** An ESP32/Arduino receiver that decrypts signals and passes them to the flight motors.

---

##  Budget Bill of Materials (BOM)
To keep this project "cheapest possible," the following components are recommended:

| Component | Recommendation | Function |
| :--- | :--- | :--- |
| **Microcontroller** | ESP32-DevKit V1 (x2) | Handles the PQC algorithms and encryption logic. |
| **RF Transceiver** | nRF24L01+ (x2) | [cite_start]Manages the physical drone-to-transmitter RF signals[cite: 11]. |
| **IMU Sensor** | MPU6050 | Provides stability and orientation data for the drone. |
| **Frame** | Cardboard or PVC Pipe | Lightweight and zero-cost structure. |
| **Motors** | 8520 Coreless Motors | Inexpensive propulsion for a micro-drone. |

---

## Getting Started

### 1. Prerequisites
* **Arduino IDE** or **VS Code with PlatformIO**.
* **Libraries:** `RadioHead` (for nRF24L01) and `FastPQC` (a lightweight wrapper for embedded devices).

### 2. Installation
```bash
git clone https://github.com/YourRepo/Q-Link-Drone.git
cd Q-Link-Drone/Firmware
```

### 3. Flashing
1.  Open `Transmitter_GCS.ino`.
2.  Connect your first ESP32 and click **Upload**.
3.  Open `Receiver_Drone.ino`.
4.  Connect the second ESP32 and click **Upload**.

---

