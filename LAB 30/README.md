# Dedicated DHCP, DNS, and Web Server Configuration

## 📌 Project Overview

This project demonstrates a centralized Data Center architecture where DHCP, DNS, and Web services are hosted on dedicated servers.

## 🎯 Objectives

* Configure Router for LAN connectivity
* Setup Dedicated DHCP Server
* Configure DNS Server
* Configure Web Server
* Enable communication between Office LAN and Data Center

## 🌐 Network Design

### Office LAN

* Network: 192.168.10.0/24
* Gateway: 192.168.10.1

### Data Center Servers

| Server Type | IP Address   |
| ----------- | ------------ |
| DHCP Server | 192.168.10.5 |
| DNS Server  | 192.168.10.6 |
| Web Server  | 192.168.10.7 |

## 🖥️ Devices Used

* Router (2911)
* Switches (2960)
* DHCP Server
* DNS Server
* Web Server
* PCs (Clients)

## ⚙️ Services Configuration

### DHCP Server

* Pool Name: OFFICE-LAN
* Default Gateway: 192.168.10.1
* Start IP: 192.168.10.11
* Subnet Mask: 255.255.255.0
* Max Users: 100

### DNS Server

* Domain: cisco.com
* A Record: cisco.com → 192.168.10.7

### Web Server

* HTTP Service Enabled
* Hosted Website: cisco.com

## 🧪 Testing

* PC → DHCP IP Assignment
* Ping Gateway: 192.168.10.1
* Open Browser → http://cisco.com


## 👩‍💻 Author

Rutuja
BTech Student
Cyber Security & Networking Learner
