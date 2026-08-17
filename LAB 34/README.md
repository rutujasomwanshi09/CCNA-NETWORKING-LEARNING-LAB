# 🌐 LAB 34 — STATIC ROUTING CONFIGURATION

### 🚀 Cisco Packet Tracer | IPv4 | Static Routing

---

## 🎯 1. LAB OBJECTIVE

| Item | Details |
|---|---|
| **Routing Type** | Static Routing |
| **Tool** | Cisco Packet Tracer |
| **Routers** | KE-R1, ENG-R1, PAK-R1, INDIA-R1 |
| **Kenya LAN** | `192.168.10.0/24` |
| **India LAN** | `192.168.20.0/24` |
| **Goal** | Establish communication between Kenya LAN and India LAN |

### 🔄 Topology Path

```text
Kenya LAN → KE-R1 → ENG-R1 → PAK-R1 → INDIA-R1 → India LAN
```

---

# 🌐 2. IP ADDRESSING

| Router | Interface | IP Address | Mask | Connection |
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

# 💻 3. PC ADDRESSING

| PC | IP Address | Mask | Gateway |
|---|---|---|---|
| **PC0** | `192.168.10.10` | `255.255.255.0` | `192.168.10.1` |
| **PC1** | `192.168.10.20` | `255.255.255.0` | `192.168.10.1` |
| **PC2** | `192.168.10.30` | `255.255.255.0` | `192.168.10.1` |
| **PC3** | `192.168.20.10` | `255.255.255.0` | `192.168.20.1` |
| **PC4** | `192.168.20.20` | `255.255.255.0` | `192.168.20.1` |
| **PC5** | `192.168.20.30` | `255.255.255.0` | `192.168.20.1` |

> 📌 Packet Tracer: **PC → Desktop → IP Configuration**

---

# ⚙️ 4. ROUTER CONFIGURATION SUMMARY

| Router | Interface Configuration | Static Route Configuration |
|---|---|---|
| **KE-R1** | G0/0 `192.168.10.1`, G0/1 `10.10.10.1` | India LAN via `10.10.10.2` |
| **ENG-R1** | G0/0 `10.10.10.2`, G0/1 `20.20.20.1` | Kenya + India routes |
| **PAK-R1** | G0/0 `20.20.20.2`, G0/1 `30.30.30.1` | Kenya + India routes |
| **INDIA-R1** | G0/0 `30.30.30.2`, G0/1 `192.168.20.1` | Kenya LAN via `30.30.30.1` |

> 💡 **All exact commands are in [`commands.md`](commands.md).**

---

# 🧠 5. STATIC ROUTING TABLE

| Router | Destination Network | Next Hop | Purpose |
|---|---|---|---|
| **KE-R1** | `192.168.20.0/24` | `10.10.10.2` | Reach India LAN |
| **ENG-R1** | `192.168.10.0/24` | `10.10.10.1` | Reach Kenya LAN |
| **ENG-R1** | `192.168.20.0/24` | `20.20.20.2` | Reach India LAN |
| **PAK-R1** | `192.168.10.0/24` | `20.20.20.1` | Reach Kenya LAN |
| **PAK-R1** | `192.168.20.0/24` | `30.30.30.2` | Reach India LAN |
| **INDIA-R1** | `192.168.10.0/24` | `30.30.30.1` | Reach Kenya LAN |

---

# 🔍 6. VERIFICATION

| Command | Run On | Purpose |
|---|---|---|
| `show ip interface brief` | All routers | Check interfaces |
| `show ip route` | All routers | Check routing table |
| `show running-config` | All routers | Check configuration |
| `ping <IP>` | Router / PC | Test connectivity |
| `tracert <IP>` | PC | Trace packet path |

### Final Test

```text
PC0 → ping 192.168.20.30
PC0 → tracert 192.168.20.30
```

Expected path:

```text
PC0 → KE-R1 → ENG-R1 → PAK-R1 → INDIA-R1 → PC5
```

---

# 📚 7. KEY CONCEPTS

| Concept | Practiced |
|---|---|
| IPv4 Addressing | ✅ |
| `/24` LAN Networks | ✅ |
| `/30` Router Links | ✅ |
| Interface Configuration | ✅ |
| Static Routing | ✅ |
| Next-Hop Routing | ✅ |
| Default Gateway | ✅ |
| Routing Table | ✅ |
| Ping / Traceroute | ✅ |
| Cisco IOS | ✅ |

---

# 🏁 8. RESULT

> ✅ **Static Routing successfully configured between Kenya LAN and India LAN using Cisco Packet Tracer.**

### 📂 Lab Files

| File | Purpose |
|---|---|
| `README.md` | Lab explanation and tables |
| `commands.md` | Complete commands + purpose |
| `.pkt` | Packet Tracer topology |

