# Layer-3 EtherChannel Using PAgP / LACP / ON Mode

## 📌 Project Overview

This lab demonstrates **Layer-3 EtherChannel configuration** using three different protocols:

* **LACP (Link Aggregation Control Protocol)**
* **PAgP (Port Aggregation Protocol)**
* **ON Mode (Static EtherChannel)**

This topology uses **3 multilayer switches** connected in a triangular topology. Each switch is connected using **Layer-3 EtherChannel** and different negotiation protocols.

This lab helps understand:

* Layer-3 EtherChannel
* LACP configuration
* PAgP configuration
* Static EtherChannel (ON Mode)
* Inter-VLAN routing using multilayer switches
* Redundancy and Load balancing

---

## 🖥️ Topology Design

Three switches:

* **Switch 1 (Top Switch)**
* **Switch 2 (Left Switch)**
* **Switch 3 (Right Switch)**

Each switch connected using EtherChannel:

| Switch Connection | Protocol Used | Network        |
| ----------------- | ------------- | -------------- |
| S1 ↔ S2           | LACP          | 192.168.1.0/24 |
| S1 ↔ S3           | PAgP          | 192.168.2.0/24 |
| S2 ↔ S3           | ON Mode       | 192.168.3.0/24 |

---

## 🧠 Network Details

### LACP (Group 1)

* Mode: Active / Passive
* Network: 192.168.1.0/24
* Port-Channel: 1

### PAgP (Group 2)

* Mode: Desirable / Auto
* Network: 192.168.2.0/24
* Port-Channel: 2

### ON Mode (Group 3)

* Mode: Static (ON)
* Network: 192.168.3.0/24
* Port-Channel: 3

---

## 🔧 Devices Used

* 3 Multilayer Switches (3560)
* 6 PCs
* Ethernet Cables

---

## 🎯 Objectives

* Configure Layer-3 EtherChannel
* Configure LACP
* Configure PAgP
* Configure Static EtherChannel
* Verify EtherChannel
* Test Connectivity

---

## 🧪 Verification Commands

```
show etherchannel summary
show ip interface brief
show running-config
show etherchannel port-channel
```

---

## 📡 IP Addressing Table

| Device | Interface      | IP Address  |
| ------ | -------------- | ----------- |
| S1     | Port-channel 1 | 192.168.1.1 |
| S2     | Port-channel 1 | 192.168.1.2 |
| S1     | Port-channel 2 | 192.168.2.1 |
| S3     | Port-channel 2 | 192.168.2.2 |
| S2     | Port-channel 3 | 192.168.3.1 |
| S3     | Port-channel 3 | 192.168.3.2 |

---

## 🚀 Learning Outcome

After completing this lab you will understand:

* Layer-3 EtherChannel
* LACP vs PAgP
* Static EtherChannel
* Redundancy in networks
* Load balancing
* Multilayer switching

---

## 👨‍💻 Author

Rutuja
CCNA Lab Practice
Cyber Security Learning Path

---
