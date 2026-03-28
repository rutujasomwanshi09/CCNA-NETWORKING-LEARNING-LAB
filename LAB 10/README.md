# 🔗 EtherChannel Configuration using LACP

## 🎯 Objective
To configure EtherChannel using LACP protocol between multiple switches to increase bandwidth and provide redundancy.

---

## 🖧 Topology Overview
- 4 Access Switches (S1, S2, S3, S4)
- 1 Multi-Layer Switch (MLS)
- Multiple links between switches
- EtherChannel configured using LACP

---

## ⚙️ Configuration Summary
- Interfaces grouped using channel-group
- LACP mode active/passive used
- Port-channel interface configured
- Load balancing and redundancy achieved

---

## 🔗 LACP Concept
LACP (Link Aggregation Control Protocol) allows multiple physical links to be combined into one logical link.

Modes:
- active → actively negotiates EtherChannel
- passive → waits for LACP packets

Active + Passive = Works ✅  
Passive + Passive = No channel ❌  

---

## 🧪 Result
- Multiple links combined into single logical link
- Increased bandwidth
- Redundancy provided
- Load balancing enabled

---

## 📁 Files Included
- README.md
- commands.txt
- topology screenshot
- packet tracer file (.pkt)

---

## 🧠 Learning Outcome
- EtherChannel configuration
- LACP protocol
- Port-channel interface
- Network redundancy
- Bandwidth aggregation