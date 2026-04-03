# STP Attack Prevention using PortFast, BPDU Guard and Root Guard

## 📌 Project Overview

This project demonstrates how to prevent Spanning Tree Protocol (STP) attacks using:

* PortFast
* BPDU Guard
* Root Guard

This topology is designed in Cisco Packet Tracer to enhance network security and prevent unauthorized switches from becoming root bridge.

---

## 🎯 Objective

* Prevent STP attacks
* Secure access ports
* Prevent unauthorized root bridge election
* Improve network stability

---

## 🏗️ Topology Description

The topology contains:

* 1 Root Bridge Switch (S1)
* 2 Non-Root Switches (S0, S2)
* 1 New Switch (Attacker Switch with Lower Priority)
* Multiple PCs connected to access ports

Security features applied:

| Feature    | Purpose                          |
| ---------- | -------------------------------- |
| PortFast   | Faster port activation           |
| BPDU Guard | Disable port if BPDU received    |
| Root Guard | Prevent unauthorized root bridge |

---

## 🔐 Security Implementation

### PortFast + BPDU Guard

Applied on access ports connected to end devices.

### Root Guard

Applied on trunk ports to prevent rogue switch.

---

## 🧪 Testing Scenario

* New switch added with lower priority
* Root Guard prevents it from becoming root
* BPDU Guard disables unauthorized connections

---

## ✅ Expected Result

* Root bridge remains unchanged
* Unauthorized switch blocked
* Network remains stable

---

## 🛠️ Tools Used

* Cisco Packet Tracer
* STP Protocol
* Cisco Switches (2960)

---

## 📚 Learning Outcomes

* STP security concepts
* Attack prevention techniques
* Switch security configuration
* Real-world network protection

---

## 👩‍💻 Author

Cyber Security Student
STP Attack Prevention Project

---
