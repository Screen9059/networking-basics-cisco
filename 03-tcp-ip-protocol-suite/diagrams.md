
Layer 4 - Application Layer

| Protocol | Full Form                          | Purpose / Meaning                                          | Common Use                                       |
| -------- | ---------------------------------- | ---------------------------------------------------------- | ------------------------------------------------ |
| HTTP     | HyperText Transfer Protocol        | Transfers web pages (not secure)                           | Browsing websites                                |
| HTTPS    | HyperText Transfer Protocol Secure | Secure version of HTTP (encrypted)                         | Secure browsing, logins, payments                |
| FTP      | File Transfer Protocol             | Transfers files between computers                          | Uploading/downloading files to servers           |
| SMTP     | Simple Mail Transfer Protocol      | Sends emails between servers                               | Sending emails                                   |
| DNS      | Domain Name System                 | Translates domain names into IP addresses                  | Accessing websites using names (e.g. google.com) |
| Telnet   | —                                  | Remote access to another computer (not secure)             | Remote command-line access (old/unsafe)          |
| SSH      | Secure Shell                       | Secure remote access to systems                            | Server management, secure login                  |
| POP3     | Post Office Protocol v3            | Downloads emails to a device (usually deletes from server) | Basic email retrieval                            |
| IMAP     | Internet Message Access Protocol   | Syncs emails across devices (keeps on server)              | Modern email apps (Gmail, Outlook)               |


Layer 3 - Transport Layer



| Protocol | Full Form                            | Meaning / Purpose                             | Key Features                                          | Difference                               |
| -------- | ------------------------------------ | --------------------------------------------- | ----------------------------------------------------- | ---------------------------------------- |
| TCP      | Transmission Control Protocol        | Reliable data transfer between devices        | Connection-oriented, error checking, ordered delivery | Slow but very reliable                   |
| UDP      | User Datagram Protocol               | Fast data transfer without reliability checks | Connectionless, no error checking, unordered          | Very fast but unreliable                 |
| SCTP     | Stream Control Transmission Protocol | Combines features of TCP and UDP              | Reliable, multi-streaming, multi-connection support   | More advanced, supports multiple streams |



Layer 2 - Internet Layer

| Protocol  | Meaning                            | Purpose (Easy)                        | Key Point                               |
| --------- | ---------------------------------- | ------------------------------------- | --------------------------------------- |
| IP (IPv4) | Internet Protocol version 4        | Gives devices an address              | Uses 32-bit address (e.g. 192.168.1.1)  |
| IP (IPv6) | Internet Protocol version 6        | New version of IP with more addresses | Uses 128-bit address (very large range) |
| ICMP      | Internet Control Message Protocol  | Sends error & status messages         | Used for ping (check connection)        |
| IGMP      | Internet Group Management Protocol | Manages group communication           | Used for streaming (multicast)          |
| IPsec     | Internet Protocol Security         | Secures IP communication              | Encrypts and protects data              |


Layer 1 - Network Layer

| Protocol | Full Form                     | Purpose (Easy)                            | Key Point                                   |
| -------- | ----------------------------- | ----------------------------------------- | ------------------------------------------- |
| Ethernet | —                             | Connects devices in a local network (LAN) | Most common wired network                   |
| PPP      | Point-to-Point Protocol       | Connects two devices directly             | Used in internet connections (dial-up, DSL) |
| ARP      | Address Resolution Protocol   | Finds MAC address from IP address         | Links IP → physical address                 |
| SLIP     | Serial Line Internet Protocol | Sends IP data over serial connections     | Older, replaced by PPP 


Port Numbers 

| Port Number | Protocol | Application (Easy)  | Purpose                           |
| ----------- | -------- | ------------------- | --------------------------------- |
| 80          | HTTP     | Web browsing        | Loads websites (not secure)       |
| 443         | HTTPS    | Secure web browsing | Loads secure websites (encrypted) |
| 22          | SSH      | Secure remote login | Access servers safely             |

