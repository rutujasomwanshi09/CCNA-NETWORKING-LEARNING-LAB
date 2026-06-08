# Cisco ASA Firewall Policy Configuration

## Project Overview

This project demonstrates Cisco ASA Firewall Policy Configuration using:

- OSPF Dynamic Routing
- Static Default Routing
- NAT (Network Address Translation)
- Access Control Lists (ACLs)
- DHCP Relay Configuration
- DMZ Security Zone
- Internet Access Control

The topology simulates a real-world enterprise network where the ASA firewall controls communication between the Inside Network, DMZ Network, and Outside Network.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Network Information

### Inside Network

Network: 192.168.100.0/24

Gateway: 192.168.100.1

Security Level: 100

Devices:
- PC0
- PC1
- PC2
- PC3
- PC4

Zone Type:
Trusted

--------------------------------------------------------------------------------------------------------------------------------------------

### DMZ Network

Network: 172.16.10.0/28

Gateway: 172.16.10.1

Security Level: 70

Servers:
- Web Server (172.16.10.9)
- DNS Server (172.16.10.7)
- DHCP Server (172.16.10.10)
- Email Server (172.16.10.8)

Zone Type:
Partially Trusted

-------------------------------------------------------------------------------------------------------------------------------------------

### Outside Network

Network: 8.8.8.0/24

Gateway: 8.8.8.1

Security Level: 0

Devices:
- Google Server
- External Hosts

Zone Type:
Untrusted

-----------------------------------------------------------------------------------------------------------------------------------------------

## Point-to-Point Links

### Router1 ↔ ASA

Network: 10.10.10.0/30

Router1: 10.10.10.2

ASA: 10.10.10.1

--------------------------------------------------------------------------------------------------------------------------------------

### Router2 ↔ ASA

Network: 20.20.20.0/30

Router2: 20.20.20.2

ASA: 20.20.20.1

----------------------------------------------------------------------------------------------------------------------------

## Technologies Used

### Cisco ASA Firewall
- Security Zones
- Access Policies
- ACL Filtering
- NAT Translation

### Routing
- OSPF Process 50
- Static Default Route

### Network Services
- DHCP Relay
- DNS
- Web Service
- Email Service

------------------------------------------------------------------------------------------------------------------------

## Security Policies Implemented

### DMZ Access Policy

Allowed Protocols:
- ICMP
- HTTP (80)
- HTTPS (443)
- DNS (53 TCP/UDP)

### Internet Access Policy

Allowed Protocols:
- ICMP
- HTTP
- HTTPS
- DNS

### NAT Policy

- Inside Users access Internet through Dynamic PAT
- DMZ Servers access Internet through Dynamic PAT

---------------------------------------------------------------------------------------------------------------------

## Verification

### Routing

show route

show ospf

### NAT

show nat

show xlate

### ACL

show access-list

### Connectivity

ping 8.8.8.8

tracert 8.8.8.8

--------------------------------------------------------------------------------------------------------------------------

## Expected Results

✔ OSPF neighbors establish successfully

✔ Routes exchanged dynamically

✔ NAT translations created

✔ DMZ services reachable

✔ Internet access available

✔ Firewall policies enforced

✔ Unauthorized traffic blocked

----------------------------------------------------------------------------------------------------------

## Learning Outcomes

- Cisco ASA Firewall Administration
- OSPF Configuration
- ACL Security Policies
- NAT and PAT
- DMZ Implementation
- Enterprise Security Design
