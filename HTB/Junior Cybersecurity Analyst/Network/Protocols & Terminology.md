## Remote Access and File Transfer Protocols

- **SSH (Secure Shell)**  
    A secure protocol used for remote system access and command execution. It replaces insecure protocols such as Telnet and RSH.
    
- **FTP (File Transfer Protocol)**  
    Used to transfer files between systems. Credentials are sent in clear text by default.
    
- **RSH (Remote Shell)**  
    Allows remote command execution without encryption. Obsolete and insecure.
    

---

## Web and Email Protocols

- **HTTP (Hypertext Transfer Protocol)**  
    A client-server protocol used to transfer data on the web.
    
- **SMTP (Simple Mail Transfer Protocol)**  
    Used for sending and receiving email messages.
    
- **AJAX (Asynchronous JavaScript and XML)**  
    A web development technique that enables dynamic content updates without reloading the page.
    
- **ISAPI (Internet Server Application Programming Interface)**  
    A set of APIs used to build high-performance extensions for web servers, mainly Microsoft IIS.
    

---

## File and Resource Sharing

- **SMB (Server Message Block)**  
    Used to share files, printers, and other resources, mainly in Windows networks.
    
- **NFS (Network File System)**  
    Enables access to remote files, commonly used in Unix/Linux environments.
    

---

## Management and Synchronization Protocols

- **SNMP (Simple Network Management Protocol)**  
    Used to monitor and manage network devices.
    
- **NTP (Network Time Protocol)**  
    Synchronizes time across systems in a network.
    

---

## Security and Authentication

### Wireless Security

- **WEP (Wired Equivalent Privacy)**  
    An outdated and vulnerable wireless security protocol.
    
- **WPA (Wi-Fi Protected Access)**  
    An improvement over WEP, still found in legacy systems.
    
- **TKIP (Temporal Key Integrity Protocol)**  
    A weak encryption algorithm associated with WPA.
    

### Authentication Frameworks

- **EAP (Extensible Authentication Protocol)**  
    An authentication framework supporting multiple authentication methods.
    
- **LEAP (Lightweight EAP)**  
    A Cisco proprietary protocol. Considered insecure today.
    
- **PEAP (Protected EAP)**  
    Creates an encrypted tunnel to protect authentication processes.
    

### Encryption and Access Control

- **PGP (Pretty Good Privacy)**  
    Used to encrypt emails and files.
    
- **TACACS**  
    Provides centralized Authentication, Authorization, and Accounting (AAA).
    

---

## Routing and Switching

### Routing Protocols

- **RIP (Routing Information Protocol)**  
    A distance-vector routing protocol with limited scalability.
    
- **OSPF (Open Shortest Path First)**  
    A link-state Interior Gateway Protocol (IGP), widely used.
    
- **IGRP / EIGRP**  
    Cisco routing protocols, with EIGRP being more efficient and hybrid.
    

### Switching and Layer 2

- **VLAN (Virtual LAN)**  
    Logical segmentation of a network.
    
- **VTP (VLAN Trunking Protocol)**  
    Centralized VLAN management on Cisco switches.
    
- **STP (Spanning Tree Protocol)**  
    Prevents loops in Layer 2 Ethernet networks.
    

---

## Redundancy and High Availability

- **HSRP (Hot Standby Router Protocol)**  
    Provides router redundancy in Cisco environments.
    
- **VRRP (Virtual Router Redundancy Protocol)**  
    An open standard for gateway redundancy.
    

---

## Voice and Multimedia

- **SIP (Session Initiation Protocol)**  
    Used to establish, manage, and terminate voice and video sessions.
    
- **VOIP (Voice Over IP)**  
    Technology that enables phone calls over IP networks.
    

---

## VPN and Tunneling

- **VPN (Virtual Private Network)**  
    Creates an encrypted tunnel over the Internet.
    
- **IPsec (Internet Protocol Security)**  
    Provides network-layer security and is the foundation of many VPNs.
    
- **PPTP (Point-to-Point Tunneling Protocol)**  
    An old and insecure tunneling protocol.
    
- **IKE (Internet Key Exchange)**  
    Handles authentication and key negotiation for IPsec.
    
- **GRE (Generic Routing Encapsulation)**  
    Encapsulates traffic inside tunnels.
    

---

## Addressing and Web Resources

- **URI (Uniform Resource Identifier)**  
    A generic identifier for resources on the Internet.
    
- **URL (Uniform Resource Locator)**  
    A subset of URI that specifies protocol and domain.
    
- **NAT (Network Address Translation)**  
    Translates private IP addresses into public ones.
    

---

## Other Relevant Concepts

- **CRLF (Carriage Return Line Feed)**  
    Indicates end-of-line in certain text formats and protocols.
    
- **NNTP (Network News Transfer Protocol)**  
    Used for distributing messages in newsgroups.
    
- **CDP (Cisco Discovery Protocol)**  
    Discovers Cisco devices on a local network.
    
- **SCADA (Supervisory Control and Data Acquisition)**  
    Industrial control systems used in critical infrastructures.
    
