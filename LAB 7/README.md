## 🌐 Remote Access using Telnet (Cisco Packet Tracer)

## 🎯 Objective
To configure remote access on a network device using Telnet protocol and allow an admin PC to access the switch remotely.

---

## 🖧 Topology Overview
- 1 Router (R1)
- 1 Switch (Remote Controlled Switch)
- 1 Admin PC (192.168.1.10)
- 2 User PCs (192.168.2.10, 192.168.2.20)

### 🌍 Networks:
- Admin Network → 192.168.1.0/24  
- User Network → 192.168.2.0/24  

---

## ⚙️ Configuration Summary
- Switch assigned IP address (VLAN 1)
- Default gateway configured
- Hostname and domain name set
- Username and password configured
- VTY lines configured for Telnet access
- Telnet enabled for remote login

---

## 🔐 Key Concept: Telnet
- Telnet is used for remote device access
- Works over TCP port 23
- Requires IP connectivity between devices

⚠️ Note: Telnet is not secure (no encryption), used only for learning

---

## 🧪 Result
- Admin PC successfully connects to switch using Telnet
- Remote CLI access achieved
- Network device can be controlled remotely

---

## 🧠 Learning Outcome
- Remote access configuration
- Telnet setup on switch
- Basic network connectivity
- Device management using CLI
