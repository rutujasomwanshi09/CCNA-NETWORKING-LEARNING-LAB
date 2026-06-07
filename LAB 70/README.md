# Cisco ASA Firewall OSPF + Static Routing Configuration

## Project Overview

This project demonstrates the implementation of Cisco ASA Firewall integrated with OSPF (Open Shortest Path First) and Static Routing.

The topology consists of:

- Inside Network (Trusted Zone)
- DMZ Network (Partially Trusted Zone)
- Outside Network (Untrusted Zone)
- ASA Firewall
- Router R1
- Router R2 (ISP Router)
- OSPF Dynamic Routing
- Static Default Route

The ASA firewall exchanges routing information using OSPF and forwards unknown traffic using a static default route toward the ISP router.

---

## Network Topology

### Inside Network

Network ID: 192.168.100.0/24

Security Level: 100

Devices:
- PC0
- PC1
- PC2
- PC3
- PC4

Gateway:
192.168.100.1

---

### DMZ Network

Network ID: 172.16.10.0/28

Security Level: 70

Servers:
- Web Server
- DNS Server
- DHCP Server
- Email Server

Gateway:
172.16.10.1

---

### Outside Network

Network ID: 8.8.8.0/24

Security Level: 0

Devices:
- Google Server
- External PCs

Gateway:
8.8.8.1

---

## Point-to-Point Links

### ASA ↔ Router1

Network:
10.10.10.0/30

Router1:
10.10.10.2

ASA:
10.10.10.1

---

### ASA ↔ Router2

Network:
20.20.20.0/30

Router2:
20.20.20.2

ASA:
20.20.20.1

---

## Features Implemented

### ASA Firewall Configuration

- Hostname Configuration
- Enable Password
- User Authentication
- Security Zones
- Interface Configuration

### OSPF Routing

- OSPF Process ID 50
- Route Advertisement
- Dynamic Route Learning

### Static Routing

- Default Route Configuration
- Internet Connectivity

### Network Segmentation

- Trusted Zone
- Partially Trusted Zone
- Untrusted Zone

---

## Verification Commands

### ASA

show route

show ospf

show running-config

### Router1

show ip route

show ip ospf neighbor

show ip protocols

### Router2

show ip route

show ip ospf neighbor

---

## Expected Results

- OSPF neighbors establish successfully.
- Routes are dynamically exchanged.
- Inside network can reach outside network.
- DMZ servers become reachable.
- Unknown traffic follows static default route.
- Firewall security levels are enforced.

---

## Learning Outcomes

- Cisco ASA Firewall Configuration
- OSPF Dynamic Routing
- Static Routing
- Security Level Concepts
- DMZ Implementation
- Enterprise Network Design