- **SMS (Systems Management Server)**  
    Microsoft solution for centralized system management.
    
- **MBSA (Microsoft Baseline Security Analyzer)**  
    Tool for detecting security vulnerabilities in Windows systems.
    



## Application Layer (Layer 7)

Protocols that provide **direct services to applications or users**.

- **HTTP**
    
- **SMTP**
    
- **FTP**
    
- **SSH**
    
- **SNMP**
    
- **NTP**
    
- **SMB**
    
- **NFS**
    
- **SIP**
    
- **VOIP**
    
- **NNTP**
    
- **RSH**
    
- **SCADA**
    
- **SMS**
    
- **MBSA**
    
- **AJAX** (technique built on top of HTTP)
    
- **ISAPI**
    

Key idea:  
If the protocol is something a user, service, or application explicitly “uses”, it is almost always Layer 7.

---

## Presentation Layer (Layer 6)

Responsible for **encryption, compression, and data representation**.

- **PGP**
    
- **WEP**
    
- **WPA**
    
- **TKIP**
    

Key idea:  
Anything focused on **cryptography or data protection**, rather than transport, fits here conceptually.

---

## Session Layer (Layer 5)

Manages **session establishment, maintenance, and termination**.

- **SIP**
    
- **IKE**
    
- **PEAP**
    
- **LEAP**
    
- **EAP**
    

Key idea:  
Authentication handshakes and session negotiation logic belong here.

---

## Transport Layer (Layer 4)

Provides **end-to-end communication**, ports, and reliability.

- (Not explicitly listed in your content, but typically:)
    
    - **TCP**
        
    - **UDP**
        

Important note:  
Most application-layer protocols implicitly rely on TCP or UDP, even if they are not mentioned.

---

## Network Layer (Layer 3)

Handles **logical addressing, routing, and packet forwarding**.

- **IPsec**
    
- **GRE**
    
- **NAT**
    
- **RIP**
    
- **OSPF**
    
- **IGRP**
    
- **EIGRP**
    
- **VPN** (conceptually spans L3–L4, but anchored here)
    

Key idea:  
If it routes packets or modifies IP addressing, it belongs to Layer 3.

---

## Data Link Layer (Layer 2)

Responsible for **frames, MAC addressing, switching, and loop prevention**.

- **VLAN**
    
- **VTP**
    
- **STP**
    
- **CDP**
    
- **HSRP**
    
- **VRRP**
    

Key idea:  
Protocols that operate between directly connected devices or switches are Layer 2.

---

## Physical Layer (Layer 1)

- No protocols from your list operate directly at this layer.
    

---

## Cross-Layer / Conceptual Elements

These do not belong cleanly to a single OSI layer but are important:

- **URI / URL** – Resource identification (application-level concepts)
    
- **CRLF** – Formatting detail used across multiple application protocols
    
- **VPN** – Architecture spanning multiple layers



--------


## Common Protocols Overview

Internet protocols are standardized rules defined in **RFCs (Request for Comments)** that specify how devices communicate over a network. These standards ensure interoperability between different hardware and software platforms.

For communication to occur:

- Devices must be connected through a **communication channel** (wired or wireless).
    
- Data is exchanged using **standardized protocols** that define structure, format, and behavior.
    

The two fundamental transport mechanisms are:

- **TCP (Transmission Control Protocol)**
    
- **UDP (User Datagram Protocol)**
    

Understanding these protocols is essential because **all network communication is built on top of them**.

---

## Transmission Control Protocol (TCP)

TCP is a **connection-oriented** protocol. Before data transmission begins, TCP establishes a connection using the **Three-Way Handshake**:

1. SYN
    
2. SYN-ACK
    
3. ACK
    

Once established:

- The connection is maintained until transmission is complete.
    
- Data delivery is **reliable, ordered, and error-checked**.
    

Example:

- When accessing a website, the browser sends an **HTTP request over TCP**.
    
- The server responds with HTML data over the same TCP connection.
    
- The connection remains active until all data is transferred.
    

Key characteristics:

- Reliable
    
- Ordered delivery
    
- Error detection and retransmission
    
- Higher overhead → slower than UDP
    

---

## Common TCP-Based Protocols

### Remote Access and Management

- **Telnet (23)** – Insecure remote login
    
- **SSH (22)** – Secure remote login
    
- **RDP (3389)** – Remote desktop access (Windows)
    
- **REXEC (512)** – Remote command execution
    
- **RLOGIN (513)** – Remote login (legacy)
    

### Web and Application Services

- **HTTP (80)** – Web traffic
    
- **HTTPS (443)** – Secure web traffic
    
- **SOAP (80, 443)** – Web services
    
- **Squid Proxy (3128)** – HTTP caching and forwarding
    

### File and Resource Sharing

- **FTP (20–21)** – File transfer
    
- **SMB (445)** – Windows file sharing
    
- **NFS (111, 2049)** – Unix/Linux file sharing
    
- **SCP (22)** – Secure file copy
    

### Email Services

- **SMTP (25)** – Send email
    
- **POP3 (110)** – Retrieve emails
    
