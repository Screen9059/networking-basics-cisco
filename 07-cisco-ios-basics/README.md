# CISCO IOS Basics

## Overview
Introduction to Cisco IOS, basic commands, and navigating the CLI.

## What is Cisco IOS?
Cisco IOS (Internetwork Operating System) is the operating system that runs on Cisco networking devices such as routers, switches, and firewalls. It provides the command-line interface (CLI) for device configuration and management.

## Accessing Cisco Devices

### Console Connection
- **Purpose:** Direct physical access to device
- **Cable:** RJ-45 to DB-9 or USB console cable
- **Speed:** 9600 baud rate (typical)
- **Tools:** PuTTY, HyperTerminal, Secure CRT

### Telnet
- **Purpose:** Remote access to device
- **Port:** TCP 23
- **Security:** Not encrypted (insecure)
- **Command:** `telnet 192.168.1.1`

### SSH (Secure Shell)
- **Purpose:** Secure remote access
- **Port:** TCP 22
- **Security:** Encrypted (secure)
- **Command:** `ssh -l admin 192.168.1.1`
- **Recommended:** Use SSH instead of Telnet

## IOS Command Modes

### User Exec Mode
- **Prompt:** `Router>`
- **Access:** Initial mode upon login
- **Capability:** View non-sensitive information
- **Commands:** ping, traceroute, show (limited)

### Privileged Exec Mode
- **Prompt:** `Router#`
- **Access:** Type `enable` from User mode
- **Capability:** View all information, change configuration
- **Commands:** configure, reload, debug, show (all)

### Global Configuration Mode
- **Prompt:** `Router(config)#`
- **Access:** Type `configure terminal` from Privileged mode
- **Capability:** Make system-wide configuration changes
- **Commands:** hostname, interface, router, line

### Interface Configuration Mode
- **Prompt:** `Router(config-if)#`
- **Access:** Type `interface [name]` from Global config
- **Capability:** Configure specific interface
- **Commands:** ip address, shutdown, description

### Subinterface Configuration Mode
- **Prompt:** `Router(config-subif)#`
- **Access:** Type `interface [name].[number]` from Global config
- **Capability:** Configure subinterfaces for VLANs

### Router Configuration Mode
- **Prompt:** `Router(config-router)#`
- **Access:** Type `router [protocol]` from Global config
- **Capability:** Configure routing protocol
- **Commands:** network, redistribute, passive-interface

## Basic Navigation Commands

### Moving Between Modes
```
# Enter Privileged Exec Mode
Router> enable

# Return to User Exec Mode
Router# disable

# Enter Global Configuration Mode
Router# configure terminal
Router# config t  (shortcut)

# Exit current mode (go back one level)
Router(config)# exit

# Exit to Privileged Exec Mode (from any config mode)
Router(config)# end
Router(config)# Ctrl+Z
```

### Getting Help
```
# List all available commands
Router> ?

# Help for specific command
Router> show ?

# Help with command parameters
Router> show ip ?

# Check if command syntax is correct
Router> configure?  (no space = shows commands starting with "configure")
```

### Command Abbreviation
```
# Most commands can be abbreviated
config t       # configure terminal
int fa 0/0     # interface fastethernet 0/0
sh ip route    # show ip route
no shut        # no shutdown
```

## Basic Device Configuration

### Set Device Hostname
```
Router(config)# hostname Router1
Router1(config)#
```

### Set Enable Password (Encrypted)
```
Router(config)# enable secret cisco123
```

### Set Console Line Password
```
Router(config)# line console 0
Router(config-line)# password console123
Router(config-line)# login
Router(config-line)# exit
```

### Set Telnet/SSH Access Password
```
Router(config)# line vty 0 15
Router(config-line)# password telnet123
Router(config-line)# login
Router(config-line)# exit
```

### Save Configuration
```
# Save to NVRAM (permanent)
Router# copy running-config startup-config
Router# write memory
Router# wr  (shortcut)

# View running configuration
Router# show running-config
Router# show run

# View saved configuration
Router# show startup-config
Router# show start
```

## Interface Configuration

### Configure IP Address on Interface
```
Router(config)# interface fastethernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
```

### Add Interface Description
```
Router(config)# interface fastethernet 0/0
Router(config-if)# description Link to Switch
Router(config-if)# exit
```

### View Interface Status
```
Router# show interface fastethernet 0/0
Router# show interface brief
Router# show ip interface brief
```

### Enable/Disable Interface
```
# Enable interface
Router(config-if)# no shutdown

# Disable interface
Router(config-if)# shutdown
```

## IP Configuration

### View IP Configuration
```
Router# show ip interface brief
Router# show ip route
Router# show ip address
```

### Configure Default Gateway (on Switches/PCs)
```
Switch(config)# ip default-gateway 192.168.1.254
```

