# SSH Configuration on Cisco Router

## 📌 Project Overview
This lab demonstrates how to configure SSH on a Cisco Router for secure remote access. Two PCs are connected to a switch, which is connected to the router. SSH is configured so that devices can securely access the router remotely.

## 🖥️ Topology

PC1 ----\
          Switch ---- Router (R1)
PC2 ----/

## 📡 IP Addressing

| Device | Interface | IP Address | Subnet Mask | Default Gateway |
|--------|-----------|------------|-------------|----------------|
| R1 | G0/0 | 192.168.10.1 | 255.255.255.0 | - |
| PC1 | Fa0 | 192.168.10.5 | 255.255.255.0 | 192.168.10.1 |
| PC2 | Fa0 | 192.168.10.6 | 255.255.255.0 | 192.168.10.1 |

## 🎯 Objectives

- Configure router interface
- Enable SSH access
- Create local user authentication
- Secure remote login
- Verify SSH connection

## ⚙️ Requirements

- Cisco Packet Tracer
- Basic networking knowledge
- SSH configuration knowledge

## 🔐 SSH Configuration Steps

1. Configure router IP address
2. Set hostname
3. Configure domain name
4. Create local username
5. Generate RSA key
6. Enable SSH
7. Configure VTY lines

## ✅ Verification

Test SSH connection from PC:
ssh -l admin 192.168.10.1


## 🎓 Learning Outcomes

After completing this lab you will learn:

- SSH Configuration
- Secure Remote Access
- Cisco Router Configuration
- Network Security Basics
