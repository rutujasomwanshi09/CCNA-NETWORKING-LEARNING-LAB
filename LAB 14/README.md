# VLAN Hopping Attack Prevention Lab

## 📌 Project Overview

This project demonstrates how to prevent VLAN hopping attacks using:

* Switchport Nonegotiate
* Disable CDP
* Native VLAN Configuration
* Access Port Security

The topology is implemented using Cisco Packet Tracer with three switches and multiple VLANs.

---

## 🎯 Objectives

* Prevent VLAN hopping attacks
* Secure trunk ports
* Disable unnecessary protocols
* Improve network security

---

## 🏗️ Topology Design

This topology includes:

* Switch S1 → VLAN 10 (IT)
* Switch S2 → VLAN 20 (HR)
* Switch S3 → VLAN 30 (FIN)
* Native VLAN → VLAN 33

All switches connected using trunk links.

---

## 🔐 Security Implementation

### VLAN Hopping Prevention Methods

* Disable DTP using switchport nonegotiate
* Configure native VLAN
* Disable CDP
* Use access ports for end devices

---

## 🛠️ VLAN Details

| VLAN | Department  |
| ---- | ----------- |
| 10   | IT          |
| 20   | HR          |
| 30   | FIN         |
| 33   | Native VLAN |

---

## 🧪 Testing

* Verify VLAN communication
* Check trunk links
* Confirm VLAN hopping prevention

---

## 🔍 Verification Commands

show vlan brief
show interfaces trunk
show running-config

---

## 🛠️ Tools Used

* Cisco Packet Tracer
* VLAN
* Switch Security

---

## 📚 Learning Outcomes

* VLAN Security
* Switch Hardening
* VLAN Hopping Prevention
* Network Security Best Practices

---
