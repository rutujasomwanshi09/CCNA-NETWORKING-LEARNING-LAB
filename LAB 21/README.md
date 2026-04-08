# Connecting Multiple Networks Using Router

## 📌 Project Overview
This lab demonstrates how to connect multiple networks using a router in Cisco Packet Tracer. 
Two different networks are configured and connected using router interfaces.

## 🎯 Objective
- Connect multiple networks using router
- Configure IP addressing
- Set default gateway
- Test connectivity using ping

## 🖥️ Topology

Network 1:
- Network ID: 192.168.1.0/24
- Default Gateway: 192.168.1.1
- Devices: PC0, PC1

Network 2:
- Network ID: 192.168.2.0/24
- Default Gateway: 192.168.2.1
- Devices: PC2, PC3

Router:
- Interface G0/0 → 192.168.1.1
- Interface G0/1 → 192.168.2.1

## ⚙️ Configuration Steps

1. Assign IP to PCs
2. Configure Router Interfaces
3. Set Default Gateway
4. Test Connectivity

## 🧪 Testing

Use ping command:
- from pc0 to pc2
PING 192.168.2.5
PING 192.168.2.6


## ✅ Expected Result

All PCs from both networks should communicate successfully.

## 📚 Concepts Used

- IP Addressing
- Router Configuration
- Default Gateway
- Network Communication
- Packet Tracer Lab

-----------------------------------------------------------------------------