# TCP/IP Protocol Suite

## Overview
Explore the TCP/IP model, its layers, and comparison with the OSI model.

## What is TCP/IP?
TCP/IP (Transmission Control Protocol/Internet Protocol) is the fundamental communication protocol used on the internet. It's a suite of protocols that work together to enable network communication.

## TCP/IP Model (4 Layers)

### Layer 4 - Application Layer
- **Function:** User applications and services
- **Protocols:** HTTP, HTTPS, FTP, SMTP, DNS, Telnet, SSH, POP3, IMAP
- **Examples:** Web browsers, email clients, file transfer apps
- **Equivalent to OSI Layers:** 5, 6, 7

### Layer 3 - Transport Layer
- **Function:** End-to-end communication and reliability
- **Protocols:** TCP, UDP, SCTP
- **TCP:** Reliable, connection-oriented (slower but accurate)
- **UDP:** Fast, connectionless (faster but less reliable)
- **Equivalent to OSI Layer:** 4

### Layer 2 - Internet Layer
- **Function:** Routing and logical addressing
- **Protocols:** IP (IPv4, IPv6), ICMP, IGMP, IPsec
- **Key Concept:** IP addresses (e.g., 192.168.1.1)
- **Equivalent to OSI Layer:** 3

### Layer 1 - Network Access/Link Layer
- **Function:** Physical transmission and hardware addressing
- **Protocols:** Ethernet, PPP, ARP, SLIP
- **Key Concept:** MAC addresses
- **Equivalent to OSI Layers:** 1, 2

## Key Protocols Explained

### TCP (Transmission Control Protocol)
- Connection-oriented
- Reliable delivery
- Used by: HTTP, HTTPS, FTP, SMTP, SSH, Telnet
- Best for: Accuracy is critical

### UDP (User Datagram Protocol)
- Connectionless
- Fast but unreliable
- Used by: DNS, DHCP, VoIP, Video streaming
- Best for: Speed is critical

### IP (Internet Protocol)
- Routes data across networks
- IPv4: 32-bit address (e.g., 192.168.1.1)
- IPv6: 128-bit address (e.g., 2001:0db8:85a3::8a2e:0370:7334)

### ICMP (Internet Control Message Protocol)
- Used for error reporting
- Used by: ping, traceroute commands

### DNS (Domain Name System)
- Converts domain names to IP addresses
- Example: google.com → 142.250.185.46

### DHCP (Dynamic Host Configuration Protocol)
- Automatically assigns IP addresses
- Used in most networks

## TCP/IP vs OSI Model

| Feature | TCP/IP | OSI |
|---------|--------|-----|
| Layers | 4 | 7 |
| Type | Practical | Theoretical |
| Development | Practical use | Educational |
| Adoption | Industry standard | Reference model |

## How Data Flows Through TCP/IP

1. **Application Layer:** User sends data
2. **Transport Layer:** Data is segmented (TCP/UDP)
3. **Internet Layer:** Segments are packetized (IP)
4. **Network Access Layer:** Packets are framed and transmitted

## Key Concepts
- **Port Numbers:** Identify applications (HTTP: 80, HTTPS: 443, SSH: 22)
- **Socket:** IP address + Port number combination
- **Three-way Handshake:** TCP connection establishment (SYN, SYN-ACK, ACK)

## Resources
- Understand the difference between TCP and UDP
- Learn common port numbers
- Practice identifying which layer protocols belong to