### Configure Static Route
```
Router(config)# ip route 10.0.0.0 255.255.255.0 192.168.1.1
```

## Essential Show Commands

### Device Information
```
Router# show version          # IOS version, uptime, hardware
Router# show inventory        # Hardware inventory
Router# show running-config   # Current configuration
Router# show startup-config   # Saved configuration
Router# show history          # Command history
```

### Network Information
```
Router# show ip route         # Routing table
Router# show ip interface     # Detailed interface info
Router# show ip interface brief  # Summary interface info
Router# show ip address       # IP addresses configured
Router# show protocols        # Protocol status
```

### VLAN Information (Switches)
```
Switch# show vlan brief       # VLAN summary
Switch# show vlan id 10       # Specific VLAN info
Switch# show mac-address-table  # MAC address table
Switch# show spanning-tree    # STP status
```

### Connection Information
```
Router# show cdp neighbors           # CDP neighbors
Router# show interfaces status       # Interface status
Router# show connections             # Active connections
Router# show users                   # Connected users
```

### Debugging
```
Router# ping 192.168.1.1       # Test connectivity
Router# traceroute 8.8.8.8     # Trace route to destination
Router# show processes         # Running processes
Router# show memory            # Memory usage
Router# show cpu               # CPU usage
```

## Configuration Best Practices

### Create Backup Before Changes
```
Router# copy running-config tftp://[server-ip]/[filename]
```

### Add Configuration Timestamps
```
Router(config)# service timestamps debug datetime msec
Router(config)# service timestamps log datetime msec
```

### Enable Logging
```
Router(config)# logging 192.168.1.100
Router(config)# logging level informational
```

### Configure NTP (Time Synchronization)
```
Router(config)# ntp server 216.239.35.0
Router(config)# ntp server 216.239.35.4
```

## Useful Command Sequences

### Initial Router Setup
```
Router> enable
Router# configure terminal
Router(config)# hostname Router1
Router(config)# enable secret cisco123
Router(config)# interface gigabitethernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# ip route 0.0.0.0 0.0.0.0 192.168.1.254
Router(config)# exit
Router# copy running-config startup-config
```

### Initial Switch Setup
```
Switch> enable
Switch# configure terminal
Switch(config)# hostname Switch1
Switch(config)# interface vlan 1
Switch(config-if)# ip address 192.168.1.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit
Switch(config)# ip default-gateway 192.168.1.254
Switch(config)# exit
Switch# copy running-config startup-config
```

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Tab | Auto-complete command |
| ? | Get help |
| Ctrl+A | Move cursor to beginning of line |
| Ctrl+E | Move cursor to end of line |
| Ctrl+B | Move cursor back one character |
| Ctrl+F | Move cursor forward one character |
| Ctrl+C | Abort current command |
| Ctrl+Z | Exit configuration mode |
| Ctrl+X | Delete word to left of cursor |
| Up Arrow | Scroll through command history |
| Down Arrow | Scroll down through command history |

## Common IOS Features

### CLI Context Sensitive Help
- Press `?` at any time to see available options
- Type partial command followed by `?` to see completions

### Command History
- Access previous commands with Up Arrow key
- Search history with Ctrl+R

### Configuration Rollback
- Use `terminal edit` for line editing
- Use `no` command to undo configurations

### Buffer Management
- Use `terminal length 0` to disable paging
- Use `terminal length [number]` to set lines per screen

## Troubleshooting Tips

### Interface Not Coming Up
```
Router# show interface [name]
Router# show ip interface brief
Router(config-if)# no shutdown
```

### Cannot Connect to Device
- Check physical connections
- Verify IP addresses
- Test with ping
- Check ACLs and firewalls

### Configuration Not Saving
```
Router# copy running-config startup-config
Router# write memory
```

### Forgot Enable Password
- Use password recovery procedures (varies by device)
- May require physical access to device

## Key Concepts to Remember

- **IOS is case-insensitive** (SHOW = show)
- **Partial commands work** if unambiguous (sh ip route)
- **`?` is your friend** for help and navigation
- **`exit` moves up one level**, `end` goes to Privileged mode
- **Always save configuration** after making changes
- **Use `no` command** to undo configurations
- **SSH is more secure** than Telnet

## Practice Exercises

1. Connect to a Cisco device via console
2. Navigate through all command modes
3. Configure hostname and IP addresses
4. Create VLANs and assign ports
5. Configure routing protocols
6. Use show commands to verify configuration
7. Save and reload configurations

## Resources
- Practice with Cisco Packet Tracer or GNS3
- Memorize common command shortcuts
- Learn modal navigation thoroughly
- Practice configuration backup and restore
- Study IOS help system (`?` command)
