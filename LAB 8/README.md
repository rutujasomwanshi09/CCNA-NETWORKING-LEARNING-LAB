## Remote Access Using SSH - Cisco Packet Tracer

## 📌 Project Overview
This project demonstrates how to configure **Secure Remote Access using SSH** on a Cisco Switch.  
An Admin PC remotely connects to the switch securely using SSH protocol.

## 🎯 Objective
- Configure SSH on Cisco Switch
- Enable secure remote login
- Connect Admin PC to switch using SSH
- Disable Telnet (secure configuration)

## 🖥️ Topology

Devices Used:
- 1 Router (Cisco 2911)
- 1 Switch (Cisco 2960)
- 3 PCs
  - Admin-PC
  - User-1
  - User-2

## 🌐 IP Addressing

| Device | IP Address | Network |
|--------|------------|---------|
| Admin-PC | 192.168.1.10 | 192.168.1.0/24 |
| Switch VLAN 1 | 192.168.2.254 | 192.168.2.0/24 |
| User-1 | 192.168.2.10 | 192.168.2.0/24 |
| User-2 | 192.168.2.20 | 192.168.2.0/24 |

## 🔐 SSH Configuration Steps

1. Configure VLAN interface
2. Assign IP Address
3. Configure Default Gateway
4. Enable SSH Version 2
5. Create Username and Password
6. Generate RSA Keys
7. Configure VTY Lines for SSH
8. Test SSH from Admin-PC

## 🧪 Testing

From Admin-PC:
ssh -l Admin 192.168.2.254


## ✅ Output

Admin PC successfully connects to switch using SSH.


## 🛠️ Tools Used

- Cisco Packet Tracer
- Networking Concepts
- SSH Protocol

