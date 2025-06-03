# 🛜 Home Network Setup

This folder documents the full layout and configuration of the home network, including physical topology, VLAN structure, routing logic, and device segregation. The network is designed to balance security, performance, and scalability across general, secure, IoT, and development systems.

—

## 🔧 Network Goals

- **General Network**: For TVs, gaming consoles, laptops, and phones.
- **Secure Network**: For the PC and Proxmox server (hardwired only).
- **IoT Network**: For smart home and automation devices.
- **Development Network**: For temporary or experimental IoT/dev devices, hosted over Wi-Fi from the PC.

—

## 🧩 VLAN Structure

### 📶 VLAN Configuration Table

```
| VLAN ID | Name        | Purpose                          | Devices                               |   Internet    | Access Rules                      |
|————-|——————-|-————————————————-|———————————————————-|———————-|—————————————————-|
| 10      | General     | Household internet devices       | Smart TVs, laptops, phones, consoles  | ✅            | 🚫 No access to VLAN 20/30       |
| 20      | Secure      | Critical systems, admin network  | PC, Proxmox Server                    | ✅            | ✅ Access to VLAN 30             |
| 30      | IoT         | Smart home and automation        | Sensors, smart plugs, hubs            | ✅            | 🚫 Cannot access VLAN 10/20      |
| 40      | Development | Temporary/test Wi-Fi devices     | Dev/test hardware (via PC Wi-Fi)      | ✅ (via PC)   | 🔒 Isolated, NAT access via PC   |
```

VLAN 10: General
  - Devices: Smart TVs, game consoles, phones, laptops
  - Internet Access: Yes
  - Access to VLAN 20: No
  - Access to VLAN 30: No

VLAN 20: Secure
  - Devices: PC (Dev Hub), Proxmox Server
  - Internet Access: Yes
  - Access to VLAN 30 (IoT): Yes
  - Access to VLAN 10: Optional

VLAN 30: IoT
  - Devices: Smart home and automation devices
  - Internet Access: Yes
  - Access to VLAN 20: No
  - Access to VLAN 10: No

VLAN 40: Development (Wi-Fi only, hosted by PC)
  - Devices: Temporary/devices under test
  - Internet Access: Optional (shared via PC NAT)
  - Access to VLAN 20/30/10: No (isolated by default)

—

## 🖥️ Core Hardware & Wiring

- **Modem** → **VLAN-capable router**
  - Router handles DHCP, NAT, and inter-VLAN routing.
- **Router Ports**:
  - Port 1: VLAN-aware Ethernet switch (trunk: VLANs 10, 20, 30)
  - Port 2: PC (tagged VLAN 20, hosts VLAN 40 Wi-Fi)
  - Port 3: Proxmox server (VLAN 20, Wi-Fi/NIC access to VLAN 40 optional)

—

## 📶 Wi-Fi Access Points (APs)

- Trunked from VLAN-aware switch
- Broadcast SSIDs:
  - `HomeNet` (VLAN 10)
  - `IoTNet` (VLAN 30)
- VLAN 40 is not passed to APs — it is local to the PC’s software Wi-Fi

—

## 🧠 Proxmox Server Role

- Connected via Ethernet to VLAN 20
- Has Wi-Fi or virtual NIC access to VLAN 40
- Needs to communicate with VLAN 30 (IoT) for automation and data collection

—

## 💡 Notes

- Powerline Ethernet may be used if physical cabling is limited, but performance is lower than dedicated Ethernet.
- VLAN 40 Wi-Fi is shared via the PC for isolated development environments.
- Each network segment has carefully defined firewall rules to maintain separation and control.

—

## 📂 Related

- [../home-entertainment/](../home-entertainment/) – HDMI & audio matrix, media routing
- [../home-iot/](../home-iot/) – Smart home devices and Home Assistant configuration