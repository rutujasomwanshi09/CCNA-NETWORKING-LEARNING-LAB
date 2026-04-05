# Port Security Configuration Lab

## 📌 Project Title

Switch Port Security Configuration using Sticky MAC

---

## 🎯 Objective

This lab demonstrates how to secure switch ports using:

* Port Security
* Sticky MAC Address
* Violation Modes
* Limiting devices per port

---

## 🏗️ Topology Components

* Switch (2960)
* 5 PCs
* Hacker PC

---

## 🌐 Network Details

Network: 192.168.1.0/24

PC0 : 192.168.1.1
PC1 : 192.168.1.2
PC2 : 192.168.1.3
PC3 : 192.168.1.4
PC4 : 192.168.1.5

---

## 🔐 Port Security Configuration

### Fa0/1-2

* Max Device: 1
* MAC Address: Sticky
* Violation Mode: Shutdown

### Fa0/3-4

* Max Device: 2
* MAC Address: Sticky
* Violation Mode: Restrict

### Fa0/5

* Max Device: 1
* Manual MAC Address
* Violation Mode: Protect

---

## ⚙️ Security Features

* Prevent unauthorized access
* Limit number of devices
* Block hacker PC
* Secure switch ports

---

## 🧪 Testing

* Connect authorized PC
* Connect unauthorized PC
* Check violation mode
* Verify port status

---

## 🔍 Verification Commands

show port-security
show mac-address-table
show running-config

---

## 🛠️ Tools Used

Cisco Packet Tracer
Switch Port Security

---

## 📚 Learning Outcomes

* Port Security concept
* Sticky MAC configuration
* Violation modes
* Switch security

---
