# Cisco ASA Firewall DHCP Configuration

## Description

This lab demonstrates DHCP configuration on a Cisco ASA 5506-X Firewall. The ASA firewall acts as a DHCP server for the Inside Network while also providing connectivity between Inside, DMZ, and Outside networks.

The firewall is configured with three security zones:

- Inside Network (Trusted)
- DMZ Network (Partially Trusted)
- Outside Network (Untrusted)

DHCP services are enabled on the Inside interface to automatically assign IP addresses to client PCs.

---

## Network Information

### Inside Network
- Network: 192.168.100.0/24
- Gateway: 192.168.100.1
- DHCP Range: 192.168.100.101 - 192.168.100.199
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

## Objectives

1. Configure ASA interfaces.
2. Assign security levels.
3. Enable DHCP service on ASA.
4. Configure DNS settings.
5. Automatically assign IP addresses to Inside clients.
6. Verify DHCP functionality.

---

## Features Implemented

- ASA Interface Configuration
- Security Zone Configuration
- DHCP Server Configuration
- DNS Server Assignment
- Network Segmentation
- Firewall Security Levels

---

## Verification

### Verify Interface Status

show interface ip brief

### Verify DHCP Pool

show dhcpd binding

show dhcpd state

### Verify Running Configuration

show running-config

### Verify Assigned Address

On PC:

ipconfig

### Connectivity Test

ping 192.168.100.1

---

## Expected Result

- PCs receive IP addresses automatically.
- Gateway is assigned as 192.168.100.1.
- DNS is assigned as 8.8.8.8.
- Clients can communicate with the firewall successfully.