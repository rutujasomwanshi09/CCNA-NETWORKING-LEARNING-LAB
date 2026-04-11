# Inter-VLAN Routing using Multilayer Switch (SVI)

## 📌 Project Overview

This project demonstrates **Inter-VLAN Routing using Multilayer Switch (SVI)** in Cisco Packet Tracer.
Different departments are placed in separate VLANs and communication between them is enabled using **Layer 3 Switch**.

---

## 🏢 Network Topology

Three Departments:

| Department | VLAN    | Network         |
| ---------- | ------- | --------------- |
| IT         | VLAN 10 | 192.168.10.0/24 |
| HR         | VLAN 20 | 192.168.20.0/24 |
| FIN        | VLAN 30 | 192.168.30.0/24 |

---

## 🎯 Objectives

* Create VLANs
* Assign ports to VLANs
* Configure trunk link
* Configure SVI interfaces
* Enable IP Routing
* Verify connectivity

---

## 🧱 Devices Used

* 1 Multilayer Switch
* 1 Access Switch
* 6 PCs
* Ethernet cables

---

## 🌐 IP Addressing

### VLAN 10 - IT

* PC0 → 192.168.10.2
* PC1 → 192.168.10.3
* Default Gateway → 192.168.10.1

### VLAN 20 - HR

* PC2 → 192.168.20.2
* PC3 → 192.168.20.3
* Default Gateway → 192.168.20.1

### VLAN 30 - FIN

* PC4 → 192.168.30.2
* PC5 → 192.168.30.3
* Default Gateway → 192.168.30.1

---

## ⚙️ Configuration Steps

### Step 1

Create VLANs on Multilayer Switch

### Step 2

Assign ports to VLANs

### Step 3

Configure Trunk Port

### Step 4

Configure SVI Interfaces

### Step 5

Enable IP Routing

---

## ✅ Verification

Ping from:

PC1 → PC4

```
ping 192.168.30.2
```

If successful, Inter-VLAN routing working properly.

------------------------------------------------------------

## 👨‍💻 Author

Network Lab Practice
Inter-VLAN Routing using Multilayer Switch

---------------------------------------------------------------------
