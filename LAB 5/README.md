# 🔗 Trunk Allowed/Denied VLAN Configuration (Cisco Packet Tracer)

## 🎯 Objective
To configure VLANs and control traffic over trunk links by allowing and denying specific VLANs between switches, including restricted VLANs for security testing.

---

## 🖧 Topology Overview
- 2 Switches connected via trunk link
- Multiple VLANs configured for different departments and testing scenarios

### 🌐 VLAN Details:
- VLAN 10 → IT (192.168.10.0/24)
- VLAN 20 → HR (192.168.20.0/24)
- VLAN 30 → FIR (192.168.30.0/24)
- VLAN 40 → Hacker1 (Testing Network)
- VLAN 50 → Hacker2 (Testing Network)

- PCs are connected to their respective VLANs on both switches

---

## ⚙️ Configuration Summary
- VLANs (10, 20, 30, 40, 50) created on both switches
- Access ports assigned to corresponding VLANs
- Trunk link configured between switches
- Only selected VLANs allowed on trunk port for secure communication

---

## 🚫 Allowed / Denied VLAN Concept
Trunk links can be restricted to carry only specific VLAN traffic.

### 🔐 Allowed VLANs:
- VLAN 10 (IT)
- VLAN 20 (HR)
- VLAN 30 (FIR)

### ❌ Denied VLANs:
- VLAN 40 (Hacker1)
- VLAN 50 (Hacker2)

👉 Denied VLANs will NOT pass through trunk link

---

## 🔐 Security Insight (Important)
- VLAN 40 & 50 are intentionally created as **untrusted networks (Hacker zones)**
- These VLANs are **blocked on trunk**
- This simulates real-world scenario where malicious or unknown networks are isolated

---

## 🧪 Result
- VLAN 10, 20 & 30 devices can communicate across switches ✅
- VLAN 40, 50 devices cannot communicate across switches ❌
- Network segmentation successfully controls traffic flow

---

🧪 5️⃣ Testing the Connectivity
From PC1 (VLAN 10):

ping 192.168.10.20
✅ Should Work

From PC1 to VLAN 20 PC:

ping 192.168.20.20
❌ Will Not Work (Different VLAN – No routing configured)

## 🧠 Learning Outcome
- VLAN segmentation
- Trunk configuration
- VLAN traffic filtering using allowed list
- Basic network security concept (isolation of untrusted VLANs)