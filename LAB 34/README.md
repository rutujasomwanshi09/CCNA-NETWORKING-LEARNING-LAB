🌐 LAB 34 — Static Routing Configuration

<p align="center">
  <b>🚀 Cisco Packet Tracer | Static Routing | IPv4 Networking</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Cisco-Packet%20Tracer-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white">
  <img src="https://img.shields.io/badge/Networking-Static%20Routing-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/IPv4-Configured-green?style=for-the-badge">
</p>

🎯 Objective

Configure Static Routing between two LAN networks using four Cisco routers.

🌍 Network

📡 Network Address

🇰🇪 Kenya LAN

192.168.10.0/24

🇮🇳 India LAN

192.168.20.0/24

🔄 Packet Path

🇰🇪 Kenya LAN
      │
      ▼
   KE-R1
      │ 10.10.10.0/30
      ▼
   ENG-R1
      │ 20.20.20.0/30
      ▼
   PAK-R1
      │ 30.30.30.0/30
      ▼
  INDIA-R1
      │
      ▼
🇮🇳 India LAN

🌐 1. IP Addressing

🖥️ Router Interfaces

Router

Interface

IP Address

Network

KE-R1

G0/0

192.168.10.1/24

Kenya LAN

KE-R1

G0/1

10.10.10.1/30

KE ↔ ENG

ENG-R1

G0/0

10.10.10.2/30

KE ↔ ENG

ENG-R1

G0/1

20.20.20.1/30

ENG ↔ PAK

PAK-R1

G0/0

20.20.20.2/30

ENG ↔ PAK

PAK-R1

G0/1

30.30.30.1/30

PAK ↔ INDIA

INDIA-R1

G0/0

30.30.30.2/30

PAK ↔ INDIA

INDIA-R1

G0/1

192.168.20.1/24

India LAN

⚙️ 2. Router Configuration

🇰🇪 KE-R1

🔧 Configuration

G0/0 → Kenya LAN

G0/1 → ENG-R1 connection

Static route → India LAN

💻 Commands

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

🧠 Static Route

Destination : 192.168.20.0/24
Next Hop    : 10.10.10.2

➡️ Meaning: India LAN tak packet ENG-R1 ke through bhejna hai.

🇬🇧 ENG-R1

🔧 Configuration

G0/0 → KE-R1 connection

G0/1 → PAK-R1 connection

Route → Kenya LAN

Route → India LAN

💻 Commands

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

🧠 Routes

192.168.10.0/24 → 10.10.10.1
192.168.20.0/24 → 20.20.20.2

➡️ Meaning: ENG-R1 ko dono LAN networks ka path pata hai.

🇵🇰 PAK-R1

🔧 Configuration

G0/0 → ENG-R1 connection

G0/1 → INDIA-R1 connection

Route → Kenya LAN

Route → India LAN

💻 Commands

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

🧠 Routes

192.168.10.0/24 → 20.20.20.1
192.168.20.0/24 → 30.30.30.2

➡️ Meaning: PAK-R1 ko Kenya aur India dono LANs ka route diya gaya hai.

🇮🇳 INDIA-R1

🔧 Configuration

G0/0 → PAK-R1 connection

G0/1 → India LAN

Static route → Kenya LAN

💻 Commands

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

🧠 Static Route

Destination : 192.168.10.0/24
Next Hop    : 30.30.30.1

➡️ Meaning: Kenya LAN tak packet PAK-R1 ke through bhejna hai.

💻 3. PC Configuration

🇰🇪 Kenya LAN

PC

IP Address

Subnet Mask

Default Gateway

PC0

192.168.10.10

255.255.255.0

192.168.10.1

PC1

192.168.10.20

255.255.255.0

192.168.10.1

PC2

192.168.10.30

255.255.255.0

192.168.10.1

Packet Tracer: PC → Desktop → IP Configuration

🇮🇳 India LAN

PC

IP Address

Subnet Mask

Default Gateway

PC3

192.168.20.10

255.255.255.0

192.168.20.1

PC4

192.168.20.20

255.255.255.0

192.168.20.1

PC5

192.168.20.30

255.255.255.0

192.168.20.1

Packet Tracer: PC → Desktop → IP Configuration

🔍 4. Verification

🟢 Check Interface Status

Run on every router:

show ip interface brief

Expected:

Status    Protocol
up        up

🟢 Check Routing Table

show ip route

Static routes appear with:

S

Example:

S 192.168.20.0/24 [1/0] via 10.10.10.2

🟢 Test Connectivity

From PC0:

ping 192.168.20.30

Expected path:

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

🟢 Trace the Packet Path

From PC0:

tracert 192.168.20.30

This verifies the routers through which the packet travels.

🧰 5. Important Commands

Command

Purpose

enable

Enter privileged mode

configure terminal

Enter configuration mode

interface g0/0

Select interface

ip address

Assign IP address

no shutdown

Enable interface

ip route

Configure static route

show ip interface brief

Check interfaces

show ip route

Check routing table

ping

Test connectivity

tracert

Trace packet path

write memory

Save configuration

🧠 6. Key Concepts

Static Routing • IPv4 • Subnetting • /24 LAN • /30 Point-to-Point • Next-Hop Routing • Default Gateway • Routing Table • Ping • Traceroute • Cisco IOS

📌 7. Static Routing Summary

KE-R1
192.168.20.0/24 → 10.10.10.2

ENG-R1
192.168.10.0/24 → 10.10.10.1
192.168.20.0/24 → 20.20.20.2

PAK-R1
192.168.10.0/24 → 20.20.20.1
192.168.20.0/24 → 30.30.30.2

INDIA-R1
192.168.10.0/24 → 30.30.30.1

✅ Result

Static Routing successfully configured between Kenya LAN and India LAN using Cisco Packet Tracer.

End-to-end connectivity verified using:

ping 192.168.20.30

and:

tracert 192.168.20.30