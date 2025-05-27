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

Got it — here's the **complete Setup Instructions** written as a **single clean Markdown block**, ready to paste directly into your `README.md`:

---

````markdown
## ⚙️ Setup Instructions

### 🔹 Raspberry Pi BLE Advertiser (Python)

1. Ensure your Raspberry Pi has Python 3 installed.  
2. Install required packages:
   ```bash
   sudo apt update
   sudo apt install bluetooth bluez python3-pip
   pip3 install bleak
````

3. Navigate to the BLE script directory and run:

   ```bash
   python3 ble_advertiser.py
   ```

---

### 🔹 Android Application (Kotlin)

1. Open the project folder in **Android Studio**.
2. Ensure you have a physical Android device with **Bluetooth LE** support.
3. Grant location and Bluetooth permissions in `AndroidManifest.xml`.
4. Connect your device and click **Run** to build and deploy the app.

---

### 🔹 Express.js Backend Server (Node.js)

1. Clone the project:
2. Install dependencies:
3. Start the server:
4. The backend should now be running at:

---



## 📐 System Architecture

```text
+--------------------+      BLE       +-------------------+       HTTPS        +----------------------+
|  Raspberry Pi (Ad) |  ───────────▶  |  Android App (User)|  ───────────────▶  | Express Backend Server |
| BLE Advertiser     |                | Scans & Sends Data |                   | Generates Ad using AI |
+--------------------+                +-------------------+                   +----------------------+
