# android-network-monitor

# Android-Based Network Device Monitoring Server

## 📌 Overview
This project demonstrates a lightweight cybersecurity monitoring lab built using an old Android device running a Linux environment (Termux). The system continuously monitors a local Wi-Fi network and detects newly connected devices by performing periodic network scans. When a new device is identified, the event is logged with a timestamp, simulating basic SOC-style network visibility.

This project focuses on **defensive security concepts only** and is intended for educational use on personal networks.

---

## 🎯 Objectives
- Detect newly connected devices on a local network
- Monitor network changes using ARP/Nmap scanning
- Maintain a baseline of known devices
- Log network events with timestamps
- Gain hands-on experience with Linux, networking, and security monitoring

---

## 🏗️ System Architecture
Wi-Fi Network
↓
Android Device (Termux Linux)
↓
Nmap / ARP Scan
↓
Python Detection Script
↓
Logs & Alerts

---

## 🧰 Tools & Technologies
- **Platform**: Android + Termux (Linux)
- **Language**: Python 3
- **Networking Tools**: Nmap, iproute2
- **Concepts**:
  - Network enumeration
  - ARP scanning
  - Baseline comparison
  - Log monitoring

---

## ⚙️ Implementation

### 1. Environment Setup
- Installed Termux from F-Droid
- Updated Linux packages
- Installed Python and networking utilities

### 2. Network Identification
Direct interface access (`wlan0`) is restricted on Android due to SELinux policies.  
The network range was identified using:
```bash
ip route
or
termux-wifi-connectioninfo
```

An initial network scan was performed and stored as a baseline:
nmap -sn 192.168.1.0/24 > baseline.txt

