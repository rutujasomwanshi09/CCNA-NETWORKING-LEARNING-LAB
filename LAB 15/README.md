# DHCP Snooping Configuration Lab

## 📌 Project Overview

This project demonstrates DHCP Snooping configuration to prevent rogue DHCP servers in a network.
The topology includes a legitimate DHCP server and a fake DHCP server to simulate an attack scenario.

---

## 🎯 Objectives

* Configure DHCP Snooping
* Prevent Rogue DHCP Attacks
* Allow only trusted DHCP server
* Block fake DHCP server

---

## 🏗️ Topology Components

* Router (R1)
* Switch (S1)
* Legitimate DHCP Server
* Fake DHCP Server
* Client PCs

---

## 🔐 Security Implementation

DHCP Snooping is configured to:

* Allow only trusted ports
* Block unauthorized DHCP servers
* Protect clients from malicious IP assignments

---

## 🧪 Attack Scenario

* Legitimate DHCP Server → Trusted
* Fake DHCP Server → Untrusted (Blocked)

---

## ⚙️ Configuration Steps

1. Configure Router Interface
2. Enable DHCP Snooping
3. Configure Trusted Ports
4. Verify Configuration

---

## 🔍 Verification Commands

show ip dhcp snooping
show ip dhcp snooping binding
show running-config

---

## 🛠️ Tools Used

* Cisco Packet Tracer
* DHCP Snooping
* Switch Security

---

## 📚 Learning Outcomes

* DHCP Snooping Concept
* Rogue DHCP Attack Prevention
* Switch Security Implementation
* Network Hardening

---
