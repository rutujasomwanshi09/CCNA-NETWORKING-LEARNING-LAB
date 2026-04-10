# Inter-VLAN Routing using Router-on-a-Stick

## 📌 Project Overview
This project demonstrates Inter-VLAN routing using Router-on-a-Stick method in Cisco Packet Tracer. Multiple VLANs are configured on a Layer 2 switch, and routing between VLANs is achieved using a router with sub-interfaces.

---

## 🏗️ Network Topology

Router: 2811  
Switch: 2960  
PCs: 6  

VLAN Details:

VLAN 10 → 192.168.1.0/24  
VLAN 20 → 192.168.2.0/24  
VLAN 30 → 192.168.3.0/24  

---

## 📍 VLAN Structure

| VLAN | Department | Network |
|------|------------|---------|
| 10 | HR | 192.168.1.0/24 |
| 20 | Finance | 192.168.2.0/24 |
| 30 | IT | 192.168.3.0/24 |

---

## ⚙️ Configuration Steps

### Step 1: Create VLANs
- VLAN 10
- VLAN 20
- VLAN 30

### Step 2: Assign VLANs to Switch Ports

### Step 3: Configure Trunk Port

### Step 4: Configure Router Subinterfaces

### Step 5: Verify Connectivity

---

## 🔌 IP Addressing

PC0 → 192.168.1.5  
PC1 → 192.168.1.6  

PC2 → 192.168.2.5  
PC3 → 192.168.2.6  

PC4 → 192.168.3.5  
PC5 → 192.168.3.6  

Gateway:

VLAN 10 → 192.168.1.1  
VLAN 20 → 192.168.2.1  
VLAN 30 → 192.168.3.1  

---

## 🧪 Verification

Ping between different VLANs:

Example:

PC0 → PC3  
PC1 → PC5  
PC2 → PC4  

## CHECK:
FROM PC2: PING 192.168.1.5
---

## 🎯 Objective

To understand:

- VLAN configuration
- Trunk configuration
- Router-on-a-stick
- Inter-VLAN Routing

---

## 🛠️ Tools Used

- Cisco Packet Tracer
- Cisco Router 2811
- Cisco Switch 2960

