# Introduction to Networking – Basic Concepts

## 1. What is Networking?
Networking is the practice of connecting devices to share data and resources.  
It enables communication, collaboration, and access to applications and the Internet.

### Key Points:
- A **network** is a group of devices connected to exchange information.
- **End devices**: computers, phones, servers, printers.
- **Intermediate devices**: switches, routers, access points.

---

## 2. Types of Networks
- **LAN (Local Area Network)**: small, local networks (home, office).
- **WAN (Wide Area Network)**: connects multiple LANs over large areas (Internet).
- **MAN (Metropolitan Area Network)**: covers a city or campus.
- **Wireless networks**: Wi-Fi or mobile data networks.

---

## 3. Network Devices
| Device | Function |
|--------|---------|
| **Router** | Connects different networks, directs traffic |
| **Switch** | Connects devices within the same network |
| **Hub** | Sends data to all connected devices (less efficient) |
| **Access Point (AP)** | Provides wireless connectivity |
| **Firewall** | Controls access and protects the network |

---

## 4. Network Models
### 4.1 OSI Model
7 layers that describe how data travels in a network:  

| Layer | Function | Example Protocols |
|-------|---------|-----------------|
| 7 Application | Interface with user | HTTP, FTP |
| 6 Presentation | Data translation, encryption | JPEG, SSL |
| 5 Session | Manages sessions | NetBIOS |
| 4 Transport | Reliable delivery | TCP, UDP |
| 3 Network | Routing and addressing | IP, ICMP |
| 2 Data Link | MAC addressing, error detection | Ethernet, PPP |
| 1 Physical | Cables, signals | Fiber, RJ45 |

### 4.2 TCP/IP Model
4 layers commonly used in real networks:  

| Layer | Function | Example Protocols |
|-------|---------|-----------------|
| Application | User interface and apps | HTTP, FTP, DNS |
| Transport | Reliable/fast delivery | TCP, UDP |
| Internet | IP addressing and routing | IP, ICMP |
| Network Interface | Physical & data link | Ethernet, Wi-Fi |

---

## 5. IP Addressing
- **IPv4**: 32 bits, example: `192.168.1.1`  
- **IPv6**: 128 bits, example: `2001:0db8:85a3::8a2e:0370:7334`  
- IP addresses are used to identify devices and route data correctly.

### Quick IP Cheatsheet (within notes)
| Class | Range | Default Subnet Mask |
|-------|-------|------------------|
| A | 1.0.0.0–126.255.255.255 | 255.0.0.0 |
| B | 128.0.0.0–191.255.255.255 | 255.255.0.0 |
| C | 192.0.0.0–223.255.255.255 | 255.255.255.0 |

---

## 6. Key Networking Concepts
- **Subnetting**: dividing networks into smaller subnetworks.  
- **MAC Address**: unique hardware identifier for each device.  
- **Topology**: arrangement of devices in a network (star, bus, ring).  

### Protocols Quick Reference (within notes)
| Protocol | Port | Purpose |
|----------|------|--------|
| HTTP | 80 | Web traffic |
| HTTPS | 443 | Secure web traffic |
| FTP | 21 | File transfer |
| DNS | 53 | Domain name resolution |
| DHCP | 67/68 | IP address assignment |

---

## 7. Recommended Resources
- [Cisco Networking Academy](https://www.netacad.com) – official course content  
- Packet Tracer – for simulating network labs  
- **Cheatsheets within these notes**:
  - Quick reference for IP addressing  
  - OSI layers overview  
  - Common network protocols
