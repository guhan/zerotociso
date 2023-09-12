# OSI Model

## Explain the OSI Model?
The (Open Systems Interconnection) OSI model has 7 layers, each layer is a communication layer and has specific protocols

Acronym: Please Do Not Tell Samantha Premed Advise

### Layer 1 - Physical 
Transmission of _raw bitstream data over the physical medium_, such as copper wires, fiber optic cables, or wireless signals.This includes specifications for the types of cables, connectors, pinouts, and signaling methods used to transmit the data. Bits. 

- Ethernet defines the physical and electrical characteristics of the communication medium.
- Network devices: Network Interface Cards, hubs, repeaters, concentrators, amplifiers

### Layer 2 - Data Link
- Responsible for formatting the packet from the Network layer into the proper format for transmission.
- Provides error-free transmission of data frames between directly connected network nodes.
- It ensures reliable and synchronized data transfer and establishes point-to-point or multi-point connections. - This layer also handles flow control, error detection, and media access control (MAC) addressing.
- Packet is called a Frame. 

#### Split into two layers
- Media Access Control (MAC) which touches Layer 1
- Logical Link Control (LLC) which touches Layer 3

- **Address Resolution Protocol (ARP)**:  ARP is responsible for resolving or _mapping an IP address to a physical (MAC) address_ on a local network

- **Ethernet**: Ethernet (IEEE 802.3) is a widely used data link protocol in local area networks (LANs). It defines the physical and logical aspects of communication over Ethernet cables, including frame structure, addressing (MAC addresses), and media access control (MAC) methods such as Carrier Sense Multiple Access with Collision Detection (CSMA/CD) or Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA).

- Token Ring
- Fiber Distributed Data Interface (FDDI)
- Copper DDI (CDDI)
  
- **Point-to-Point Protocol (PPP)**: PPP is a data link protocol used for establishing and maintaining a direct connection between two nodes, typically over serial links. It supports various network layer protocols, such as IP, and provides features like authentication, error detection, and link quality monitoring.

- **High-Level Data Link Control (HDLC)**: HDLC is a synchronous data link protocol used in point-to-point and multipoint communication links. It provides error detection, error correction, and flow control mechanisms.

- **Asynchronous Transfer Mode (ATM)**: ATM is a data link protocol that operates over both local and wide area networks. It uses fixed-size cells for data transmission and supports various traffic types, including voice, video, and data.

- **Frame Relay**: Frame Relay is a packet-switching data link protocol used for connecting devices in wide area networks. It provides a simple and cost-effective way to transmit data over a shared network infrastructure.

- **Wireless LAN protocols**: Various data link protocols are used in wireless LANs, such as IEEE 802.11 standards (e.g., 802.11a/b/g/n/ac) for Wi-Fi networks. These protocols define frame formats, MAC addressing, and media access control methods specific to wireless communication.

- **Synchronous Data Link Control (SDLC)**: SDLC is a synchronous data link protocol developed by IBM. It is used for communication between IBM mainframe computers and other devices.

- Layer 2 Forwarding (L2F)
- Layer 2 Tunneling Protocol (L2TP)
- Point to Point Tunneling Protocol (PPTP)
- Integrated Services Digital Network (ISDN)
- Serial Line Internet Protocol (SLIP)

- MAC Addresses: 00-13-02 (Vendor aka Organizationally Unique Identifier) 1F-58-F3 (unique number assigned to that interface)

### Layer 3 - Network 
- Logical addressing and routing of data packets across different networks.
- It defines protocols that determine the best path for data to travel.
- Packet 

- [**Internet Protocol (IP)**](IP.md)

- [**Internet Control Message Protocol (ICMP)**](docs/ICMP.md)

- **Internet Group Management Protocol (IGMP)**: IGMP is used for managing multicast group memberships on IP networks. It enables devices to join or leave multicast groups and facilitates the delivery of multicast traffic.

- **Border Gateway Protocol (BGP)**: BGP is a protocol used for routing between autonomous systems (AS) in the Internet. It enables routers in different ASes to exchange routing information and make routing decisions based on policies and network conditions.

- **Routing Information Protocol (RIP)**: RIP is a dynamic routing protocol used within smaller networks. It enables routers to exchange information about network reachability and automatically update routing tables based on the best available paths.

