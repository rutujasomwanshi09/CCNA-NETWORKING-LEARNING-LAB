# 🌐 VLAN Configuration using Cisco Packet Tracer

## 📌 Objective
To configure VLANs on switches and segment the network into different departments (IT, HR, FIR) using Cisco Packet Tracer.

---

## 🖧 Topology Overview

- 2 Switches (2960-24TT)
- Multiple PCs connected to different VLANs
- VLANs:
  - VLAN 10 → IT Department (192.168.10.0/24)
  - VLAN 20 → HR Department (192.168.20.0/24)
  - VLAN 30 → FIR Department (192.168.30.0/24)
- Trunk link between switches

---

## 🛠️ Devices Used

- Cisco 2960 Switch
- PCs
- Ethernet cables

---

## ⚙️ VLAN Details

| VLAN ID | Name | Network |
|--------|------|--------|
| 10 | IT | 192.168.10.0/24 |
| 20 | HR | 192.168.20.0/24 |
| 30 | FIR | 192.168.30.0/24 |

---

## 🔧 Configuration Summary

- VLANs created on both switches
- Access ports assigned to respective VLANs
- Trunk port configured between switches
- PCs assigned IPs based on VLAN

---

## ✅ Result

- Devices in same VLAN can communicate successfully
- Devices in different VLANs cannot communicate (without routing)

---

## 📚 Learning Outcome

- Understanding VLAN segmentation
- Switch configuration (access & trunk ports)
- Basic network isolation concept

---