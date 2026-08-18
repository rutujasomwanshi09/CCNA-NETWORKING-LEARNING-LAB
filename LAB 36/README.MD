# 🌐 LAB 36 — DEFAULT STATIC ROUTING WITH BACKUP ROUTE

<p align="center">

### 🚀 Default Static Routing + Floating Static Route

**Cisco Packet Tracer | Static Routing | Default Route | Backup Route**

</p>

---

## 🎯 Objective

IN THIS LAB **Default Static Routing** AND **Floating Static
Backup Route** HAVE ALREADY CONFIGURED.

### Main Concepts

- Default Static Route
- Floating Static Route
- Administrative Distance
- Primary & Backup Path
- Return Static Route
- Route Failover

---

## 🖥️ Topology

```text
                 ISP-1
              200.100.50.2
                  |
                  |
                  R1
                /    \
               /      \
          ISP-1       ISP-2
                      200.100.50.6
                  |
               LAN
           192.168.1.0/24
             /       \
           PC2       PC3

🌐 IP Addressing
| Device | Network / IP   | Purpose          |
| ------ | -------------- | ---------------- |
| R1     | 192.168.1.1/24 | LAN Gateway      |
| R1     | 200.100.50.1   | Primary ISP      |
| R1     | 200.100.50.5   | Backup ISP       |
| ISP-1  | 200.100.50.2   | Primary Next-Hop |
| ISP-2  | 200.100.50.6   | Backup Next-Hop  |
| PC2    | 192.168.1.10   | LAN Host         |
| PC3    | 192.168.1.20   | LAN Host         |
