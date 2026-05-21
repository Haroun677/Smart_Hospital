<div align="center">

<img src="https://img.shields.io/badge/Cisco_Packet_Tracer-8.x+-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white"/>
<img src="https://img.shields.io/badge/IoT-Smart_Healthcare-00C896?style=for-the-badge&logo=raspberry-pi&logoColor=white"/>
<img src="https://img.shields.io/badge/Network-WAN_Simulation-FF6B35?style=for-the-badge&logo=cloudflare&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge"/>

# 🏥 Smart Hospital — IoT Network Simulation

**A dual-site WAN simulation connecting a smart security controller to an intelligent patient room, built with Cisco Packet Tracer.**

</div>

---

## 📸 Preview

| Network Topology | Patient Room View | Controller Site |
|:---:|:---:|:---:|
| ![Topology](https://github.com/user-attachments/assets/f897a4c0-bacf-4d83-bb5b-85852e3cb47a) | ![Patient Room](https://github.com/user-attachments/assets/9ce4c38c-92c4-4944-a28a-d37767511bc1) | ![Controller](https://github.com/user-attachments/assets/f014be67-dbfc-402a-9e58-aea8e9b29571) |

---

## 📖 Overview

This project simulates a **real-world smart healthcare network** composed of two geographically separate sites linked via a WAN connection:

| Site | Role | Subnet |
|------|------|--------|
| 🏡 **Controller Site** | Security & alarm management | `192.168.80.0/24` |
| 🏥 **Patient Room** | Smart IoT medical device monitoring | `192.168.60.0/24` |
| 🌐 **WAN Link** | Inter-site communication | `10.10.10.0/24` |

Remote control is enabled through smartphones, allowing staff to monitor and manage devices across both sites in real time.

---

## 🗺️ Network Architecture

```
          ┌──────────────────────┐         WAN          ┌──────────────────────┐
          │   CONTROLLER SITE    │  10.10.10.0/24       │    PATIENT ROOM      │
          │  192.168.80.0/24     │◄────────────────────►│  192.168.60.0/24     │
          │                      │                       │                      │
          │  [R1] ── [Switch0]   │                       │  [R2] ── [Switch1]   │
          │    │         │       │                       │    │         │       │
          │  DHCP       AP01     │                       │  DHCP       AP02     │
          │  Server  Smartphone1 │                       │  Server  Smartphone0 │
          │  IoT Srv  Sirens     │                       │  Camera  Fan  Light  │
          │                      │                       │  Door  Window Motion │
          └──────────────────────┘                       └──────────────────────┘
```

---

## 🔧 Components

### Network Infrastructure

| Device | Model | Quantity | Role |
|--------|-------|----------|------|
| Router | Cisco 2901 | 2 | WAN routing (R1, R2) |
| Switch | Cisco 2960 | 2 | LAN switching |
| Access Point | — | 2 | Wireless (ap01, ap02) |
| DHCP Server | — | 2 | Auto IP per site |


### 🚨 Security Devices — Controller Site (LAN 1)

- 🔴 **Siren alarme 1 & 2** — Dual alarm sirens for intrusion detection
- 📱 **Smartphone1** — Remote security control & monitoring

### 🏥 Smart IoT Devices — Patient Room (LAN 2)

| Device | Icon | Function |
|--------|------|----------|
| Webcam | 📷 | Surveillance & patient monitoring |
| Light Lamp | 💡 | Smart lighting control |
| Ceiling Fan | 🌀 | Automated climate control |
| Motion Detector | 🚶 | Presence sensing |
| Smart Door | 🚪 | Remote access control |
| Smart Window | 🪟 | Automated ventilation |
| Smartphone0 | 📱 | Room-level device control |

---

## 🎯 Project Objectives

- [x] Design a **WAN network** linking two geographically separate sites
- [x] Configure **automatic DHCP addressing** for each LAN independently
- [x] Integrate all IoT devices with a **centralized IoT server**
- [x] Enable **remote device control** via smartphone over the WAN
- [x] Simulate a **real-time security and alarm system**
- [x] Demonstrate **smart home automation** in a healthcare context

---

## 🚀 Getting Started

### Prerequisites

- [Cisco Packet Tracer 8.x or later](https://www.netacad.com/resources/lab-downloads) — free with a Cisco NetAcad account

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Haroun677/Smart_Hospital.git

# 2. Navigate to the project folder
cd Smart_Hospital
```

### Usage

1. Open **Cisco Packet Tracer**
2. Load the file: `File → Open → network_topology.pkt`
3. Click the **Play** button to start the simulation
4. Use the smartphones to test remote device control
5. Trigger the motion detector to test the alarm system

---

## 📁 Project Structure

```
Smart_Hospital/
├── network_topology.pkt       # Main Packet Tracer simulation file
├── docs/
│   └── configuration.md       # IP addressing, routing & IoT server setup
├── images/
│   ├── topology.png
│   ├── patient_room.png
│   └── controller_site.png
└── README.md
```

---

## 📡 IP Addressing Table

| Device | Interface | IP Address | Subnet Mask |
|--------|-----------|------------|-------------|
| R1 | Fa0/0 | 192.168.80.1 | 255.255.255.0 |
| R1 | Se0/0/0 | 10.10.10.1 | 255.255.255.0 |
| R2 | Fa0/0 | 192.168.60.1 | 255.255.255.0 |
| R2 | Se0/0/0 | 10.10.10.2 | 255.255.255.0 |
| DHCP Server (LAN1) | — | 192.168.80.2 | 255.255.255.0 |
| DHCP Server (LAN2) | — | 192.168.60.2 | 255.255.255.0 |
| IoT Server | — | 192.168.60.3 | 255.255.255.0 |

> All end devices receive their IP automatically via DHCP.

---

## 🛠️ Technologies Used

![Cisco](https://img.shields.io/badge/Cisco-Packet_Tracer-1BA0D7?style=flat-square&logo=cisco)
![IoT](https://img.shields.io/badge/Protocol-IoT_over_TCP%2FIP-00C896?style=flat-square)
![DHCP](https://img.shields.io/badge/Service-DHCP-FF6B35?style=flat-square)
![WAN](https://img.shields.io/badge/Link-WAN_Serial-6C63FF?style=flat-square)
![WiFi](https://img.shields.io/badge/Wireless-802.11-F7C948?style=flat-square)

---

## 📄 Documentation

Full configuration guide including:
- Static & dynamic IP setup
- Routing protocol configuration (RIP/Static)
- IoT Server registration steps
- Smartphone pairing walkthrough

👉 See [`docs/configuration.md`](docs/configuration.md)

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Open an **issue** for bugs or suggestions
- Submit a **pull request** with improvements
- Fork the project for your own use

---

## 📬 Contact

**Haroun** — [@Haroun677](https://github.com/Haroun677)

Project Link: [https://github.com/Haroun677/Smart_Hospital](https://github.com/Haroun677/Smart_Hospital)

---

<div align="center">

Made with ❤️ using Cisco Packet Tracer

⭐ **Star this repo if you found it useful!**

</div>
