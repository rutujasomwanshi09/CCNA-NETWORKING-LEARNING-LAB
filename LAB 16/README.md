# IPSG + DAI + DHCP Snooping Security Lab

## 📌 Project Title

Network Security using DHCP Snooping, Dynamic ARP Inspection (DAI) and IP Source Guard (IPSG)

---

## 🎯 Objective

This project demonstrates how to protect a network from:

* Rogue DHCP Attack
* ARP Spoofing Attack
* IP Spoofing Attack

Using:

* DHCP Snooping
* Dynamic ARP Inspection (DAI)
* IP Source Guard (IPSG)

---

## 🏗️ Topology Components

* Router (2911)
* Switch (2960)
* 3 PCs (Clients)
* Legitimate DHCP Server
* Fake DHCP Server

---

## 🌐 Network Details

Network: 192.168.1.0/24

Router IP:
192.168.1.1

Legitimate DHCP Server:
192.168.1.100

Fake DHCP Server:
192.168.1.110

Clients:
DHCP Enabled

---

## 🔐 Security Implementation

### DHCP Snooping

* Trusted Port → Legitimate DHCP
* Untrusted Port → Clients

### Dynamic ARP Inspection

* Prevent ARP Spoofing
* Validate ARP packets

### IP Source Guard

* Prevent IP Spoofing
* Allow valid IP only

---

## ⚙️ Features

* Rogue DHCP Protection
* ARP Spoofing Protection
* IP Spoofing Protection
* Secure Network Infrastructure

---

## 🧪 Testing

1. Enable DHCP
2. Ping Router
3. Check IP assignment
4. Verify Fake DHCP blocked

---

## 🔍 Verification Commands

show ip dhcp snooping
show ip arp inspection
show ip verify source
show ip dhcp snooping binding

---

## 🛠️ Tools Used

Cisco Packet Tracer
Layer 2 Switch Security
DHCP Snooping
DAI
IPSG

---

## 📚 Learning Outcomes

* Network Security Fundamentals
* Layer 2 Security
* DHCP Snooping
* DAI Configuration
* IPSG Configuration

---
