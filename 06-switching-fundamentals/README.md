# Switching Fundamentals

## Overview
Fundamentals of network switches, VLANs, and Cisco switching basics.

## What is a Network Switch?
A network switch is a device that connects multiple devices on a local area network (LAN) and forwards data frames between them based on MAC addresses. It operates at Layer 2 (Data Link Layer) of the OSI model.

## Switch vs Hub vs Router

| Feature | Hub | Switch | Router |
|---------|-----|--------|--------|
| Layer | Layer 1 | Layer 2 | Layer 3 |
| Intelligence | None | MAC address learning | IP routing |
| Forwarding | Broadcast | Unicast | Based on IP |
| Collision Domain | Shared | Separate per port | Separate |
| Bandwidth | Shared | Dedicated per port | Dedicated |
| Cost | Low | Medium | High |

## How Switches Work

### MAC Address Table (CAM Table)
- **Purpose:** Maps MAC addresses to switch ports
- **Learning:** Switches learn MAC addresses from source addresses of incoming frames
- **Aging:** Entries expire after inactivity (default 300 seconds)

### Frame Forwarding Process
1. **Learning:** Switch learns source MAC → incoming port
2. **Flooding:** If destination MAC unknown → broadcast to all ports
3. **Forwarding:** If destination MAC known → forward to specific port
4. **Filtering:** Drop frames with same source and destination port

### Switch Ports
- **Access Port:** Connects to end devices (computers, printers)
- **Trunk Port:** Connects to other switches or routers

## VLANs (Virtual Local Area Networks)

### What is a VLAN?
A VLAN is a logical grouping of devices on a network, regardless of physical location. It creates multiple broadcast domains on a single switch.

### Benefits of VLANs
- **Segmentation:** Isolate traffic by department or function
- **Security:** Restrict access between departments
- **Performance:** Reduce broadcast traffic
- **Flexibility:** Easy to move devices logically
- **Cost:** No need for additional switches

### VLAN Types

#### Management VLAN
- Used for administrative access to switch
- Example: VLAN 1 (default)

#### Data VLAN
- For user devices and data traffic
- Example: VLAN 10 (Accounting), VLAN 20 (Sales)

#### Voice VLAN
- For VoIP phones
- Separate quality of service (QoS) requirements

#### Native VLAN
- Untagged traffic on trunk ports
- Default is VLAN 1

### Cisco VLAN Configuration

#### Create a VLAN
```
Switch(config)# vlan 10
Switch(config-vlan)# name Accounting
Switch(config-vlan)# exit
```

#### Assign Port to VLAN
```
Switch(config)# interface fastethernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
Switch(config-if)# exit
```

#### Configure Trunk Port
```
Switch(config)# interface fastethernet 0/24
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 1,10,20,30
Switch(config-if)# exit
```

#### Set Native VLAN on Trunk
```
Switch(config-if)# switchport trunk native vlan 1
```

## Spanning Tree Protocol (STP)

### Why STP?
- Prevents loops in switched networks
- Automatically disables redundant paths
- Re-enables paths if primary link fails

### How STP Works

**Election Process:**
1. **Root Bridge Election:** Switch with lowest Bridge ID becomes root
2. **Root Port:** Each non-root switch selects best port to root
3. **Designated Port:** Each segment gets one designated port
4. **Blocking:** All other ports go to blocking state

**Port States:**
- **Blocking:** Listening state (doesn't forward frames)
- **Listening:** Learning MAC addresses
- **Learning:** Building MAC table
- **Forwarding:** Actively forwarding frames
- **Disabled:** Port is shut down

### Rapid Spanning Tree (RSTP)
- Faster convergence than STP
- Better for modern networks
- Reduced recovery time

## Cisco Switch Configuration

### Initial Switch Setup
```
Switch(config)# hostname Switch1
Switch(config)# enable password cisco123
Switch(config)# line console 0
Switch(config-line)# password console123
Switch(config-line)# exit
```

### Configure Management Interface (VLAN 1)
```
Switch(config)# interface vlan 1
Switch(config-if)# ip address 192.168.1.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit
Switch(config)# ip default-gateway 192.168.1.254
```

### View VLAN Information
```
Switch# show vlan brief
Switch# show vlan id 10
Switch# show vlan name Accounting
```

### View Switch Interfaces
```
Switch# show interface status
Switch# show interface fastethernet 0/1
```

### View MAC Address Table
```
Switch# show mac-address-table
Switch# show mac-address-table vlan 10
```

### View Spanning Tree Status
```
Switch# show spanning-tree
Switch# show spanning-tree vlan 10
```

## Port Security

### Purpose
Prevent unauthorized devices from connecting to switch ports.

### Configuration
```
Switch(config)# interface fastethernet 0/1
Switch(config-if)# switchport port-security
Switch(config-if)# switchport port-security mac-address sticky
Switch(config-if)# switchport port-security maximum 1
Switch(config-if)# switchport port-security violation shutdown
Switch(config-if)# exit
```

## Switch Types

### Access Switches
- Connect end devices (computers, printers)
- Usually have many fast ethernet ports
- Example: Cisco Catalyst 2960

### Distribution/Aggregation Switches
- Connect access switches
- Provide inter-VLAN routing
- Example: Cisco Catalyst 3750

### Core Switches
- High-speed backbone
- Connect distribution switches
- Example: Cisco Catalyst 6500

## Layer 3 Switching

### What is a Layer 3 Switch?
A switch with routing capabilities. Can perform both switching (Layer 2) and routing (Layer 3) functions.

### Benefits
- Improved performance (hardware-based routing)
- Simplified network design
- Inter-VLAN routing without separate router

### Inter-VLAN Routing Configuration
```
Switch(config)# ip routing
Switch(config)# interface vlan 10
Switch(config-if)# ip address 192.168.10.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit

Switch(config)# interface vlan 20
Switch(config-if)# ip address 192.168.20.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit
```

## Switching Best Practices

1. **Plan VLAN structure** before implementation
2. **Document** all VLAN assignments
3. **Use meaningful VLAN names** for clarity
4. **Enable port security** on access ports
5. **Configure spanning tree** for redundancy
6. **Use trunk ports** for switch-to-switch connections
7. **Regularly monitor** switch performance
8. **Backup switch configurations** regularly

## Key Concepts to Remember

- **Switches operate at Layer 2** (MAC addresses)
- **Broadcast domain** = VLAN
- **Collision domain** = Physical port
- **MAC address table** drives forwarding decisions
- **VLANs create logical separation** on switches
- **STP prevents loops** in redundant topologies
- **Layer 3 switches** combine switching and routing

## Practice Scenarios

1. **Configure multiple VLANs** on a switch
2. **Set up trunk ports** between switches
3. **Configure inter-VLAN routing** on Layer 3 switch
4. **Enable port security** and test violations
5. **Monitor MAC address table** and spanning tree

## Resources
- Study switch port modes (access vs trunk)
- Practice VLAN configuration on Cisco switches
- Understand spanning tree concepts
- Learn inter-VLAN routing techniques
