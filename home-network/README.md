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

| VLAN ID | Name         | Purpose                                     | Access Rules                                           |
|———:|—————|———————————————|———————————————————|
| 10      | General      | Household internet devices                  | Internet access only                                  |
| 20      | Secure       | PC and Proxmox server (wired only)          | Full access to VLANs 10 & 30                          |
| 30      | IoT          | Smart home and automation devices           | Cannot access VLAN 20 (secure network)                |
| 40      | Development  | Temporary/devices via PC’s hosted Wi-Fi     | Isolated; optional internet via PC NAT                ||

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