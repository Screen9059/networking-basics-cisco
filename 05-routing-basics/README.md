# Routing Basics

## Overview
Introduction to routing concepts, protocols (RIP, OSPF, EIGRP), and configuring routes on Cisco devices.

## What is Routing?
Routing is the process of directing data packets from a source network to a destination network across multiple networks (internetworks). Routers use routing tables to determine the best path for data.

## Key Routing Concepts

### Routing Table
- **Definition:** A database of known networks and how to reach them
- **Contains:** Network destinations, next-hop addresses, metrics
- **Located on:** Routers and end devices
- **Purpose:** Guides packets to their destination

### Best Path Selection
Routers use metrics to determine the best path:
- **Metric:** A value assigned to routes (hop count, bandwidth, delay, etc.)
- **Lower metric** = Better/preferred route
- **Multiple metrics:** Different routing protocols use different criteria

### Static vs Dynamic Routing

| Feature | Static Routing | Dynamic Routing |
|---------|----------------|-----------------|
| Configuration | Manual | Automatic |
| Updates | Manual updates needed | Automatic updates |
| Overhead | Low | Higher |
| Scalability | Small networks | Large networks |
| Example | Default routes | RIP, OSPF, EIGRP |

## Routing Protocols

### RIP (Routing Information Protocol)

**Type:** Distance-vector protocol

**Characteristics:**
- Uses hop count as metric (max 15 hops)
- Sends entire routing table every 30 seconds
- Slower convergence time
- Simple but inefficient

**Versions:**
- **RIPv1:** Classful (old)
- **RIPv2:** Classless (better)

**Best for:** Small networks only

**Cisco RIPv2 Configuration Example:**
```
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 10.0.0.0
Router(config-router)# exit
```

### OSPF (Open Shortest Path First)

**Type:** Link-state protocol

**Characteristics:**
- Uses cost as metric (based on bandwidth)
- Sends updates only when changes occur
- Fast convergence time
- More complex but efficient
- Divides network into areas for scalability

**Advantages:**
- Faster convergence
- Lower bandwidth usage
- More scalable
- Industry standard

**Cisco OSPF Configuration Example:**
```
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router(config-router)# network 10.0.0.0 0.255.255.255 area 0
Router(config-router)# exit
```

### EIGRP (Enhanced Interior Gateway Routing Protocol)

**Type:** Hybrid protocol (distance-vector + link-state features)

**Characteristics:**
- Uses composite metric (bandwidth, delay, reliability, load)
- Fast convergence
- Low bandwidth usage
- Cisco proprietary (but now open standard)
- Very efficient

**Advantages:**
- Faster than OSPF in some scenarios
- Better for Cisco networks
- DUAL algorithm ensures loop-free routing

**Cisco EIGRP Configuration Example:**
```
Router(config)# router eigrp 100
Router(config-router)# network 192.168.1.0 0.0.0.255
Router(config-router)# network 10.0.0.0 0.255.255.255
Router(config-router)# no auto-summary
Router(config-router)# exit
```

## Routing Protocol Comparison

| Feature | RIP | OSPF | EIGRP |
|---------|-----|------|-------|
| Type | Distance-vector | Link-state | Hybrid |
| Metric | Hop count | Cost (bandwidth) | Composite |
| Max hops | 15 | Unlimited | Unlimited |
| Convergence | Slow | Fast | Very fast |
| Bandwidth | High | Low | Very low |
| Complexity | Simple | Complex | Moderate |
| Scalability | Small | Large | Large |
| Cisco only | No | No | Yes (originally) |

## Static Routing on Cisco Devices

### Default Route
**Purpose:** Route for packets with unknown destinations

**Configuration:**
```
Router(config)# ip route 0.0.0.0 0.0.0.0 192.168.1.1
```

### Specific Static Route
**Purpose:** Route for a specific network

**Configuration:**
```
Router(config)# ip route 10.0.0.0 255.255.255.0 192.168.1.1
```

**Breakdown:**
- `10.0.0.0` = Destination network
- `255.255.255.0` = Subnet mask
- `192.168.1.1` = Next-hop IP address (router's interface)

## Viewing Routing Information on Cisco

### Show Routing Table
```
Router# show ip route
```

### Show Routing Protocol Status
```
Router# show ip ospf
Router# show ip eigrp neighbors
Router# show ip rip database
```

### Show IP Interfaces
```
Router# show ip interface brief
```

## Routing Metrics Explained

### Hop Count (RIP)
- Number of routers between source and destination
- Simpler but less accurate

### Cost (OSPF)
- Based on bandwidth of the link
- Formula: 100,000,000 / bandwidth (in bps)
- Example: 10 Mbps link = 10,000 cost

### Composite Metric (EIGRP)
- Combines multiple factors
- Default: 20% bandwidth + 20% delay
- Can be adjusted with K values

## Key Concepts

### Convergence
- Time taken by all routers to agree on network changes
- Faster convergence = Better for network stability

### Loop Prevention
- **RIP:** TTL (Time To Live) field
- **OSPF:** SPF algorithm
- **EIGRP:** DUAL algorithm

### Administrative Distance (AD)
- Trustworthiness rating of routing source (0-255)
- Lower = More trusted
- Examples:
  - Connected interface: 0
  - Static route: 1
  - EIGRP: 90
  - OSPF: 110
  - RIP: 120

## Cisco Router Configuration Tips

### Basic Router Setup
```
Router(config)# hostname Router1
Router(config)# interface gigabitethernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
```

### Enable Routing Protocol
```
Router(config)# router ospf 1
Router(config-router)# network 0.0.0.0 255.255.255.255 area 0
```

## Practice Scenarios

1. **Configure static routing** between two routers
2. **Set up OSPF** in a multi-area network
3. **Compare metrics** between different protocols
4. **Troubleshoot routing issues** using show commands

## Resources
- Understand when to use each routing protocol
- Practice Cisco router configurations
- Use routing simulators to test configurations
- Study real-world routing scenarios
