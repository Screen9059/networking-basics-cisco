TCP/IP Lab in Cisco Packet Tracer (Layer 4 + Application Layer)
Objective:

Simulate how data flows from the application layer through the transport layer using TCP and UDP, and how services like HTTP, FTP, and Ping work.

Step 1: Open Packet Tracer and Set Up Devices
Open Cisco Packet Tracer.
Drag 2 PCs onto the workspace (PC0 and PC1).
Drag a switch to connect them.
Step 2: Connect Devices
Use Copper Straight-Through cables to connect:
PC0 → Switch
PC1 → Switch
Verify connections (green dots indicate the link is active).
Step 3: Assign IP Addresses
Click PC0 → Desktop → IP Configuration:
IP: 192.168.1.10
Subnet Mask: 255.255.255.0
Gateway: leave blank (not needed for same LAN)
Click PC1 → Desktop → IP Configuration:
IP: 192.168.1.11
Subnet Mask: 255.255.255.0
Step 4: Test Basic Connectivity (ICMP / Ping)
Go to PC0 → Desktop → Command Prompt.

Run:

ping 192.168.1.11


✅ Green replies confirm connectivity.

This shows data passing through Layer 3 (IP) but relies on Layer 4 ICMP.

Step 5: Simulate Application Layer Services
On PC1 → Desktop → Services, enable:
HTTP
FTP

On PC0 → Desktop → Web Browser, type:

192.168.1.11


✅ You should see the HTTP server page from PC1.

On PC0 → Desktop → File Transfer, test FTP:
Connect to 192.168.1.11
Upload/download files.

This demonstrates Application Layer using TCP (HTTP/FTP) on Layer 4.

Step 6: Observe TCP vs UDP
Add a PC2 to the network.
Go to PC2 → Desktop → IP Configuration:
IP: 192.168.1.12
Subnet Mask: 255.255.255.0

On PC0, open Command Prompt and run:

ping 192.168.1.12

ICMP uses Layer 4 concepts, similar to UDP.
Optional: Use Packet Tracer Simulation Mode:
Switch to Simulation Mode.
Click Add Simple PDU → PC0 → PC1.
Observe TCP handshake for HTTP/FTP and data encapsulation.
Step 7: Use Simulation Mode to Visualize Layers
Switch to Simulation Mode in Packet Tracer.
Select Show All Layers.
Send a PDU from PC0 → PC1.
Observe:
Application Layer: HTTP request
Transport Layer: TCP segments with ports (80, 21)
Network Layer: IP addresses
Data Link Layer: Ethernet frames

This reinforces the flow you diagrammed earlier.

Step 8: Optional – Add Router for Internet Simulation
Drag a router and connect it to the switch.
Assign IPs to router interfaces.
Test connectivity across different subnets to demonstrate Layer 3 + Layer 4 interactions.
✅ What You Learned
Layer 4 segments data (TCP/UDP) and uses port numbers.
Application Layer (HTTP/FTP) generates and consumes data.
Packet Tracer simulation shows encapsulation: Application → Transport → Network → Data Link.
You can see how TCP performs a handshake and ensures reliable delivery.
