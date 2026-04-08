# TELNET Configuration on Router (Cisco Packet Tracer)

## 📌 Project Overview

This project demonstrates how to configure **Telnet access on a Cisco Router** using **Cisco Packet Tracer**.
Multiple PCs are connected to a switch, and the switch is connected to a router.
Telnet is configured so that PCs can remotely access the router.

---

## 🎯 Objective

* Configure Router IP Address
* Enable Telnet access
* Create Username and Password
* Allow Remote Login from PCs
* Verify Telnet Connectivity

---

## 🖥️ Topology Diagram

Router → Switch → PC1, PC2, PC3

Network: **192.168.1.0/24**

---

## 📡 IP Addressing Table

| Device | IP Address  | Default Gateway |
| ------ | ----------- | --------------- |
| Router | 192.168.1.1 | -               |
| PC1    | 192.168.1.5 | 192.168.1.1     |
| PC2    | 192.168.1.6 | 192.168.1.1     |
| PC3    | 192.168.1.7 | 192.168.1.1     |

---

## 🔧 Devices Used

* Cisco Router (2811)
* Cisco Switch (2960)
* 3 PCs
* Copper Straight Through Cable

---

## ⚙️ Configuration Steps

### Step 1: Configure Router IP

Assign IP address to router interface.

### Step 2: Configure Hostname

Set router hostname.

### Step 3: Configure Username and Password

Create local login credentials.

### Step 4: Enable Telnet Access

Configure VTY lines.

### Step 5: Verify Configuration

Test Telnet from PC.

---

## 🧪 Verification

### Ping Router FROM PCs

```
ping 192.168.1.1
```

### Telnet Router

```
telnet 192.168.1.1
```

---

## ✅ Expected Output

* Successful ping reply
* Telnet login prompt
* Router access via remote login

---

## 📚 Learning Outcome

After completing this lab you will learn:

* Telnet configuration
* Remote Router access
* VTY configuration
* Network troubleshooting
* Basic Cisco security

---
