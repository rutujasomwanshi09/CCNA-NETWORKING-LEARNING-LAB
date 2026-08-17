# 🌐 LAB 34 — STATIC ROUTING CONFIGURATION

<p align="center">

### 🚀 Cisco Packet Tracer | IPv4 | Static Routing

</p>

---

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

### 🧠 Static Routes

| **Destination Network** | **Next Hop** | **Purpose** |
|---|---|---|
| `192.168.10.0/24` | `10.10.10.1` | Kenya LAN via KE-R1 |
| `192.168.20.0/24` | `20.20.20.2` | India LAN via PAK-R1 |

---

## 🇵🇰 PAK-R1

### What was configured?

| **Configuration** | **Details** |
|---|---|
| G0/0 | Connection to ENG-R1 |
| G0/1 | Connection to INDIA-R1 |
| Static Route 1 | Route to Kenya LAN |
| Static Route 2 | Route to India LAN |

### 💻 Commands

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

### 🧠 Static Routes

| **Destination Network** | **Next Hop** | **Purpose** |
|---|---|---|
| `192.168.10.0/24` | `20.20.20.1` | Kenya LAN via ENG-R1 |
| `192.168.20.0/24` | `30.30.30.2` | India LAN via INDIA-R1 |

---

## 🇮🇳 INDIA-R1

### What was configured?

| **Configuration** | **Details** |
|---|---|
| G0/0 | Connection to PAK-R1 |
| G0/1 | India LAN |
| Static Route | Route to Kenya LAN |

### 💻 Commands

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

### 🧠 Static Route

| **Destination Network** | **Next Hop** | **Purpose** |
|---|---|---|
| `192.168.10.0/24` | `30.30.30.1` | Kenya LAN via PAK-R1 |

---

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

```bash
show ip interface brief
```

Expected:

```text
Status     Protocol
up         up
```

### 🟢 Routing Table Check

```bash
show ip route
```

Static routes are marked with:

```text
S
```

---

# 📡 6. CONNECTIVITY TEST

### From PC0 → PC5

```bash
ping 192.168.20.30
```

Expected path:

```text
PC0 → KE-R1 → ENG-R1 → PAK-R1 → INDIA-R1 → PC5
```

### Trace the Path

```bash
tracert 192.168.20.30
```

---

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
| `write memory` | Save configuration |

---

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

<p align="center">

### ⭐ LAB 34 — STATIC ROUTING ⭐

**Cisco Packet Tracer • IPv4 • Static Routing • Network Configuration**

</p>
