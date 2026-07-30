# LAB 33 - Configure DHCP Relay Agent on Cisco Multilayer Switch (IP Helper Address)

## Objective

The objective of this lab is to configure a Cisco Multilayer Switch as a DHCP Relay Agent using the `ip helper-address` command. This enables clients in a different subnet to receive IP addresses from a centralized DHCP server.

---

## Network Topology

### DHCP Server Network
- Network: 192.168.11.0/24
- DHCP Server IP: 192.168.11.254

### Client Network
- Network: 192.168.22.0/24
- Gateway: 192.168.22.1

### Devices Used

- Cisco 3650 Multilayer Switch
- Cisco 2960 Switch (2)
- DHCP Server
- 5 Client PCs

---

## IP Addressing

| Device | Interface | IP Address |
|----------|-----------|------------|
| DHCP Server | Fa0 | 192.168.11.254 |
| MLS | Gi1/0/1 | 192.168.11.1/24 |
| MLS | Gi1/0/2 | 192.168.22.1/24 |
| PCs | DHCP | Automatic |

---

## Configuration Steps

### Step 1
Configure Layer-3 interfaces on the Multilayer Switch.

### Step 2
Enable routing between networks.

### Step 3
Configure the DHCP pool on the DHCP Server.

### Step 4
Configure the `ip helper-address` on the client VLAN interface.

### Step 5
Configure all PCs for DHCP.

### Step 6
Verify IP assignment.

---

## Verification Commands

show ip interface brief

show running-config

show ip route

ipconfig /all

ping 192.168.11.254

---

## Expected Result

- Clients receive IP addresses automatically.
- DHCP Discover packets are forwarded by the Relay Agent.
- Successful communication between different networks.
- End-to-end connectivity is verified.

---

## Technologies Used

- DHCP
- DHCP Relay Agent
- IP Helper Address
- Layer 3 Switching
- Inter-VLAN Routing
- Cisco IOS
- Cisco Packet Tracer

---

## Learning Outcome

After completing this lab you will understand:

- Working of DHCP Relay Agent
- Why DHCP Broadcast cannot cross routers
- Purpose of IP Helper Address
- Layer 3 Switching
- Centralized DHCP Server implementation