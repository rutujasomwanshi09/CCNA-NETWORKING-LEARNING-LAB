# Lab 01 – Basic Switch Configuration (2960-24TT)

## Objective
To configure a Cisco Layer 2 switch with basic settings such as hostname, passwords, banner, VLAN interface, and management IP for network communication.

---

## Topology
- 1 Switch (Cisco 2960-24TT)
- 1 PC
- Ethernet connection between PC and Switch

---

## Tool Used
Cisco Packet Tracer

---

## Configuration Overview

In this lab, the following configurations were performed:

- Switch hostname configured
- Enable password set
- Console and VTY password configured
- Login security enabled
- Banner message configured
- Domain name and username configured
- Password encryption enabled
- System clock configured
- VLAN 1 interface activated
- Management IP assigned to switch
- Default gateway configured
- Configuration saved permanently


---

# Verification Commands

Check configuration:

S1# show running-config

Check interface status:

S1# show ip interface brief

## IP Addressing

| Device | IP Address       | Subnet Mask     |
|--------|----------------|----------------|
| Switch | 192.168.10.254 | 255.255.255.0  |
| Gateway| 192.168.10.1   | -              |

---

## Important Notes

- Commands are already included in the topology file.
- VLAN 1 is used as the management VLAN.
- `no shutdown` command is required to activate VLAN interface.
- `service password-encryption` ensures all passwords are encrypted.
- `ip default-gateway` is necessary for remote management.

---

## Verification Commands

Use the following commands to verify configuration:

show running-config  
show ip interface brief  
show vlan brief  

---

## Result

The switch was successfully configured with basic security, management IP, and connectivity settings. The device is ready for further network configuration.
