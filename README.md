# 📡 Wireless-Analyzer-IDS

**A Python-based 802.11 Reconnaissance & Wireless Intrusion Detection System.**

---

## 🎯 Project Overview

**Wireless-Analyzer-IDS** is a high-performance network reconnaissance tool designed for deep visibility into the local 802.11 landscape. Leveraging the **Scapy** library and the multi-band capabilities of the **Realtek RTL8812AU** chipset, this module performs passive sniffing, frame dissection, and real-time security auditing.

This project represents **Module 1** of a multi-stage R&D roadmap focused on **WiFi Sensing** and human activity detection using Channel State Information (CSI).

### 🚀 Key Features

* **Live Beacon Dissection:** Passively captures 802.11 management frames to map active SSIDs and BSSIDs without revealing the analyzer's presence.
* **Security Protocol Auditing:** Automatically identifies encryption standards, including **WPA2**, **WPA3**, and **WPA3-Transition Mode**.
* **Signal Intelligence (RSSI):** Real-time monitoring of Received Signal Strength (RSSI) to estimate device proximity and network density.
* **Intrusion Detection:** Implements logic to detect **Rogue APs**, "Evil Twin" attempts mimicking known SSIDs, and common deauthentication attack signatures.
* **Multi-Channel Intelligence:** Integrated background thread for automated channel hopping across the 2.4GHz and 5GHz spectrums.

---

## 📊 Visualized Intelligence

### Real-Time Network Mapping

| CH | SSID | BSSID | RSSI | CRYPTO | STATUS |
| --- | --- | --- | --- | --- | --- |
| 1 | Home_Secure_5G | DE:AD:BE:EF:00:01 | -42dBm | WPA3(SAE) | ✅ SECURE |
| 6 | Coffee_Shop_Free | AA:BB:CC:11:22:33 | -68dBm | OPEN | 🔓 UNSECURE |
| 11 | Rogue_Portal_Test | FF:EE:DD:33:22:11 | -25dBm | WPA2(CCMP) | ⚠️ ROGUE! |

### Signal Variance (CSI Foundation)

*Research ongoing: Visualizing signal fluctuations caused by human movement. Current benchmarks show up to 99% accuracy for presence detection.*

---

## 🛠️ Technical Stack

| Component | Technology |
| --- | --- |
| **Language** | Python 3.10+ |
| **Core Library** | Scapy (Packet Manipulation & Dissection) |
| **Data Handling** | Pandas (Real-time Frame Buffering) |
| **Hardware** | Realtek RTL8812AU (Supports Monitor Mode/Packet Injection) |
| **Environment** | Kali Linux / Parrot Security OS |

---

## ⚙️ Installation & Usage

### 1. Driver Setup (Realtek RTL8812AU)

Ensure your adapter is in monitor mode using the appropriate DKMS drivers.bash

# Install Drivers

sudo apt update && sudo apt install dkms realtek-rtl88xxau-dkms

# Enable Monitor Mode

sudo ip link set wlan0 down
sudo iw dev wlan0 set type monitor
sudo ip link set wlan0 up

```

### 2. Run the Analyzer
```bash
sudo python3 analyzer.py --interface wlan0

```

---

## 🗺️ Project Roadmap

* [x] **Module 1: Passive Reconnaissance** (Current) - SSID/BSSID extraction and security auditing.
* [ ] **Module 2: Web Dashboard Integration** - Real-time visualization using Flask and Socket.io.
* [ ] **Module 3: WiFi Sensing R&D** - Extracting CSI data for crowd counting and human activity recognition.

---

## ⚖️ Ethical Disclaimer

This tool is strictly for **Security Audit and Awareness** purposes only. It must only be used on networks and devices where the user has explicit legal permission to conduct testing. Unauthorized network interference or data interception is illegal and unethical.

---

**Developed by: Goldyeti2006**
*Aspiring Cybersecurity & Product Security Specialist*

```
