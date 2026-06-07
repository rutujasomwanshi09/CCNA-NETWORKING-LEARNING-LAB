# Cisco ASA Firewall Basic Configuration

## Description
This lab demonstrates the basic configuration of a Cisco ASA 5506-X Firewall. The firewall is configured with three security zones:

1. INSIDE Network (Trusted)
2. DMZ Network (Partially Trusted)
3. OUTSIDE Network (Untrusted)

The ASA controls traffic flow between these networks using Security Levels and Interface Configuration.

---

## Network Topology

### Inside Network
- Network: 192.168.100.0/24
- Gateway: 192.168.100.1
- Security Level: 100

### DMZ Network
- Network: 10.10.10.0/28
- Gateway: 10.10.10.1
- Security Level: 70

### Outside Network
- Network: 20.20.20.0/24
- Gateway: 20.20.20.1
- Security Level: 0

---

## Devices Used

- Cisco ASA 5506-X Firewall
- Cisco 2960 Switches
- PCs
- Web Server
- DNS Server
- DHCP Server
- Email Server

---

## Security Zones

### Inside
Trusted internal users.

### DMZ
Public-facing servers.

### Outside
Internet or untrusted network.

---

## Features Implemented

- ASA Initial Setup
- Interface Configuration
- Security Level Assignment
- Hostname Configuration
- Local User Creation
- SSH Remote Access
- AAA Authentication
- RSA Key Generation

---

## Verification Commands

show interface ip brief

show running-config

show version

show ssh

show aaa-server

show route

show access-list

ping 192.168.100.1

ssh -l admin 192.168.100.1

---

## Expected Result

- Inside users can access DMZ services.
- DMZ servers are isolated from direct Inside control.
- Outside network is treated as untrusted.
- SSH access is enabled for firewall management.