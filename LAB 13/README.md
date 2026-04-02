# STP Security Features: PortFast, BPDU Guard, and Root Guard

## 📌 Overview
This Cisco Packet Tracer topology demonstrates the configuration and behavior of three essential Spanning Tree Protocol (STP) security mechanisms:

- **PortFast** – Enables rapid transition from blocking to forwarding on access ports.
- **BPDU Guard** – Disables a port if a BPDU is received (prevents rogue switch connections).
- **Root Guard** – Prevents unauthorized switches from becoming the root bridge.

## 🖧 Topology Description
- **Root Bridge**: Central switch (e.g., `Switch0`)
- **Non-Root Bridges**: Switches connected to the root bridge
- **End Devices**: PCs connected to access ports
- **Key Label in Topology**: `"PORTFAST + ROOTGUARD"` indicates where these features are applied.

## 🎯 Configuration Goals
1. Enable **PortFast** on all access ports connected to PCs.
2. Enable **BPDU Guard** on the same access ports to prevent loop formation.
3. Enable **Root Guard** on selected ports to protect root bridge position.

## 🧪 Testing & Validation
| Feature       | Test Command                          | Expected Result                          |
|---------------|---------------------------------------|------------------------------------------|
| PortFast      | `show spanning-tree interface fast 0/1` | `EdgePort` = Yes, `OperEdge` = True      |
| BPDU Guard    | Connect a switch to access port       | Port enters `err-disable` state          |
| Root Guard    | `show spanning-tree interface gig 0/1` | Root guard enabled, port blocks superior BPDUs |

## 📁 Files
- `topology.pkt` – Packet Tracer file
- `commands.txt` – CLI commands for all switches
- `README.md` – This file

## 🧠 Key Commands Summary
```cisco
interface fastEthernet 0/1
 spanning-tree portfast
 spanning-tree bpduguard enable
 spanning-tree guard root