- **IMAP (143)** – Access emails remotely
    

### Directory and Authentication

- **LDAP (389)** – Directory services
    
- **Kerberos (88)** – Authentication and authorization
    
- **RADIUS (1812–1813)** – Centralized authentication
    
- **TCP Wrappers (113)** – Access control
    

### Databases

- **MySQL (3306)**
    
- **Microsoft SQL Server (1433)**
    
- **Oracle TNS Listener (1521/1526)**
    
- **Ingres Lock (1524)**
    
- **DB2 (50000)**
    

### Other TCP Protocols

- **NNTP (119)** – Newsgroups
    
- **Ident (113)** – User identification
    
- **X11 (6000)** – GUI forwarding
    
- **SIP (5060)** – VoIP signaling
    
- **SSL (443)** – Encrypted communication
    
- **ISAKMP (500)** – VPN key management
    
- **PPTP (1723)** – VPN tunneling
    
- **KINK (892)** – Kerberos-based key exchange
    

---

## User Datagram Protocol (UDP)

UDP is a **connectionless** protocol:

- No handshake
    
- No delivery guarantee
    
- No retransmission
    

Packets are sent independently without checking if they arrive.

Example:

- Video streaming (e.g., YouTube)
    
- Some packet loss is acceptable
    
- Speed is prioritized over reliability
    

Key characteristics:

- Fast
    
- Low overhead
    
- Unreliable
    
- No ordering guarantees
    

---

## Common UDP-Based Protocols

- **DNS (53)** – Domain name resolution
    
- **TFTP (69)** – Simple file transfer
    
- **NTP (123)** – Time synchronization
    
- **SNMP (161)** – Network monitoring
    
- **RIP (520)** – Routing information exchange
    
- **IKE (500)** – VPN key exchange
    
- **BOOTP (68)** – Network bootstrapping
    
- **DHCP (67)** – Dynamic IP assignment
    
- **NetBIOS-NS (137)** – Name resolution
    
- **UPnP (1900)** – Device discovery
    
- **Syslog (514)** – Log collection
    
- **IRC (194)** – Chat protocol
    
- **VNC (5900)** – Remote desktop
    
- **XDMCP (177)** – Remote X11 login
    
- **OpenPGP (11371)** – Encryption services
    
- **IPsec (500)** – Secure communication
    

---

## Internet Control Message Protocol (ICMP)

ICMP is used for **error reporting and network diagnostics**, not for data transmission.

It supports:

- Status messages
    
- Error notifications
    
- Connectivity testing
    

Versions:

- **ICMPv4** – IPv4
    
- **ICMPv6** – IPv6 (enhanced functionality)
    

---

## ICMP Requests

- **Echo Request** – Tests reachability (ping, traceroute)
    
- **Timestamp Request** – Retrieves remote time
    
- **Address Mask Request** – Requests subnet mask
    

---

## ICMP Messages

- **Echo Reply** – Response to echo request
    
- **Destination Unreachable** – Packet cannot be delivered
    
- **Redirect** – Better route available
    
- **Time Exceeded** – TTL reached zero
    
- **Parameter Problem** – Invalid header
    
- **Source Quench** – Congestion control (deprecated)
    

---

## Time-To-Live (TTL)

TTL limits a packet’s lifetime to prevent routing loops.

Behavior:

- TTL is decremented by 1 at each router
    
- When TTL reaches 0, the packet is dropped
    
- An **ICMP Time Exceeded** message is returned
    

TTL can be used to:

- Estimate hop count
    
- Infer approximate distance
    
- Guess operating systems (heuristic)
    

Typical default TTL values:

- **Windows**: 128
    
- **Linux / macOS**: 64
    
- **Solaris**: 255
    

Note: TTL values can be modified, so OS detection is not definitive.

---

## Voice over Internet Protocol (VoIP)

VoIP enables voice and multimedia communication over IP networks instead of traditional phone lines.

Examples:

- Skype
    
- WhatsApp
    
- Zoom
    
- Slack
    
- Google Hangouts
    

Common ports:

- **SIP**: TCP/5060, TCP/5061
    
- **H.323**: TCP/1720 (legacy)
    

SIP is the dominant protocol for VoIP signaling.

---

## Session Initiation Protocol (SIP)

SIP is a **signaling protocol** used to:

- Initiate
    
- Modify
    
- Maintain
    
- Terminate real-time sessions
    

### Common SIP Methods

- **INVITE** – Start a session
    
- **ACK** – Confirm INVITE
    
- **BYE** – End session
    
- **CANCEL** – Cancel pending INVITE
    
- **REGISTER** – Register user agent
    
- **OPTIONS** – Query capabilities
    

---

## Information Disclosure in SIP

SIP can be abused for **user enumeration** and reconnaissance.

- **OPTIONS requests** can reveal:
    
    - Active users
        
    - Supported codecs
        
    - Server capabilities
        

Cisco environments may expose:

- **SEPxxxx.cnf** files  
    Configuration files for Cisco IP phones containing:
    
    - Device model
        
    - Firmware version
        
    - Network settings
        

These files can be valuable during security assessments.