- **Open Shortest Path First (OSPF)**: OSPF is a link-state routing protocol commonly used in large enterprise networks and the Internet. It calculates the shortest path for data packets through the network based on link costs and creates a link-state database for routing decisions.

- **Interior Gateway Routing Protocol (IGRP) / Enhanced Interior Gateway Routing Protocol (EIGRP)**: IGRP and EIGRP are Cisco proprietary routing protocols used within autonomous systems. They facilitate efficient routing of IP packets within Cisco networks.

- **Internet Protocol Security (IPsec)**: IPsec is a protocol suite used for securing IP communications. It provides authentication, encryption, and integrity verification for IP packets, ensuring secure communication between network nodes.

- **Network Address Translation (NAT)**

### Layer 4 - Transport 
- Ensures reliable data delivery between applications on different hosts.

- [**Tranmission Control Protocol (TCP)**](TCP.md)

- [**User Datagram Protocol (UDP)**](UDP.md)

- **Stream Control Transmission Protocol (SCTP)**: SCTP is a transport protocol designed for more robust and reliable transmission than UDP while offering similar features to TCP. It provides message-oriented, connection-oriented communication and supports multi-homing, which allows a device to have multiple network connections simultaneously.

- **Datagram Congestion Control Protocol (DCCP)**: DCCP is a transport protocol that provides congestion control and flow control while allowing different service types and message-oriented communication. It supports both unreliable and reliable transmission modes.

- **Secure Sockets Layer (SSL)**
- **Transport Layer Security (TLS)**

### Layer 5 - Session
- Establishes, manages, and terminates communication sessions between applications.
- It sets up and synchronizes communication between two devices.
- Packet is called Data Stream

There are three modes: Simplex, Half Duplex, and Full Duplex

- **Network File System (NFS)**
- **Structured Query Language (SQL)**

- **Remote Procedure Call (RPC)**: RPC is a protocol that allows a program running on one host to invoke a procedure or function on another host. It includes session-related functions such as session establishment, authentication, and session termination.

- **Session Initiation Protocol (SIP)**: SIP is a protocol used for establishing, modifying, and terminating multimedia sessions such as VoIP (Voice over IP) calls and video conferences. SIP provides session control functions, allowing endpoints to establish and manage communication sessions.

- **NetBIOS Session Service**: NetBIOS (Network Basic Input/Output System) is a protocol suite used for communication between computers in a local area network. NetBIOS Session Service provides session management capabilities, allowing applications to establish and maintain sessions for data exchange.

- **AppleTalk Session Protocol**: AppleTalk is a suite of protocols used in Apple networks. The AppleTalk Session Protocol handles session management tasks, including session establishment, synchronization, and termination.

### Layer 6 - Presentation
- Responsible for data representation, encryption, and compression.
- Data Stream.

- **Encryption and Decryption**: The Presentation Layer may involve encryption and decryption processes to secure the data during transmission. Encryption protocols like SSL/TLS (Secure Sockets Layer/Transport Layer Security) and cryptographic algorithms such as AES (Advanced Encryption Standard) operate at this layer to protect the confidentiality and integrity of the data.

- **Data Compression**: The Presentation Layer can include compression techniques to reduce the size of the data for efficient transmission. Compression protocols and algorithms like ZIP, LZW (Lempel-Ziv-Welch), or gzip may be employed to minimize the bandwidth utilization.

- **Data Formatting and Syntax**: The Presentation Layer handles the formatting and syntax of the data exchanged between applications. This includes encoding schemes, character sets, and data representation formats. For example, protocols like ASCII, Unicode, or EBCDIC are used to represent and interpret character data.
  - ASCII
  - TIFF
  - JPEG
  - MPEG
  - MIDI
  - PNG

- **Data Translation**: The Presentation Layer may involve data translation or code conversion to enable communication between systems with different data formats or character encoding schemes. Protocols like MIME (Multipurpose Internet Mail Extensions) are used to facilitate the exchange of different types of data, such as multimedia content or email attachments.


### Layer 7 - Application 
- Deals directly with applications and their interaction with the network.
- Data stream
​​
- HTTP
- FTP
- SMTP
- SSH
- [**DNS**](DNS.md) 
