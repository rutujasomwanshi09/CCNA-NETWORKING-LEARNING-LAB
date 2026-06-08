# Cisco ASA Firewall Advanced Policy Configuration

## Project Overview

This project demonstrates Advanced Cisco ASA Firewall Policy Configuration using:

- OSPF Dynamic Routing
- Static Default Routing
- Dynamic NAT/PAT
- Extended Access Control Lists (ACLs)
- DMZ Security Architecture
- Protocol-Specific Traffic Filtering
- Web, DNS, DHCP and Email Server Protection

The objective is to implement granular firewall policies that allow only authorized services between Inside, DMZ, and Outside networks while blocking unauthorized access.

---

## Network Topology

### Inside Network (Trusted Zone)

Network: 192.168.100.0/24

Security Level: 100

Gateway: 10.10.10.1

Devices:
- PC0
- PC1
- PC2
- PC3
- PC4

Purpose:
Internal corporate users.

---

### DMZ Network (Partially Trusted Zone)

Network: 172.16.10.0/28

Security Level: 60

Gateway: 172.16.10.1

Servers:

| Server | IP Address |
|----------|------------|
| Web Server | 172.16.10.9 |
| DNS Server | 172.16.10.7 |
| DHCP Server | 172.16.10.10 |
| Email Server | 172.16.10.6 |

Purpose:
Public-facing services.

---

### Outside Network (Untrusted Zone)

Network: 8.8.8.0/24

Security Level: 0

Purpose:
Internet Simulation

Devices:
- Google Server
- External Hosts

---

## Point-to-Point Networks

### Router1 ↔ ASA

Network: 10.10.10.0/30

Router1: 10.10.10.2

ASA: 10.10.10.1

---

### Router2 ↔ ASA

Network: 20.20.20.0/30

Router2: 20.20.20.2

ASA: 20.20.20.1

---

## Features Implemented

### Routing

- OSPF Process 50
- Dynamic Route Advertisement
- Static Default Route

### NAT

- Inside Network Dynamic PAT
- DMZ Network Dynamic PAT

### Advanced ACL Policies

DMZ Rules:
- DHCP Client → DHCP Server
- DNS Queries → DNS Server
- HTTP Access → Web Server

Internet Rules:
- ICMP Allowed
- HTTP Allowed
- HTTPS Allowed
- DNS Allowed

### Security Zones

| Zone | Security Level |
|--------|---------------|
| Inside | 100 |
| DMZ | 60 |
| Outside | 0 |

---

## Verification Commands

show route

show ospf

show nat

show access-list

show xlate

---

## Testing

### Routing Verification

ping 8.8.8.8

tracert 8.8.8.8

### DNS Verification

nslookup google.com

### HTTP Verification

Open Web Browser

http://172.16.10.9

### DHCP Verification

Obtain IP automatically

---

## Expected Results

✔ OSPF neighbors formed

✔ Dynamic routes learned

✔ NAT translations generated

✔ Web Server reachable

✔ DNS resolution working

✔ DHCP service operational

✔ ACL filtering enforced

✔ Unauthorized traffic blocked

---

## Learning Outcomes

- Cisco ASA Firewall Security
- Advanced ACL Implementation
- DMZ Deployment
- Dynamic NAT/PAT
- OSPF Routing
- Enterprise Network Security Design