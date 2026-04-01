# Securing All Unused Ports in a Switch

## 📌 Project Title
Securing All Unused Ports Using VLAN and Port Security

## 🎯 Objective
To secure unused switch ports by assigning them to a blackhole VLAN and shutting them down.

## 🖥️ Devices Used

- 2 Switches (2960)
- Multiple PCs
- VLAN Configuration

## 🧩 VLAN Configuration

| VLAN | Name |
|------|------|
| VLAN 10 | IT |
| VLAN 20 | HR |
| VLAN 30 | FIN |
| VLAN 999 | BLACKHOLE |

## 🔐 Security Concept

- Unused ports assigned to VLAN 999
- VLAN 999 used as Blackhole VLAN
- Unused ports shutdown

## 📡 Topology Description

- Two switches connected using trunk
- Multiple VLANs created
- Unused ports secured using VLAN 999

## 🧪 Verification Commands

show vlan brief  
show interfaces trunk  
show running-config  

## ✅ Expected Result

- VLANs created successfully
- Unused ports secured
- Network protected from unauthorized access

## 📚 Learning Outcome

- VLAN Configuration  
- Switch Security  
- Blackhole VLAN  
- Port Security  