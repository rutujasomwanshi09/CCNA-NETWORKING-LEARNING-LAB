# README.md

## DHCP Relay Agent Configuration on Cisco Router

### Project Overview

This lab demonstrates how to configure a **DHCP Relay Agent** on a Cisco Router. The DHCP server is located in a different network (**192.168.20.0/24**) than the client PCs (**192.168.10.0/24**). Since DHCP broadcasts cannot cross routers, the router forwards DHCP requests to the remote DHCP server using the `ip helper-address` command.

### Objective

* Configure a centralized DHCP Server.
* Configure a Cisco Router as a DHCP Relay Agent.
* Allow clients from a different subnet to receive IP addresses automatically.
* Verify successful DHCP lease allocation.

### Topology Details

| Device       | Interface   | IP Address      |
| ------------ | ----------- | --------------- |
| Router0 G0/1 | LAN Side    | 192.168.10.1/24 |
| Router0 G0/0 | Server Side | 192.168.20.1/24 |
| DHCP Server  | Fa0         | 192.168.20.5/24 |
| PCs          | DHCP        | Dynamic         |

### Network Diagram

**Client Network**

* Network: 192.168.10.0/24
* Default Gateway: 192.168.10.1

**Server Network**

* Network: 192.168.20.0/24
* DHCP Server: 192.168.20.5

### DHCP Pool Configuration

| Parameter       | Value         |
| --------------- | ------------- |
| Pool Name       | OFFICE        |
| Network         | 192.168.10.0  |
| Subnet Mask     | 255.255.255.0 |
| Default Gateway | 192.168.10.1  |
| DNS Server      | 192.168.20.5       |
| Start IP        | 192.168.10.21 |

### Verification Steps

#### Verify Router Interfaces

```bash
show ip interface brief
```

#### Verify DHCP Relay

```bash
show running-config
```

#### Verify Client IP Assignment

On PC:

ipconfig


#### Test Connectivity


ping 192.168.10.1
ping 192.168.20.2

### Expected Result

* All PCs receive IP addresses automatically from the DHCP Server.
* Router forwards DHCP Discover packets to the server.
* End-to-end connectivity is successful.

### Technologies Used

* Cisco Packet Tracer
* Cisco 2911 Router
* Cisco 2960 Switch
* DHCP Protocol
* DHCP Relay Agent

### Learning Outcomes

* Understanding DHCP broadcast limitations.
* Configuring DHCP Relay Agent.
* Centralized DHCP deployment.
* Inter-network communication.

---

# COMMANDS.md

## Router Configuration

### Enter Privileged Mode

```bash
enable
```

### Enter Global Configuration

```bash
configure terminal
```

### Configure LAN Interface

```bash
interface gigabitEthernet 0/1
ip address 192.168.10.1 255.255.255.0
no shutdown

ip helper-address 192.168.20.5
exit
```

### Configure Server Side Interface

```bash
interface gigabitEthernet 0/0
ip address 192.168.20.1 255.255.255.0
no shutdown
exit
```

### Save Configuration

```bash
end
write memory
```

---

## DHCP Server Configuration

### Desktop → IP Configuration

```text
IP Address: 192.168.20.5
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.20.1
DNS Server: 192.168.20.5
```

### Services → DHCP

```text
DHCP Service: ON

Pool Name: IT-DEPT-POOL

Default Gateway: 192.168.10.1

DNS Server: 192.168.20.5

Start IP Address: 192.168.10.21

Subnet Mask: 255.255.255.0

Maximum Users: 200
```

Click **Add**.

---

## PC Configuration

### Desktop → IP Configuration

```text
Select DHCP
```

The PCs will automatically receive:

```text
IP Address : 192.168.10.x
Gateway    : 192.168.10.1
DNS        : 192.168.20.5
```

---

## Verification Commands

### Router

```bash
show ip interface brief
show running-config
show ip route
```

### PC

```bash
ipconfig
ping 192.168.10.1
ping 192.168.20.5
```

---

