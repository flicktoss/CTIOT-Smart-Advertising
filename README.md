# 📡 CTIOT – Context-Aware Targeted Advertising using IoT

A multi-platform IoT-based advertising system that delivers **personalized, hyper-local ads** through BLE (Bluetooth Low Energy) broadcast and mobile interaction. The system integrates **hardware (Raspberry Pi)**, **mobile app (Android)**, and **backend (Express.js)** to create a seamless smart advertising ecosystem.

---

## 🚀 Project Overview

CTIOT is designed to explore how Internet of Things can enhance real-time, location-aware advertising. By leveraging BLE, user personalization, and cloud-based ad generation, it creates a smart system where:

- Advertisers **broadcast BLE signals** from Raspberry Pi devices in physical locations.
- Nearby users **receive and interact** with personalized ads via an Android app.
- A backend server **processes preferences and context** to dynamically generate and serve relevant ads.

---

## 🧩 System Components

### 🔹 1. Raspberry Pi BLE Advertiser *(Python)*
- Uses Raspberry Pi 4 to send BLE advertising packets with location + advertiser context.
- Built using `bluez` and `bleak` for Python BLE stack.
- Runs continuously to detect nearby users and update advertiser-side status.

### 🔹 2. Android Application *(Kotlin)*
- Scans for BLE signals from nearby Raspberry Pi devices.
- Collects user preferences and facilitates ad interaction.
- Sends data back to backend for ad targeting.
- Built with Kotlin and Jetpack libraries.

### 🔹 3. Express.js Backend Server *(Node.js)*
- RESTful API to receive user context and Raspberry Pi data.
- Integrates **Gemini API** to generate dynamic, personalized ads.
- Responds with customized ad content for the mobile app.

---

## 🛠️ Technologies Used

| Layer         | Tech Stack                          |
|---------------|-------------------------------------|
| IoT Hardware  | Raspberry Pi 4, Python, BLE (bluez) |
| Mobile App    | Android (Kotlin), BLE APIs          |
| Backend       | Node.js, Express.js, Gemini API     |
| Communication | BLE, REST API, JSON                 |

---

## 📐 System Architecture

+--------------------+      BLE       +-------------------+       HTTPS        +----------------------+
|  Raspberry Pi (Ad) |  ───────────▶  |  Android App (User)|  ───────────────▶  | Express Backend Server |
| BLE Advertiser     |                | Scans & Sends Data |                   | Generates Ad using AI |
+--------------------+                +-------------------+                   +----------------------+


⚙️ Setup Instructions
1. Raspberry Pi
Install Python 3, bluez, and bleak
Run ble_advertiser.py

2. Android App
Open in Android Studio
Enable location & BLE permissions
Run on a physical Android device (Bluetooth LE enabled)

3. Express.js Backend
git clone https://github.com/your-username/ctiot-smart-ads.git
cd backend
npm install
node index.js
