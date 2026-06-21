# README.md

## Project Title

**Email Server & FTP Server Configuration using Cisco Packet Tracer**

## Project Description

This project demonstrates the configuration of a dedicated Data Center LAN containing DHCP, DNS, Web, Email, and FTP servers connected to an Office LAN. The objective is to provide centralized network services for clients in the organization.

The topology includes:

* Office LAN Network: `192.168.10.0/24`
* Router Gateway: `192.168.10.1`
* DHCP Server: `192.168.10.5`
* DNS Server: `192.168.10.6`
* Web Server: `192.168.10.7`
* Email Server: `192.168.10.8`
* FTP Server: `192.168.10.9`
* Client PCs: `192.168.10.2 - 192.168.10.11`

---

## Network Topology

### Office LAN

| Device  | IP Address    |
| ------- | ------------- |
| Router0 | 192.168.10.1  |
| PC0     | 192.168.10.2  |
| PC1     | 192.168.10.3  |
| PC2     | 192.168.10.4  |
| PC3     | 192.168.10.10 |
| PC4     | 192.168.10.11 |

### Data Center LAN

| Server       | IP Address   |
| ------------ | ------------ |
| DHCP Server  | 192.168.10.5 |
| DNS Server   | 192.168.10.6 |
| Web Server   | 192.168.10.7 |
| Email Server | 192.168.10.8 |
| FTP Server   | 192.168.10.9 |

---

## Services Configured

### DHCP Service

* Automatically assigns IP addresses to clients.
* Provides subnet mask, default gateway, and DNS information.

### DNS Service

* Resolves domain names to IP addresses.
* Example:

  * gtech.com → 192.168.10.7
  * mail.gtech.com → 192.168.10.8
  * ftp.gtech.com → 192.168.10.9

### Web Service

* Hosts the company website.
* Accessible through browser using domain name.

### Email Service

* Provides email communication.
* SMTP and POP3 services enabled.

### FTP Service

* Provides centralized file storage and transfer.
* Supports authenticated user access.

---

## Verification Steps

### DHCP Verification

```bash
ipconfig /renew
ipconfig
```

### DNS Verification

```bash
ping gtech.com
nslookup gtech.com
```

### Web Server Verification

```bash
Open Browser
http://gtech.com
```

### Email Verification

```bash
Desktop > Email
Send Mail
Receive Mail
```

### FTP Verification

```bash
ftp 192.168.10.9
```

---

## Learning Outcomes

* DHCP Server Configuration
* DNS Server Configuration
* Web Hosting Configuration
* Email Server Deployment
* FTP Server Deployment
* Client Connectivity Testing
* Enterprise Network Service Management

---

# COMMANDS.md

## Router Configuration

```cisco
enable
configure terminal

hostname Router0

interface gigabitEthernet0/0
ip address 192.168.10.1 255.255.255.0
no shutdown

exit

copy running-config startup-config
```

---

## DHCP Server Configuration

### Services → DHCP

```text
DHCP Service : ON

Pool Name : OFFICE

Default Gateway : 192.168.10.1

DNS Server : 192.168.10.6

Start IP Address : 192.168.10.100

Subnet Mask : 255.255.255.0

Maximum Users : 100

Add
```

---

## DNS Server Configuration

### Services → DNS

```text
DNS Service : ON

A Records

gtech.com            192.168.10.7
mail.gtech.com       192.168.10.8
ftp.gtech.com        192.168.10.9
```

---

## Web Server Configuration

### Services → HTTP

```text
HTTP Service : ON
HTTPS Service : ON
```

### Sample Web Page

```html
<h1>Welcome to GTECH.COM</h1>
<p>Web Server Successfully Configured</p>
```

---

## Email Server Configuration

### Services → EMAIL

```text
SMTP : ON
POP3 : ON

Domain Name : gtech.com

Users

ADMIN1
Password: ADMIN1

ADMIN2
Password: ADMIN2

ADMIN3
Password: ADMIN3
```

---

## FTP Server Configuration

### Services → FTP

```text
FTP Service : ON

Username : ADMIN1
Password : ADMIN1

Username : ADMIN2
Password : ADMIN2

Username : ADMIN3
Password : ADMIN3
```

---

## PC Configuration

### Desktop → IP Configuration

```text
DHCP
```

OR

```text
IP Address : 192.168.10.x
Subnet Mask : 255.255.255.0
Default Gateway : 192.168.10.1
DNS Server : 192.168.10.6
```

---

## Connectivity Testing Commands

### Ping Test

```bash
ping 192.168.10.1
ping 192.168.10.7
ping 192.168.10.8
ping 192.168.10.9
```

### DNS Test

```bash
ping gtech.com
```

### FTP Test

```bash
ftp 192.168.10.9
```

### Email Test

```text
Compose Mail
Send Mail
Receive Mail
```

### Web Test

```text
Browser → http://gtech.com
```


