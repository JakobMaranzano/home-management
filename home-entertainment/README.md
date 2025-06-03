# 🎮 Home Entertainment System Setup

This folder documents the configuration and routing of the home entertainment system, including AV sources, display targets, audio management, and control systems. The setup is designed for flexibility, allowing multiple devices to be viewed and heard across several zones.

—

## 🖥️ Primary Devices

## Primary Devices

### HDMI Matrix  
**Purpose:** Routes HDMI sources to multiple displays.  
**Notes:** Central to managing shared inputs (e.g., consoles, streaming devices).  

### Audio Matrix / Selector  
**Purpose:** Routes audio to multiple output devices (speakers, headphones).  
**Notes:** Can select between output sources for different zones or preferences.  

### USB Switch  
**Purpose:** Shares USB peripherals (e.g., keyboard, mouse) across devices.  
**Notes:** Useful for switching control between work and entertainment setups.  

### Headphones  
**Purpose:** Private listening.  
**Notes:** May be routed via audio matrix or direct output.  

### Desktop Speakers  
**Purpose:** Main stereo audio output.  
**Notes:** Typically powered speakers for easy PC or console integration.  

### Surround Sound Speakers  
**Purpose:** Immersive multi-channel audio.  
**Notes:** For use in media or theater setups, requires additional amp or receiver.

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

## 📦 Parts List

```
| Item                      | Quantity | Notes                                          | Estimated Price Range |
|—————————|-———|————————————————|————————|
| HDMI Matrix               | 1        | For routing HDMI video signals to multiple displays | $60–$150           |
| Audio Matrix / Selector   | 1        | For routing audio signals to multiple speaker outputs | $30–$100         |
| USB Switch                | 1        | For switching USB peripherals between devices   | $20–$50              |
| Headphones                | 1        | For private listening                           | $30–$200             |
| Desktop Speakers          | 2        | Powered speakers recommended                    | $50–$150             |
| Surround Sound Speakers   | Depends  | For multi-channel audio setups                  | $150–$600+           |
| Cables (HDMI)             | Various  | HDMI cables for video/audio connections         | $20–$50              |
| Cables (USB)              | Various  | USB cables for peripherals                      | $10–$30              |
| Cables (Audio)            | Various  | Audio cables for speakers and devices           | $20–$60              |

**Estimated Total Cost Range**: **$390 – $1,390+**
```

—

## 🌐 Control System

- **Platform:** Home Assistant (running on Proxmox server)
- **Controls:** 
  - HDMI Matrix
  - Audio Matrix
- **Access:** Web UI, API, or network/serial commands