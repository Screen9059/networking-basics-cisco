# OSI Model

## Overview
Detailed explanation of the OSI Model and its 7 layers.

## What is the OSI Model?
The OSI (Open Systems Interconnection) model is a conceptual framework used to describe how network communication occurs. It divides the communication process into 7 layers.

## The 7 Layers of the OSI Model

### Layer 7 - Application Layer
- **Function:** User applications and services
- **Examples:** HTTP, HTTPS, FTP, SMTP, DNS, Telnet
- **Devices:** Computers, servers

### Layer 6 - Presentation Layer
- **Function:** Data encryption, compression, translation
- **Examples:** SSL/TLS, JPEG, MPEG
- **Devices:** Gateways, firewalls

### Layer 5 - Session Layer
- **Function:** Manages sessions/connections between applications
- **Examples:** NetBIOS, RPC, SSH
- **Devices:** Computers, servers

### Layer 4 - Transport Layer
- **Function:** End-to-end communication and data flow
- **Examples:** TCP, UDP, SCTP
- **Devices:** Firewalls, load balancers

### Layer 3 - Network Layer
- **Function:** Routing and logical addressing (IP addresses)
- **Examples:** IP, ICMP, IGMP, IPsec
- **Devices:** Routers, layer 3 switches

### Layer 2 - Data Link Layer
- **Function:** Physical addressing (MAC addresses) and frame switching
- **Examples:** Ethernet, PPP, Frame Relay
- **Devices:** Switches, network bridges

### Layer 1 - Physical Layer
- **Function:** Physical transmission of data
- **Examples:** Copper cables, fiber optics, radio waves
- **Devices:** Cables, hubs, repeaters

## Key Concepts
- **PDU (Protocol Data Unit):** Each layer has its own PDU
  - Layer 7-5: Data
  - Layer 4: Segment
  - Layer 3: Packet
  - Layer 2: Frame
  - Layer 1: Bits

## OSI Model vs TCP/IP Model
- OSI has 7 layers, TCP/IP has 4 layers
- OSI is theoretical, TCP/IP is practical

## Resources
- Study the layers from bottom-up and top-down
- Practice identifying which layer different protocols belong to
