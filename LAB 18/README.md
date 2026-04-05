# ACL for VTY Interface (SSH Access Control)

## 📌 Project Title

ACL for VTY Interface using SSH (Secure Remote Access)

---

## 🎯 Objective

This lab demonstrates how to:

* Configure SSH Remote Access
* Apply ACL on VTY Lines
* Allow only authorized users
* Block unauthorized access

---

## 🏗️ Topology Overview

Network consists of:

* 1 Router
* 1 Switch
* 1 Sysadmin PC (IT Department)
* 4 Sales Department PCs

---

## 🌐 Network Details

### IT Department

Network: 192.168.1.0/24
Sysadmin PC: 192.168.1.5
Gateway: 192.168.1.1

---

### Sales Department

Network: 192.168.2.0/24

PC0 : 192.168.2.8
PC1 : 192.168.2.7
PC2 : 192.168.2.6
PC3 : 192.168.2.5

Switch VLAN 1: 192.168.2.254

---

## 🔐 Security Implementation

### Step 1

Configure SSH on Switch

### Step 2

Create User Authentication

### Step 3

Create ACL

### Step 4

Apply ACL on VTY lines

---

## ⚙️ Security Goal

Only Sysadmin PC (192.168.1.5)
Can access switch remotely using SSH

All other users blocked

---

## 🔍 Verification Steps

* SSH from Sysadmin PC → Should Work
* SSH from Sales PCs → Should Fail

---

## 🛠️ Tools Used

* Cisco Packet Tracer
* SSH Configuration
* Access Control List (ACL)
* VTY Security

---

## 📚 Learning Outcomes

* SSH configuration
* ACL configuration
* VTY security
* Network access control

---
