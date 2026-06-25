# 🔗 802.1Q Trunk Native VLAN Configuration (Cisco Packet Tracer)

## 🎯 Objective
To configure VLANs and implement 802.1Q trunking with a native VLAN between two switches.

---

## 🖧 Topology Overview
- 2 Switches connected using trunk links (Fa0/1 & Fa0/2)
- 2 PCs connected to switches
- VLANs:
  - VLAN 10 → IT
  - VLAN 20 → HR
  - VLAN 99 → Native VLAN

---

## ⚙️ Configuration Summary
- VLAN 10 and VLAN 20 created for users
- VLAN 99 configured as Native VLAN
- Trunk links configured between switches
- Native VLAN set on trunk interfaces

---

## 🔗 Key Concept: Native VLAN
- Native VLAN is the default VLAN for untagged traffic on trunk links
- In this lab:
  - Native VLAN = VLAN 99
- Both switches must have same native VLAN

---

## 🧪 Result
- Devices in same VLAN can communicate
- Trunk carries multiple VLAN traffic
- Native VLAN handles untagged frames


---

## 🧠 Learning Outcome
- VLAN creation
- 802.1Q trunk configuration
- Native VLAN concept
- Inter-switch communication