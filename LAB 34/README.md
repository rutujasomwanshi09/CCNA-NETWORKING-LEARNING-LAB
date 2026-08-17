# 🌐 LAB 34 — STATIC ROUTING CONFIGURATION USING CISCO PACKET TRACER

<p align="center">

### 🚀 Cisco Packet Tracer • IPv4 • Static Routing

</p>

---

## 🎯 1. OBJECTIVE

| Item | Details |
|---|---|
| Routing Type | **Static Routing** |
| Tool | **Cisco Packet Tracer** |
| Routers | **KE-R1, ENG-R1, PAK-R1, INDIA-R1** |
| Kenya LAN | `192.168.10.0/24` |
| India LAN | `192.168.20.0/24` |
| Goal | Enable communication between Kenya and India LANs |

### 🔄 Topology Path

```text
PC0/PC1/PC2
    │
192.168.10.0/24
    │
  KE-R1
    │ 10.10.10.0/30
  ENG-R1
    │ 20.20.20.0/30
  PAK-R1
    │ 30.30.30.0/30
 INDIA-R1
    │
192.168.20.0/24
    │
PC3/PC4/PC5
```

---

# 🌐 2. IP ADDRESSING TABLE

| Router | Interface | IP Address | Subnet Mask | Connected To |
|---|---|---|---|---|
| **KE-R1** | G0/0 | `192.168.10.1` | `255.255.255.0` | Kenya LAN |
| **KE-R1** | G0/1 | `10.10.10.1` | `255.255.255.252` | ENG-R1 |
| **ENG-R1** | G0/0 | `10.10.10.2` | `255.255.255.252` | KE-R1 |
| **ENG-R1** | G0/1 | `20.20.20.1` | `255.255.255.252` | PAK-R1 |
| **PAK-R1** | G0/0 | `20.20.20.2` | `255.255.255.252` | ENG-R1 |
| **PAK-R1** | G0/1 | `30.30.30.1` | `255.255.255.252` | INDIA-R1 |
| **INDIA-R1** | G0/0 | `30.30.30.2` | `255.255.255.252` | PAK-R1 |
| **INDIA-R1** | G0/1 | `192.168.20.1` | `255.255.255.0` | India LAN |

---

# ⚙️ 3. KE-R1 CONFIGURATION

### 📌 What was configured?

| Command / Configuration | Purpose |
|---|---|
| `interface g0/0` | Select Kenya LAN interface |
| `ip address 192.168.10.1 255.255.255.0` | Assign Kenya LAN gateway IP |
| `no shutdown` | Enable G0/0 |
| `interface g0/1` | Select link to ENG-R1 |
| `ip address 10.10.10.1 255.255.255.252` | Assign point-to-point IP |
| `no shutdown` | Enable G0/1 |
| `ip route 192.168.20.0 ...` | Add route to India LAN |
| `write memory` | Save configuration |

### 💻 Commands Entered on KE-R1

```bash
enable
configure terminal

interface g0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
exit

interface g0/1
ip address 10.10.10.1 255.255.255.252
no shutdown
exit

ip route 192.168.20.0 255.255.255.0 10.10.10.2

end
write memory
```

### 🧠 Static Route on KE-R1

| Destination | Next Hop | Meaning |
|---|---|---|
| `192.168.20.0/24` | `10.10.10.2` | India LAN traffic goes to ENG-R1 |

---

# ⚙️ 4. ENG-R1 CONFIGURATION

### 📌 What was configured?

| Command / Configuration | Purpose |
|---|---|
| `interface g0/0` | Select link to KE-R1 |
| `ip address 10.10.10.2 ...` | Assign IP to G0/0 |
| `interface g0/1` | Select link to PAK-R1 |
| `ip address 20.20.20.1 ...` | Assign IP to G0/1 |
| Static route to `192.168.10.0/24` | Return path to Kenya |
| Static route to `192.168.20.0/24` | Forward path to India |
| `write memory` | Save configuration |

### 💻 Commands Entered on ENG-R1

```bash
enable
configure terminal

interface g0/0
ip address 10.10.10.2 255.255.255.252
no shutdown
exit

interface g0/1
ip address 20.20.20.1 255.255.255.252
no shutdown
exit

ip route 192.168.10.0 255.255.255.0 10.10.10.1
ip route 192.168.20.0 255.255.255.0 20.20.20.2

end
write memory
```

### 🧠 Static Routes on ENG-R1

| Destination | Next Hop | Meaning |
|---|---|---|
| `192.168.10.0/24` | `10.10.10.1` | Kenya LAN via KE-R1 |
| `192.168.20.0/24` | `20.20.20.2` | India LAN via PAK-R1 |

---

# ⚙️ 5. PAK-R1 CONFIGURATION

### 📌 What was configured?

| Command / Configuration | Purpose |
|---|---|
| `interface g0/0` | Select link to ENG-R1 |
| `ip address 20.20.20.2 ...` | Assign IP to G0/0 |
| `interface g0/1` | Select link to INDIA-R1 |
| `ip address 30.30.30.1 ...` | Assign IP to G0/1 |
| Static route to `192.168.10.0/24` | Return path to Kenya |
| Static route to `192.168.20.0/24` | Forward path to India |
| `write memory` | Save configuration |

### 💻 Commands Entered on PAK-R1

```bash
enable
configure terminal

interface g0/0
ip address 20.20.20.2 255.255.255.252
no shutdown
exit

interface g0/1
ip address 30.30.30.1 255.255.255.252
no shutdown
exit

ip route 192.168.10.0 255.255.255.0 20.20.20.1
ip route 192.168.20.0 255.255.255.0 30.30.30.2

end
write memory
```

