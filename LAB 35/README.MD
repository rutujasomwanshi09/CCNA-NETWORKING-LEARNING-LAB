# 🛰️ LAB 35 — Floating Static Routing Using Cisco Packet Tracer

> **Objective:** Configure **Floating Static Routing** with a primary path and a backup path between Kenya LAN and India LAN.

## 🌐 Topology

**Primary:** `Kenya LAN → KE-R1 → ENG-R1 → PAK-R1 → INDIA-R1 → India LAN`

**Backup:** `Kenya LAN → KE-R1 → AUS-R1 → INDIA-R1 → India LAN`

## 📍 IP Addressing

| Device | Interface | IP Address | Network |
|---|---|---|---|
| KE-R1 | G0/0 | 192.168.10.1/24 | Kenya LAN |
| KE-R1 | G0/1 | 10.10.10.1/30 | KE ↔ ENG |
| KE-R1 | G0/2 | 40.40.40.1/30 | KE ↔ AUS |
| ENG-R1 | G0/0 | 10.10.10.2/30 | KE ↔ ENG |
| ENG-R1 | G0/1 | 20.20.20.1/30 | ENG ↔ PAK |
| PAK-R1 | G0/0 | 20.20.20.2/30 | ENG ↔ PAK |
| PAK-R1 | G0/1 | 30.30.30.1/30 | PAK ↔ INDIA |
| INDIA-R1 | G0/0 | 30.30.30.2/30 | PAK ↔ INDIA |
| INDIA-R1 | G0/1 | 192.168.20.1/24 | India LAN |
| AUS-R1 | G0/0 | 40.40.40.2/30 | KE ↔ AUS |
| AUS-R1 | G0/1 | 50.50.50.1/30 | AUS ↔ INDIA |
| INDIA-R1 | G0/2 | 50.50.50.2/30 | AUS ↔ INDIA |

## 🔐 Floating Static Routing

Primary routes use the normal path. Backup routes are configured with **Administrative Distance 130**, making them less preferred than the primary routes.

| Router | Destination | Route | AD |
|---|---|---|---|
| KE-R1 | 192.168.20.0/24 | G0/1 | 1 |
| ENG-R1 | 192.168.20.0/24 | G0/1 | 1 |
| PAK-R1 | 192.168.20.0/24 | G0/1 | 1 |
| INDIA-R1 | 192.168.10.0/24 | 30.30.30.1 | 1 |
| KE-R1 | 192.168.20.0/24 | 40.40.40.2 | 130 |
| AUS-R1 | 192.168.20.0/24 | 50.50.50.2 | 1 |
| INDIA-R1 | 192.168.10.0/24 | 50.50.50.1 | 130 |
| AUS-R1 | 192.168.10.0/24 | 40.40.40.1 | 1 |

## ⚙️ What Was Configured?

| Router | Configuration |
|---|---|
| **KE-R1** | Kenya LAN, ENG link, AUS link, primary route and floating backup route |
| **ENG-R1** | KE link, PAK link and route toward India LAN |
| **PAK-R1** | ENG link, INDIA link and route toward India LAN |
| **AUS-R1** | KE link, INDIA link and backup-path routes |
| **INDIA-R1** | India LAN, PAK link, AUS link, primary and floating route toward Kenya LAN |

## 🧪 Verification

```text
show ip interface brief
show ip route
show running-config
ping 192.168.20.30
traceroute 192.168.20.30
```

To test the backup path, shut down the primary link and verify that traffic moves through `AUS-R1`.

## 📂 Files

- `README.md` — Lab documentation
- `commands.txt` — Router configuration commands
- `.pkt` — Cisco Packet Tracer topology

## ✅ Result

Floating Static Routing was configured with a primary route and a backup route using **AD 130**. The backup path is used when the primary route becomes unavailable.
