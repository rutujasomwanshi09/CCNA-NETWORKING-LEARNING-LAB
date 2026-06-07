# Cisco ASA Firewall SSH Configuration

## Overview
This project demonstrates Cisco ASA Firewall SSH Configuration using Cisco Packet Tracer. The firewall is configured with three security zones:

1. Inside Network (Trusted)
2. DMZ Network (Partially Trusted)
3. Outside Network (Untrusted)

The ASA firewall provides:
- Interface Security Configuration
- DHCP Services
- SSH Remote Management
- User Authentication
- Network Segmentation

------------------------------------------------------

## Network Information

### Inside Network
Network: 192.168.100.0/24
Gateway: 192.168.100.1
Security Level: 100

### DMZ Network
Network: 10.10.10.0/28
Gateway: 10.10.10.1
Security Level: 70

### Outside Network
Network: 20.20.20.0/24
Gateway: 20.20.20.1
Security Level: 0

----------------------------------------------------

## Devices Used

- Cisco ASA 5506-X Firewall
- Cisco 2960 Switches
- PCs
- Web Server
- DNS Server
- DHCP Server
- Email Server

-----------------------------------------------------------

## Features Implemented

### ASA Firewall
- Hostname Configuration
- Enable Password Configuration
- User Authentication
- Interface Configuration
- Security Levels

### DHCP
- Automatic IP Assignment
- DNS Configuration
- Gateway Configuration

### SSH
- RSA Key Generation
- Secure Remote Access
- Local Authentication

------------------------------------------------

## Verification

Check DHCP Lease:
show dhcpd binding

Check SSH:
show ssh

Check Running Configuration:
show running-config

SSH Login:
ssh -l admin 192.168.100.1

---------------------------------------------------

## Expected Output ##

- PCs obtain IP addresses automatically.
- SSH login to ASA firewall works successfully.
- DMZ and Outside networks remain logically separated.
- Firewall security levels control traffic flow.

--------------------------------------------------------

## Learning Outcomes ##

- Cisco ASA Interface Configuration
- DHCP Server Configuration on ASA
- SSH Remote Management
- Security Level Implementation
- Basic Firewall Administration
