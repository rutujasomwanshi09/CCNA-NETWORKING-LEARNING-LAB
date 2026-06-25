# EtherChannel Configuration Using PAgP

## 📌 Project Overview

This project demonstrates **EtherChannel configuration using PAgP (Port Aggregation Protocol)** in Cisco Packet Tracer.
EtherChannel is used to combine multiple physical links into a single logical link to increase bandwidth and provide redundancy.

This topology includes:

* 1 Multilayer Switch (MLS1)
* 2 Access Switches (S1 & S2)
* PAgP based EtherChannel configuration

---

## 🖥️ Topology

* MLS1 connected to Switch1 using **PAgP Channel Group 2**
* MLS1 connected to Switch2 using **PAgP Channel Group 1**
* Trunk configuration applied on Port-Channel interfaces

---

## 🎯 Objectives

* Configure EtherChannel using PAgP
* Configure trunking on Port-Channel interfaces
* Verify EtherChannel configuration
* Understand desirable and auto modes

---

## 🧰 Devices Used

* Cisco 2960 Switch (2)
* Cisco Multilayer Switch (1)
* Cisco Packet Tracer

---

## ⚙️ Technologies Used

* EtherChannel
* PAgP Protocol
* VLAN Trunking
* Cisco CLI

---

## 🔗 EtherChannel Modes Used

| Mode      | Description                      |
| --------- | -------------------------------- |
| desirable | Actively negotiates EtherChannel |
| auto      | Passively waits for negotiation  |

---

## 🛠️ Configuration Summary

### MLS1

* Channel Group 1 (Auto)
* Channel Group 2 (Desirable)

### Switch 1

* Channel Group 2 (Auto)

### Switch 2

* Channel Group 1 (Desirable)

---

## 🔍 Verification Commands

```
show etherchannel summary
show interfaces trunk
```

---

## 📚 Learning Outcomes

After completing this lab, you will understand:

* EtherChannel concept
* PAgP configuration
* Trunk configuration
* Switch to switch redundancy

---

## 👩‍💻 Author

Rutuja Somwanshi
BTech CSE (Cyber Security) Student
Cisco Networking Lab Practice

---
