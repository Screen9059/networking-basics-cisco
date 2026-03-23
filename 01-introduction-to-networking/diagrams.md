# Networking Diagrams – Cisco Style

## 1. Home Network (Realistic)

        [Internet]
            |
         [Router]
       (WiFi Router)
      /      |      \
 [Laptop] [Phone] [Smart TV]

### Description:
- The router connects the home to the Internet.
- Devices connect via WiFi.
- The router acts as DHCP server and gateway.

---

## 2. Small Office Network

          [Internet]
              |
           [Router]
              |
           [Switch]
     /        |        \
 [PC1]     [PC2]    [Server]
                           \
                         [Printer]

### Description:
- Router connects to ISP.
- Switch distributes network to devices.
- Server provides services (files, apps).
- Printer is shared in the network.

---

## 3. Network with Access Point

          [Internet]
              |
           [Router]
              |
           [Switch]
              |
       [Access Point]
        /        \
   [Laptop]    [Phone]

### Description:
- Access Point extends wireless network.
- Used in offices or large homes.
- Switch connects wired infrastructure.

---

## 4. Basic Enterprise Network

            [Internet]
                |
            [Router]
                |
            [Firewall]
                |
            [Core Switch]
         /        |        \
    [PCs]     [Servers]   [APs]

### Description:
- Firewall protects the network.
- Core switch connects all major components.
- Servers host services.
- Access Points provide wireless access.

---

## 5. Star Topology (Cisco Standard)

            [PC1]
              |
[PC2] --- [Switch] --- [PC3]
              |
            [PC4]


       
### Description:
- Most common topology.
- Centralized control via switch.
- Easy to scale and troubleshoot.

