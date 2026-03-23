# IP Addressing & Subnetting

## Overview
Learn about IPv4, IPv6, subnetting concepts, and calculations.

## What is an IP Address?
An IP address is a unique identifier assigned to each device on a network. It allows devices to communicate with each other across networks.

## IPv4 Addressing

### IPv4 Format
- **Structure:** Four octets (numbers) separated by dots
- **Example:** 192.168.1.100
- **Range:** 0.0.0.0 to 255.255.255.255
- **Total Addresses:** 4.3 billion

### IPv4 Address Classes

| Class | Range | Purpose | Subnet Mask |
|-------|-------|---------|------------|
| A | 1.0.0.0 - 126.255.255.255 | Large networks | 255.0.0.0 |
| B | 128.0.0.0 - 191.255.255.255 | Medium networks | 255.255.0.0 |
| C | 192.0.0.0 - 223.255.255.255 | Small networks | 255.255.255.0 |
| D | 224.0.0.0 - 239.255.255.255 | Multicast | N/A |
| E | 240.0.0.0 - 255.255.255.255 | Reserved | N/A |

### Private IP Addresses (RFC 1918)
- **Class A:** 10.0.0.0 to 10.255.255.255
- **Class B:** 172.16.0.0 to 172.31.255.255
- **Class C:** 192.168.0.0 to 192.168.255.255

## Subnetting Basics

### What is Subnetting?
Dividing a large network into smaller, manageable networks (subnets).

### Subnet Mask
- **Purpose:** Identifies which part of IP address is the network and which is the host
- **Example:** 255.255.255.0
- **Binary:** 11111111.11111111.11111111.00000000

### CIDR Notation
- **Meaning:** Classless Inter-Domain Routing
- **Format:** IP/Prefix length
- **Example:** 192.168.1.0/24 (24 bits for network, 8 bits for host)

### Subnetting Calculation Example

**Given:** 192.168.1.0/24 (Class C network)

**Calculate:**
- **Network Address:** 192.168.1.0
- **Broadcast Address:** 192.168.1.255
- **First Host Address:** 192.168.1.1
- **Last Host Address:** 192.168.1.254
- **Total Usable Hosts:** 254

### Common Subnet Masks

| CIDR | Subnet Mask | Hosts | Use |
|------|------------|-------|-----|
| /24 | 255.255.255.0 | 254 | Small networks |
| /25 | 255.255.255.128 | 126 | Smaller networks |
| /26 | 255.255.255.192 | 62 | Very small networks |
| /30 | 255.255.255.252 | 2 | Point-to-point links |

### Subnetting Steps

1. **Determine required subnets** (how many you need)
2. **Calculate bits needed** for subnets
3. **Determine new subnet mask**
4. **Calculate subnet addresses**
5. **Identify host ranges** for each subnet
6. **Assign addresses** to devices

## IPv6 Addressing

### IPv6 Format
- **Structure:** Eight groups of 4 hexadecimal digits separated by colons
- **Example:** 2001:0db8:85a3:0000:0000:8a2e:0370:7334
- **Shortened:** 2001:db8:85a3::8a2e:370:7334
- **Total Addresses:** 340 undecillion (practically unlimited)

### Why IPv6?
- **IPv4 exhaustion:** Running out of IPv4 addresses
- **Larger address space:** 128-bit vs 32-bit
- **Better features:** Built-in security, auto-configuration
- **No NAT needed:** Every device can have a public address

### IPv6 Address Types
- **Unicast:** One-to-one communication
- **Multicast:** One-to-many communication
- **Anycast:** One-to-nearest communication

### IPv6 Prefix Length
- Uses slash notation like IPv4 (e.g., /64)
- /64 is standard for local networks

## Special IP Addresses

### IPv4 Special Addresses
- **127.0.0.1:** Loopback (localhost)
- **0.0.0.0:** Default route
- **255.255.255.255:** Broadcast
- **169.254.x.x:** Link-local (APIPA)

### IPv6 Special Addresses
- **::1:** Loopback
- **:::** Default route
- **fe80::** Link-local prefix

## Subnetting Practice

### Example Problem
Network: 172.16.0.0/16
Need: 4 subnets

**Solution:**
- Add 2 bits for subnets (2² = 4)
- New mask: /18 (16 + 2)
- Subnet addresses:
  - 172.16.0.0/18 (0-63)
  - 172.16.64.0/18 (64-127)
  - 172.16.128.0/18 (128-191)
  - 172.16.192.0/18 (192-255)

## Key Concepts to Remember
- Network address: First address in a subnet
- Broadcast address: Last address in a subnet
- Usable hosts: Network address + 1 to Broadcast address - 1
- All zeros in host portion = Network address
- All ones in host portion = Broadcast address

## Resources
- Use subnet calculators to verify your work
- Practice subnetting until it becomes second nature
- Understand the difference between classful and classless addressing
