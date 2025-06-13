# 🧰 DIY USB Switch with Home Assistant Integration

This project is a custom-built USB switch designed to allow seamless sharing of USB peripherals (e.g., keyboard, mouse, printer, DAC) between multiple devices in the home entertainment setup. It includes a physical button for manual switching and integrates with Home Assistant for automation and remote control.

—

## 📦 Features

- Supports **4 USB inputs** (devices like keyboard, mouse, etc.)
- Supports **3 USB outputs** (targets like PC, server, or console)
- **Physical switch button** for local control
- **Home Assistant integration** via MQTT or API
- Optionally expandable to more inputs/outputs with modular design

—

## 🛠️ Parts List


```
| Item                      | Description                               |
|—————————|-——————————————|
| USB Hub or Switch Core    | A USB multiplexer (manual or relay-based) |
| Microcontroller           | ESP32 or similar with USB host capability |
| Physical Button           | For local toggling of active USB target   |
| Enclosure                 | Custom or off-the-shelf case              |
| USB Cables (various)      | Input/output connectivity                 |
| Optional: Relay Modules   | If building electrical switching manually |
```


> 💡 A more detailed and centralized [Parts List](../parts-list.md) exists in the parent directory.

—

## ⚙️ Functionality Overview

- The microcontroller manages switching logic.
- Physical button toggles between connected outputs (e.g., PC, Proxmox server).
- The microcontroller publishes/receives state to/from Home Assistant for automation triggers.
- USB host/device switching may be done electronically (relays or USB switch ICs) or with a commercial switch core.

—

## 🧰 Home Assistant Integration

- **MQTT or HTTP API** can be used to toggle the current output.
- Example use cases:
  - Automate switching to the Proxmox server when the PC is idle.
  - Switch USB devices with a voice command or dashboard button.

—

## 🧰 Wiring Diagram

> _Coming soon!_ Will include ESP32 pinout, USB routing, and button connection.

—

## 📌 Future Enhancements

- LED indicators for active port
- Web-based interface for manual switching
- Additional USB port support
- Display status on Home Assistant dashboard

—

## 📁 File Structure

```
home-entertainment/
└── usb-switch/
    ├── README.md            # Project documentation
    ├── firmware/            # Microcontroller code and configs
    │   └── main.ino         # Example firmware entry point (placeholder)
    ├── wiring-diagram.png   # Visual schematic (planned)
    └── assets/              # Optional: button icons, CAD files, etc.
```

—

## 📎 Notes

- USB switching reliability depends on the method (mechanical vs electronic).
- Home Assistant integration may require MQTT Broker or local API access.
- Some USB devices may not handle hot switching gracefully—test thoroughly.