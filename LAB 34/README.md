<<<<<<< HEAD
# 🌐 LAB 34 — STATIC ROUTING CONFIGURATION USING CISCO PACKET TRACER

<p align="center">

### 🚀 Cisco Packet Tracer • IPv4 • Static Routing
=======
# 🌐 LAB 34 — STATIC ROUTING CONFIGURATION

<p align="center">

### 🚀 Cisco Packet Tracer | IPv4 | Static Routing
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

</p>

---

<<<<<<< HEAD
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
=======
## 🎯 1. LAB OBJECTIVE

| **Item** | **Details** |
|---|---|
| **Routing Type** | Static Routing |
| **Tool** | Cisco Packet Tracer |
| **Routers** | KE-R1, ENG-R1, PAK-R1, INDIA-R1 |
| **Kenya LAN** | `192.168.10.0/24` |
| **India LAN** | `192.168.20.0/24` |
| **Goal** | Establish communication between Kenya and India LANs |

### 🔄 Packet Path

> 🇰🇪 **Kenya LAN** → **KE-R1** → **ENG-R1** → **PAK-R1** → **INDIA-R1** → 🇮🇳 **India LAN**

---

# 🌐 2. IP ADDRESSING

## 🖥️ Router Interfaces

| **Router** | **Interface** | **IP Address** | **Subnet Mask** | **Purpose** |
|---|---|---|---|---|
| **KE-R1** | G0/0 | `192.168.10.1` | `255.255.255.0` | Kenya LAN |
| **KE-R1** | G0/1 | `10.10.10.1` | `255.255.255.252` | KE ↔ ENG |
| **ENG-R1** | G0/0 | `10.10.10.2` | `255.255.255.252` | KE ↔ ENG |
| **ENG-R1** | G0/1 | `20.20.20.1` | `255.255.255.252` | ENG ↔ PAK |
| **PAK-R1** | G0/0 | `20.20.20.2` | `255.255.255.252` | ENG ↔ PAK |
| **PAK-R1** | G0/1 | `30.30.30.1` | `255.255.255.252` | PAK ↔ INDIA |
| **INDIA-R1** | G0/0 | `30.30.30.2` | `255.255.255.252` | PAK ↔ INDIA |
| **INDIA-R1** | G0/1 | `192.168.20.1` | `255.255.255.0` | India LAN |

---

# ⚙️ 3. ROUTER CONFIGURATION

## 🇰🇪 KE-R1

### What was configured?

| **Configuration** | **Details** |
|---|---|
| G0/0 | Kenya LAN IP |
| G0/1 | Connection to ENG-R1 |
| Static Route | Route to India LAN |

### 💻 Commands
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

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

<<<<<<< HEAD
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
=======
### 🧠 Static Route

| **Destination Network** | **Next Hop** | **Purpose** |
|---|---|---|
| `192.168.20.0/24` | `10.10.10.2` | India LAN via ENG-R1 |

---

## 🇬🇧 ENG-R1

### What was configured?

| **Configuration** | **Details** |
|---|---|
| G0/0 | Connection to KE-R1 |
| G0/1 | Connection to PAK-R1 |
| Static Route 1 | Route to Kenya LAN |
| Static Route 2 | Route to India LAN |

### 💻 Commands
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

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

<<<<<<< HEAD
### 🧠 Static Routes on ENG-R1

| Destination | Next Hop | Meaning |
=======
### 🧠 Static Routes

| **Destination Network** | **Next Hop** | **Purpose** |
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec
|---|---|---|
| `192.168.10.0/24` | `10.10.10.1` | Kenya LAN via KE-R1 |
| `192.168.20.0/24` | `20.20.20.2` | India LAN via PAK-R1 |

---

<<<<<<< HEAD
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
=======
## 🇵🇰 PAK-R1

### What was configured?

| **Configuration** | **Details** |
|---|---|
| G0/0 | Connection to ENG-R1 |
| G0/1 | Connection to INDIA-R1 |
| Static Route 1 | Route to Kenya LAN |
| Static Route 2 | Route to India LAN |

### 💻 Commands
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

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

<<<<<<< HEAD
### 🧠 Static Routes on PAK-R1

| Destination | Next Hop | Meaning |
=======
### 🧠 Static Routes

| **Destination Network** | **Next Hop** | **Purpose** |
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec
|---|---|---|
| `192.168.10.0/24` | `20.20.20.1` | Kenya LAN via ENG-R1 |
| `192.168.20.0/24` | `30.30.30.2` | India LAN via INDIA-R1 |

---

<<<<<<< HEAD
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
=======
## 🇮🇳 INDIA-R1

### What was configured?

| **Configuration** | **Details** |
|---|---|
| G0/0 | Connection to PAK-R1 |
| G0/1 | India LAN |
| Static Route | Route to Kenya LAN |

### 💻 Commands
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

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

<<<<<<< HEAD
### 🧠 Static Route on INDIA-R1

