# 🌐 VLAN Trunking Protocol (VTP) Configuration - Cisco Packet Tracer

## 📌 Aim
To configure VLAN Trunking Protocol (VTP) in a multi-switch network to centrally manage VLANs using a VTP Server and Clients.

---

## 🧠 Theory

VTP (VLAN Trunking Protocol) is used to manage VLAN configurations across multiple switches.

### 🔹 VTP Modes:
- **Server** → Creates, modifies VLANs
- **Client** → Receives VLAN info from server
- **Transparent** → Forwards but doesn’t store

### 🔹 Key Concepts:
- Domain name must match
- Password must match
- Trunk links required between switches

---

## 🛠️ Topology Description

- 1 VTP Server (Switch1)
- Multiple VTP Clients (Switch2, Switch3, Switch4)
- VLANs created:
  - VLAN 10 → IT
  - VLAN 20 → HR
  - VLAN 30 → FIR
  - VLAN 40 → AD
  - VLAN 50 → PRO

---

## ⚙️ Configuration Steps

### Step 1: Configure VTP Server
- Set VTP mode to server
- Configure domain and password
- Create VLANs

### Step 2: Configure VTP Clients
- Set VTP mode to client
- Configure same domain and password

### Step 3: Configure Trunk Links
- Enable trunking between switches

---

## ✅ Result

- VLANs created on server are automatically propagated to all client switches.
- Network becomes centralized and easier to manage.

---

## ⚠️ Precautions

- Domain name must be same on all switches
- Password must match
- Use trunk links between switches
- Avoid accidental deletion on server

---

## 📂 Files Included

- commands.txt
- Topology Screenshot
- This README

---

🚀 This lab demonstrates centralized VLAN management using VTP.