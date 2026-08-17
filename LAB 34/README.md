LAB 34 - Static Routing Configuration Using Cisco Packet Tracer

📌 Objective

Configure Static Routing between two LAN networks:

🇰🇪 Kenya LAN → 192.168.10.0/24

🇮🇳 India LAN → 192.168.20.0/24

Traffic path:

Kenya LAN
   ↓
KE-R1
   ↓
ENG-R1
   ↓
PAK-R1
   ↓
INDIA-R1
   ↓
India LAN

🌐 IP Addressing

Device

Interface

IP Address

KE-R1

G0/0

192.168.10.1/24

KE-R1

G0/1

10.10.10.1/30

ENG-R1

G0/0

10.10.10.2/30

ENG-R1

G0/1

20.20.20.1/30

PAK-R1

G0/0

20.20.20.2/30

PAK-R1

G0/1

30.30.30.1/30

INDIA-R1

G0/0

30.30.30.2/30

INDIA-R1

G0/1

192.168.20.1/24

⚙️ Router Configuration

1. KE-R1 Configuration

What we configured:

G0/0 → Kenya LAN IP

G0/1 → Link to ENG-R1

Static route → India LAN

Commands:

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

Static Route Meaning:

192.168.20.0/24
        ↓
Next Hop: 10.10.10.2

KE-R1 ko bataya ki India LAN tak packets ENG-R1 ke through bhejne hain.

2. ENG-R1 Configuration

What we configured:

G0/0 → KE-R1 connection

G0/1 → PAK-R1 connection

Route → Kenya LAN

Route → India LAN

Commands:

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

Static Routes:

192.168.10.0/24 → 10.10.10.1
192.168.20.0/24 → 20.20.20.2

ENG-R1 ko dono LAN networks ka path pata hai.

3. PAK-R1 Configuration

What we configured:

G0/0 → ENG-R1 connection

G0/1 → INDIA-R1 connection

Route → Kenya LAN

Route → India LAN

Commands:

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

Static Routes:

192.168.10.0/24 → 20.20.20.1
192.168.20.0/24 → 30.30.30.2

PAK-R1 ko Kenya aur India dono LANs ka route diya gaya hai.

4. INDIA-R1 Configuration

What we configured:

G0/0 → PAK-R1 connection

G0/1 → India LAN

Static route → Kenya LAN

Commands:

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

Static Route Meaning:

192.168.10.0/24
        ↓
Next Hop: 30.30.30.1

INDIA-R1 ko bataya ki Kenya LAN tak packets PAK-R1 ke through bhejne hain.

💻 PC Configuration

🇰🇪 Kenya PCs

PC

IP Address

Gateway

PC0

192.168.10.10

192.168.10.1

PC1

192.168.10.20

192.168.10.1

PC2

192.168.10.30

192.168.10.1

Subnet Mask:

255.255.255.0

Configure from:

PC → Desktop → IP Configuration

🇮🇳 India PCs

PC

IP Address

Gateway

PC3

192.168.20.10

192.168.20.1

PC4

192.168.20.20

192.168.20.1

PC5

192.168.20.30

192.168.20.1

Subnet Mask:

255.255.255.0

Configure from:

PC → Desktop → IP Configuration

🔍 Verification

Check Interfaces

Run on every router:

show ip interface brief

Interfaces should show:

Status     Protocol
up         up

Check Routing Table

show ip route

Static routes are shown with:

S

Example:

S 192.168.20.0/24 via 10.10.10.2

Test Router Connectivity

ping 10.10.10.2
ping 20.20.20.2
ping 30.30.30.2

End-to-End Test

From PC0:

ping 192.168.20.30

Expected:

PC0 → KE-R1 → ENG-R1 → PAK-R1 → INDIA-R1 → PC5

Trace the Path

From PC0:

tracert 192.168.20.30

This shows the routers through which the packet travels.

🧠 Important Commands

Command

Purpose

enable

Privileged mode

configure terminal

Configuration mode

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

🧠 Key Concepts

Static Routing

IPv4 Addressing

/24 LAN Networks

/30 Point-to-Point Networks

Next-Hop Routing

Default Gateway

Routing Table

Ping

Traceroute

Cisco IOS CLI

✅ Result

Static routing was configured successfully between the Kenya LAN (192.168.10.0/24) and India LAN (192.168.20.0/24) through ENG-R1 and PAK-R1.

Connectivity can be verified using:

ping 192.168.20.30

and:

tracert 192.168.20.30