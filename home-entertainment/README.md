# 🎮 Home Entertainment System Setup

This folder documents the configuration and routing of the home entertainment system, including AV sources, display targets, audio management, and control systems. The setup is designed for flexibility, allowing multiple devices to be viewed and heard across several zones.

—

## 🖥️ Primary Devices

```

| Device           | Connection Types Used                                | Notes                                      |
|——————|——————————————————|———————————————|
| PC               | 2× HDMI (monitors), 1× HDMI (matrix), Optical (audio) | Primary desktop with audio + video routing |
| Laptop           | HDMI, USB                                           | Docked or direct connection                 |
| Work Laptop      | HDMI (via dock), USB                                | USB switch to share keyboard/mouse         |
| Nintendo Switch  | HDMI                                                | Routed through HDMI matrix                  |

```

—

## 📺 Display System

### HDMI Matrix Switch (4×4)

- **Inputs:** PC, Laptop, Work Laptop, Nintendo Switch  
- **Outputs:** 2× Desk Monitors, 2× TVs  
- **Audio Out:** Optical S/PDIF to Audio Matrix  

> **Purpose:** Allows routing any input to any combination of displays.

—

## 🔊 Audio Management

### Audio Matrix / Multi-Zone Selector

- **Inputs:**
  - Optical S/PDIF from:
    - HDMI Matrix
    - PC
    - TV 1
    - TV 2
  - Bluetooth
- **Outputs:** Multiple speaker zones throughout the home

> **Purpose:** Flexible audio routing from any source to any speaker zone.

—

## ⌨️ Input Sharing

### USB Switch

- **Connected To:** PC, Laptop, Work Laptop  
- **Purpose:** Shares keyboard and mouse across systems

—

## 🌐 Control System

- **Platform:** Home Assistant (running on Proxmox server)
- **Controls:** 
  - HDMI Matrix
  - Audio Matrix
- **Access:** Web UI, API, or network/serial commands