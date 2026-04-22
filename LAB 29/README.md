# Inter-VLAN Routing + DHCP Server on Layer 3 Switch

## 📌 Project Title

Inter-VLAN Routing with DHCP Server using Multilayer Switch (Cisco Packet Tracer)

---

## 📖 Project Description

This project demonstrates **Inter-VLAN Routing** using a **Layer 3 Switch** along with **DHCP Server Configuration**.
Multiple departments are separated using VLANs and each VLAN is assigned IP addresses dynamically using DHCP.

---

## 🏢 Departments & VLANs

| Department | VLAN    | Network Address |
| ---------- | ------- | --------------- |
| IT Dept    | VLAN 10 | 192.168.1.0/24  |
| HR Dept    | VLAN 20 | 192.168.2.0/24  |
| FIN Dept   | VLAN 30 | 192.168.3.0/24  |

---

## 🎯 Objectives

* Configure VLANs
* Configure Access Ports
* Configure Trunk Ports
* Enable Inter-VLAN Routing
* Configure DHCP Server
* Test Connectivity

---

## 🖥️ Devices Used

* Multilayer Switch (3650)
* Layer 2 Switches (2960)
* PCs
* Ethernet cables

---

## 🌐 Network Topology

* IT Department → VLAN 10
* HR Department → VLAN 20
* FIN Department → VLAN 30
* Layer 3 Switch performs Inter-VLAN Routing
* DHCP Server configured on Layer 3 Switch

---

## ⚙️ Features

✔ Inter-VLAN Routing
✔ DHCP Configuration
✔ VLAN Segmentation
✔ Trunking
✔ Network Testing

---

## 🧪 Testing

Use ping command:

```
ping 192.168.1.11
ping 192.168.2.11
ping 192.168.3.11
```

---

## ✅ Expected Output

* All VLANs communicate successfully
* DHCP assigns IP automatically
* Successful ping between VLANs

---