| Destination | Next Hop | Meaning |
=======
### 🧠 Static Route

| **Destination Network** | **Next Hop** | **Purpose** |
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec
|---|---|---|
| `192.168.10.0/24` | `30.30.30.1` | Kenya LAN via PAK-R1 |

---

<<<<<<< HEAD
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
=======
# 💻 4. PC CONFIGURATION

## 🇰🇪 Kenya LAN

| **PC** | **IP Address** | **Subnet Mask** | **Default Gateway** |
|---|---|---|---|
| PC0 | `192.168.10.10` | `255.255.255.0` | `192.168.10.1` |
| PC1 | `192.168.10.20` | `255.255.255.0` | `192.168.10.1` |
| PC2 | `192.168.10.30` | `255.255.255.0` | `192.168.10.1` |

**Configure:** `PC → Desktop → IP Configuration`

## 🇮🇳 India LAN

| **PC** | **IP Address** | **Subnet Mask** | **Default Gateway** |
|---|---|---|---|
| PC3 | `192.168.20.10` | `255.255.255.0` | `192.168.20.1` |
| PC4 | `192.168.20.20` | `255.255.255.0` | `192.168.20.1` |
| PC5 | `192.168.20.30` | `255.255.255.0` | `192.168.20.1` |

**Configure:** `PC → Desktop → IP Configuration`

---

# 🔍 5. VERIFICATION

| **Command** | **Run On** | **Purpose** |
|---|---|---|
| `show ip interface brief` | Router | Check interface status |
| `show ip route` | Router | Check routing table |
| `show running-config` | Router | Check configuration |
| `ping <IP>` | Router / PC | Test connectivity |
| `tracert <IP>` | PC | Trace packet path |

### 🟢 Interface Check
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

```bash
show ip interface brief
```

Expected:

```text
Status     Protocol
up         up
```

<<<<<<< HEAD
### 🟢 Check Routing Table
=======
### 🟢 Routing Table Check
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

```bash
show ip route
```

<<<<<<< HEAD
Static routes are identified by:
=======
Static routes are marked with:
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

```text
S
```

---

<<<<<<< HEAD
# 📡 9. CONNECTIVITY TEST

### PC0 → PC5

From **PC0 → Desktop → Command Prompt**:
=======
# 📡 6. CONNECTIVITY TEST

### From PC0 → PC5
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

```bash
ping 192.168.20.30
```

Expected path:

```text
<<<<<<< HEAD
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
=======
PC0 → KE-R1 → ENG-R1 → PAK-R1 → INDIA-R1 → PC5
```

### Trace the Path
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec

```bash
tracert 192.168.20.30
```

---

<<<<<<< HEAD
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
=======
# 🧰 7. IMPORTANT COMMANDS

| **Command** | **Function** |
|---|---|
| `enable` | Enter privileged mode |
| `configure terminal` | Enter global configuration mode |
| `interface g0/0` | Select interface |
| `ip address` | Assign IPv4 address |
| `no shutdown` | Enable interface |
| `ip route` | Configure static route |
| `show ip interface brief` | Check interfaces |
| `show ip route` | Check routing table |
| `show running-config` | View configuration |
| `ping` | Test connectivity |
| `tracert` | Trace packet path |
>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec
| `write memory` | Save configuration |

---

<<<<<<< HEAD
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

=======
# 🧠 8. KEY CONCEPTS

| **Concept** | **What We Used** |
|---|---|
| Static Routing | Manual route configuration |
| IPv4 Addressing | Router + PC IP addresses |
| `/24` | LAN networks |
| `/30` | Router-to-router links |
| Next-Hop Routing | `ip route ... next-hop` |
| Default Gateway | PC → Router communication |
| Routing Table | `show ip route` |
| Ping | Connectivity testing |
| Traceroute | Path verification |
| Cisco IOS | Router configuration |

---

# 📌 9. STATIC ROUTING SUMMARY

| **Router** | **Destination Network** | **Next Hop** |
|---|---|---|
| KE-R1 | `192.168.20.0/24` | `10.10.10.2` |
| ENG-R1 | `192.168.10.0/24` | `10.10.10.1` |
| ENG-R1 | `192.168.20.0/24` | `20.20.20.2` |
| PAK-R1 | `192.168.10.0/24` | `20.20.20.1` |
| PAK-R1 | `192.168.20.0/24` | `30.30.30.2` |
| INDIA-R1 | `192.168.10.0/24` | `30.30.30.1` |

---

# 🏁 10. RESULT

> ✅ **Static Routing successfully configured between Kenya LAN and India LAN using Cisco Packet Tracer.**

### Final Connectivity Test

```bash
ping 192.168.20.30
```

```bash
tracert 192.168.20.30
```

>>>>>>> 41b09168f856ede31314ab50d943146e93a0eaec
<p align="center">

### ⭐ LAB 34 — STATIC ROUTING ⭐

**Cisco Packet Tracer • IPv4 • Static Routing • Network Configuration**

</p>