### 🧠 Static Routes on PAK-R1

| Destination | Next Hop | Meaning |
|---|---|---|
| `192.168.10.0/24` | `20.20.20.1` | Kenya LAN via ENG-R1 |
| `192.168.20.0/24` | `30.30.30.2` | India LAN via INDIA-R1 |

---

# ⚙️ 6. INDIA-R1 CONFIGURATION

### 📌 What was configured?

| Command / Configuration | Purpose |
|---|---|
| `interface g0/0` | Select link to PAK-R1 |
| `ip address 30.30.30.2 ...` | Assign IP to G0/0 |
| `interface g0/1` | Select India LAN interface |
| `ip address 192.168.20.1 ...` | Assign India LAN gateway IP |
| Static route to `192.168.10.0/24` | Return path to Kenya |
| `write memory` | Save configuration |

### 💻 Commands Entered on INDIA-R1

```bash
enable
configure terminal

interface g0/0
ip address 30.30.30.2 255.255.255.252
no shutdown
exit

interface g0/1
ip address 192.168.20.1 255.255.255.0
no shutdown
exit

ip route 192.168.10.0 255.255.255.0 30.30.30.1

end
write memory
```

### 🧠 Static Route on INDIA-R1

| Destination | Next Hop | Meaning |
|---|---|---|
| `192.168.10.0/24` | `30.30.30.1` | Kenya LAN via PAK-R1 |

---

# 💻 7. PC CONFIGURATION

## 🇰🇪 Kenya LAN

| PC | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| **PC0** | `192.168.10.10` | `255.255.255.0` | `192.168.10.1` |
| **PC1** | `192.168.10.20` | `255.255.255.0` | `192.168.10.1` |
| **PC2** | `192.168.10.30` | `255.255.255.0` | `192.168.10.1` |

**Packet Tracer:** `PC → Desktop → IP Configuration`

## 🇮🇳 India LAN

| PC | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| **PC3** | `192.168.20.10` | `255.255.255.0` | `192.168.20.1` |
| **PC4** | `192.168.20.20` | `255.255.255.0` | `192.168.20.1` |
| **PC5** | `192.168.20.30` | `255.255.255.0` | `192.168.20.1` |

**Packet Tracer:** `PC → Desktop → IP Configuration`

---

# 🔍 8. VERIFICATION COMMANDS

| Command | Run On | What It Checks |
|---|---|---|
| `show ip interface brief` | All Routers | Interface IP + status |
| `show ip route` | All Routers | Static + connected routes |
| `show running-config` | All Routers | Current configuration |
| `ping <IP>` | Router / PC | Connectivity |
| `tracert <IP>` | PC | Complete packet path |

### 🟢 Check Interfaces

```bash
show ip interface brief
```

Expected:

```text
Status     Protocol
up         up
```

### 🟢 Check Routing Table

```bash
show ip route
```

Static routes are identified by:

```text
S
```

---

# 📡 9. CONNECTIVITY TEST

### PC0 → PC5

From **PC0 → Desktop → Command Prompt**:

```bash
ping 192.168.20.30
```

Expected path:

```text
PC0
 ↓
KE-R1
 ↓
ENG-R1
 ↓
PAK-R1
 ↓
INDIA-R1
 ↓
PC5
```

### 🔎 Trace Path

From PC0:

```bash
tracert 192.168.20.30
```

---

# 🧰 10. IMPORTANT COMMANDS

| Command | Purpose |
|---|---|
| `enable` | Enter privileged EXEC mode |
| `configure terminal` | Enter global configuration mode |
| `interface g0/0` | Select router interface |
| `ip address X.X.X.X MASK` | Configure IP address |
| `no shutdown` | Enable interface |
| `ip route NETWORK MASK NEXT-HOP` | Configure static route |
| `show ip interface brief` | Verify interfaces |
| `show ip route` | Verify routing table |
| `show running-config` | View active configuration |
| `ping X.X.X.X` | Test connectivity |
| `tracert X.X.X.X` | Trace path from PC |
| `write memory` | Save configuration |

---

# 🧠 11. STATIC ROUTING SUMMARY

| Router | Destination Network | Next Hop | Why? |
|---|---|---|---|
| **KE-R1** | `192.168.20.0/24` | `10.10.10.2` | Reach India LAN |
| **ENG-R1** | `192.168.10.0/24` | `10.10.10.1` | Reach Kenya LAN |
| **ENG-R1** | `192.168.20.0/24` | `20.20.20.2` | Reach India LAN |
| **PAK-R1** | `192.168.10.0/24` | `20.20.20.1` | Reach Kenya LAN |
| **PAK-R1** | `192.168.20.0/24` | `30.30.30.2` | Reach India LAN |
| **INDIA-R1** | `192.168.10.0/24` | `30.30.30.1` | Reach Kenya LAN |

---

# 🏁 12. RESULT

> ✅ **Static Routing successfully configured between Kenya LAN and India LAN.**

### Final Test Commands

```bash
show ip interface brief
show ip route
ping 192.168.20.30
tracert 192.168.20.30
```

### 📚 Topics Practiced

| Topic | Status |
|---|---|
| IPv4 Addressing | ✅ |
| Subnetting | ✅ |
| Router Interface Configuration | ✅ |
| Static Routing | ✅ |
| Next-Hop Routing | ✅ |
| Default Gateway | ✅ |
| Routing Table Verification | ✅ |
| Ping | ✅ |
| Traceroute | ✅ |
| Cisco IOS Commands | ✅ |

---

<p align="center">

### ⭐ LAB 34 — STATIC ROUTING ⭐

**Cisco Packet Tracer • IPv4 • Static Routing • Network Configuration**

</p>
