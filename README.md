# 📷 ESP32-CAM RHYX M21-45 Control Center

<p align="center">
  <img src="https://img.shields.io/badge/ESP32-CAM-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Arduino_Core-2.x_|_3.x-success?style=for-the-badge">
  <img src="https://img.shields.io/badge/Single_File-Firmware-orange?style=for-the-badge">
  <img src="https://img.shields.io/badge/License-MIT-red?style=for-the-badge">
</p>

> A production-ready **single-file ESP32-CAM firmware** featuring an offline web dashboard, AP + STA mode, live MJPEG streaming, OTA updates, software JPEG fallback for RHYX M21-45 (GC2145), REST API, and complete camera controls.

---

## ✨ Features

* 📷 Live MJPEG video streaming
* 📸 One-click image capture
* 🌐 Built-in Offline Web Dashboard (HTML/CSS/JS)
* 📡 AP + STA Wi-Fi Mode
* 🔄 Automatic Wi-Fi Reconnection
* 💾 Preferences stored in NVS
* 💡 Flash LED Brightness Control
* ⚙ Complete Camera Settings
* 🔐 Optional HTTP Authentication
* 📲 OTA Firmware Update
* 📊 Live System Monitoring
* 🌍 mDNS Support (`http://suryacam.local`)
* 🚀 Single `.ino` File
* ✅ Compatible with Arduino ESP32 Core 2.x & 3.x

---

# 📸 Supported Camera Modules

| Camera                     | Status              |
| -------------------------- | ------------------- |
| OV2640                     | ✅ Supported         |
| OV3660                     | ✅ Supported         |
| OV5640                     | ✅ Supported         |
| RHYX M21-45 (GC2145)       | ✅ Supported         |
| Other ESP32 Camera Sensors | ⚠ Depends on Driver |

---

# 🔥 RHYX M21-45 Automatic Fallback

Unlike the stock CameraWebServer example, this firmware automatically detects the RHYX M21-45 camera.

If hardware JPEG is unavailable, it automatically switches to:

```text
RGB565
   ↓
Software JPEG Encoding
   ↓
Live Stream & Snapshot
```

No code modifications are required.

---

# 🚀 Features Overview

* AP + STA Mode
* Live Video Streaming
* Snapshot Download
* Flash LED Control
* PWM Brightness Control
* Camera Resolution Selection
* JPEG Quality Adjustment
* FPS Control
* Brightness
* Contrast
* Saturation
* White Balance
* Exposure
* Gain Control
* Mirror
* Flip
* Color Effects
* Auto Flash
* Camera Reset
* OTA Update
* Factory Reset
* System Information
* Network Diagnostics

---

# 🖥 Dashboard

The firmware hosts its own modern dashboard.

### Camera

* Live Stream
* Snapshot
* Flash
* Auto Flash
* Resolution
* Quality
* FPS

### Network

* Wi-Fi Status
* STA/AP Information
* RSSI
* Connected Clients
* IP Address
* Reconnect
* Forget Network

### System

* Firmware Version
* Sensor Name
* Chip Information
* Heap Usage
* PSRAM Usage
* Uptime
* Stream URL
* Restart
* Factory Reset

---

# 📦 Hardware Required

* ESP32-CAM AI Thinker
* RHYX M21-45 Camera Module
* USB to TTL Programmer
* 5V / 2A Power Supply
* Jumper Wires

---

# ⚙ Arduino IDE Settings

| Setting          | Value                |
| ---------------- | -------------------- |
| Board            | AI Thinker ESP32-CAM |
| Flash Mode       | QIO                  |
| PSRAM            | Enabled              |
| Partition Scheme | Huge APP             |
| Upload Speed     | 115200               |
| Core Version     | 2.x or 3.x           |

---

# 🚀 Installation

### 1. Install ESP32 Board Package

Install the **Espressif ESP32** board package from Arduino Boards Manager.

### 2. Create New Sketch

Delete the default code.

### 3. Paste Firmware

Paste the complete firmware into the sketch.

### 4. Select Board

```text
AI Thinker ESP32-CAM
```

### 5. Upload

Connect GPIO0 to GND.

Press RESET.

Upload the firmware.

After uploading:

1. Remove GPIO0 from GND.
2. Press RESET again.
3. Open the Serial Monitor.

---

# 📶 Default Access Point

```text
SSID     : SuryaCAM-ESP32
Password : surya12345
```

Open:

```text
http://192.168.4.1
```

---

# 🌐 REST API

| Endpoint     | Method | Description     |
| ------------ | ------ | --------------- |
| `/`          | GET    | Dashboard       |
| `/status`    | GET    | System Status   |
| `/capture`   | GET    | Capture Image   |
| `/control`   | GET    | Camera Settings |
| `/config`    | POST   | Save Wi-Fi      |
| `/reboot`    | GET    | Restart Device  |
| `/factory`   | GET    | Factory Reset   |
| `:81/stream` | GET    | MJPEG Stream    |
| `:81/frame`  | GET    | Single JPEG     |

---

# 📈 Performance

| Resolution    |           FPS |
| ------------- | ------------: |
| QVGA          |     12–18 FPS |
| VGA           |      6–10 FPS |
| SVGA          |       4–6 FPS |
| UXGA Snapshot | 1–2 sec/frame |

Actual performance depends on camera sensor, lighting, PSRAM availability, Wi-Fi conditions, and firmware configuration.

---

# 🛠 Troubleshooting

### Camera Init Failed (0x106)

The firmware automatically attempts to switch to Software JPEG mode.

### Wi-Fi Not Connecting

* Verify SSID and password.
* Use a 2.4 GHz Wi-Fi network.
* Disable WPA3-only mode if required.
* Ensure stable power.

### Brownout / Random Restart

Use:

* 5V / 2A power supply
* Short USB cable
* Stable power connection
* PSRAM enabled where supported

### Stream Not Opening

Open:

```text
http://BOARD_IP:81/stream
```

---

# 📁 Project Structure

```text
ESP32_CAM_RHYX_M21_45/
│
├── ESP32_CAM_RHYX_M21_45_Mohd_Arhan.ino
├── README.md
├── LICENSE
│
├── assets/
│   ├── dashboard.png
│   ├── stream.gif
│   └── wiring.png
│
└── screenshots/
```

---

# 📷 Preview

Add project screenshots to the repository:

```text
assets/dashboard.png
assets/stream.gif
assets/network.png
assets/system.png
```

Example:

```markdown
![Dashboard](assets/dashboard.png)
```

---

# 🤝 Contributing

Contributions, bug reports, feature requests, and pull requests are welcome.

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

# 👨‍💻 Author

**Mohd Arhan**

Mechanical & Robotics Engineer
Robotics • Embedded Systems • IoT • AI • Automation • Research

GitHub: **Arhan-Khan**

---

# 📄 License

This project is licensed under the **MIT License**.

---

## ⭐ Support

If this project helped you:

⭐ Star the repository
🍴 Fork the project
💬 Share it with others

**Happy Coding! 🚀**
