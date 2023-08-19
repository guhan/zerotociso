# Networking


## Key Concepts
- Encapsulation: addition of a header, and possibly footer to the data received by each layer from the layer above it
- Distance vector routing protocol: maintain a list of destination networks along with metrics of direction and distance (hops)
- Link state routing protocol: maintain a topography map of all connected network and use the map to determine the shortest path to the destination
- TCP Wrapper: an application that serves as a basic firewall by restricting access to ports and resources based on user IDs or system IDs.
- Socket: combination of IP address and port number

## Explain the OSI Model?
The (Open Systems Interconnection) OSI model has 7 layers, each layer is a communication layer and has specific protocols

Acronym: P D N T S P A

### Layer 1 - Physical 
Transmission of _raw bitstream data over the physical medium_, such as copper wires, fiber optic cables, or wireless signals.This includes specifications for the types of cables, connectors, pinouts, and signaling methods used to transmit the data. Bits. 

- Ethernet defines the physical and electrical characteristics of the communication medium.
- Network devices: Network Interface Cards, hubs, repeaters, concentrators, amplifiers

### Layer 2 - Data Link
Responsible for formatting the packet from the Network layer into the proper format for transmission. Provides error-free transmission of data frames between directly connected network nodes. It ensures reliable and synchronized data transfer and establishes point-to-point or multi-point connections. This layer also handles flow control, error detection, and media access control (MAC) addressing. Frame. 

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
Logical addressing and routing of data packets across different networks. It defines protocols that determine the best path for data to travel. Packet. 

- **Internet Protocol (IP)**: IP is the fundamental network layer protocol of the Internet. It provides logical addressing (IP addresses) for devices and defines how data packets are routed and delivered between networks. 
- IPv4 (Internet Protocol version 4) and IPv6 (Internet Protocol version 6) are the two prevalent versions of IP.

- **Internet Control Message Protocol (ICMP)**: ICMP is used for diagnostic and error reporting purposes in IP networks. It handles messages like "ping" to test network connectivity, error notifications, and routing information exchanges between network devices.

- **Internet Group Management Protocol (IGMP)**: IGMP is used for managing multicast group memberships on IP networks. It enables devices to join or leave multicast groups and facilitates the delivery of multicast traffic.

- **Border Gateway Protocol (BGP)**: BGP is a protocol used for routing between autonomous systems (AS) in the Internet. It enables routers in different ASes to exchange routing information and make routing decisions based on policies and network conditions.

- **Routing Information Protocol (RIP)**: RIP is a dynamic routing protocol used within smaller networks. It enables routers to exchange information about network reachability and automatically update routing tables based on the best available paths.

- **Open Shortest Path First (OSPF)**: OSPF is a link-state routing protocol commonly used in large enterprise networks and the Internet. It calculates the shortest path for data packets through the network based on link costs and creates a link-state database for routing decisions.

- **Interior Gateway Routing Protocol (IGRP) / Enhanced Interior Gateway Routing Protocol (EIGRP)**: IGRP and EIGRP are Cisco proprietary routing protocols used within autonomous systems. They facilitate efficient routing of IP packets within Cisco networks.

- **Internet Protocol Security (IPsec)**: IPsec is a protocol suite used for securing IP communications. It provides authentication, encryption, and integrity verification for IP packets, ensuring secure communication between network nodes.

- **Network Address Translation (NAT)**

### Layer 4 - Transport 
Ensures reliable data delivery between applications on different hosts.

- **TCP**: offers reliable, connection-oriented communication, ensuring that data is delivered accurately and in the correct order. TCP manages flow control, error detection, and retransmission of lost or corrupted packets.
  - Segment.
  - Full Duplex

- **User Datagram Protocol (UDP)**: UDP is a connectionless transport protocol that offers unreliable, best-effort communication. It is faster and less reliable compared to TCP since it does not guarantee delivery or provide mechanisms for error recovery.
  - Datagram.
  - Simplex

- **Stream Control Transmission Protocol (SCTP)**: SCTP is a transport protocol designed for more robust and reliable transmission than UDP while offering similar features to TCP. It provides message-oriented, connection-oriented communication and supports multi-homing, which allows a device to have multiple network connections simultaneously.

- **Datagram Congestion Control Protocol (DCCP)**: DCCP is a transport protocol that provides congestion control and flow control while allowing different service types and message-oriented communication. It supports both unreliable and reliable transmission modes.

- **Secure Sockets Layer (SSL)**
- **Transport Layer Security (TLS)**

### Layer 5 - Session
Establishes, manages, and terminates communication sessions between applications. It sets up and synchronizes communication between two devices. Data Stream

- **Network File System (NFS)**
- **Structured Query Language (SQL)**

- **Remote Procedure Call (RPC)**: RPC is a protocol that allows a program running on one host to invoke a procedure or function on another host. It includes session-related functions such as session establishment, authentication, and session termination.

- **Session Initiation Protocol (SIP)**: SIP is a protocol used for establishing, modifying, and terminating multimedia sessions such as VoIP (Voice over IP) calls and video conferences. SIP provides session control functions, allowing endpoints to establish and manage communication sessions.

- **NetBIOS Session Service**: NetBIOS (Network Basic Input/Output System) is a protocol suite used for communication between computers in a local area network. NetBIOS Session Service provides session management capabilities, allowing applications to establish and maintain sessions for data exchange.

- **AppleTalk Session Protocol**: AppleTalk is a suite of protocols used in Apple networks. The AppleTalk Session Protocol handles session management tasks, including session establishment, synchronization, and termination.

### Layer 6 - Presentation
Responsible for data representation, encryption, and compression. Data Stream.

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
Deals directly with applications and their interaction with the network. Data stream. 
​​
- HTTP
- FTP
- SMTP
- SSH
- DNS 

## What is a three-way handshake?
- A: SYN, initial sequence number
- B: SYN-ACK, initial sequence number 
- A: ACK, increments B’s ISN

## How are TCP connections closed?
- FIN: start the process for a graceful shutdown with a 4 way ACK
- RST: abrubt close

## What is in a TCP header?
- 20 to 60 bytes long

## What are the different modes of communication?
- **Simplex**: goes only one way
- **Half Duplex**: goes both ways but only one way at a time
- **Full Duplex**: goes both ways at the same time

## What is Multicast? 
One packet is sent and the network equipment replicates it to the multiple subscribers

## What is Unicast?
One packet is sent to one recipient

## How does a CDN use multicast?
CDNs use multicast in the following ways:
- **Content Ingestion**: CDNs often employ multicast for efficient content ingestion from the origin server to the edge nodes. Multicast allows the content to be replicated and distributed across the CDN infrastructure without the need for individual unicast streams from the origin server to each edge node.


- **Internal Communication**: Multicast is used for internal communication and synchronization between different CDN nodes. It helps in efficiently disseminating control and synchronization messages, enabling the CDN infrastructure to operate in a coordinated and synchronized manner.


- **Origin-Edge Communication**: CDNs may use multicast for communication between the origin server and the edge nodes. This allows for efficient distribution of updates or changes in content from the origin server to the edge nodes, minimizing the load on the origin server and optimizing the content replication process.


## What is IPSEC?
**Authentication Header (AH)**: AH provides integrity and authentication of IP packets. It verifies that the content of the packet has not been tampered with during transit and confirms the identity of the sender. AH uses cryptographic hash functions to generate a hash-based message authentication code (HMAC) for packet verification.


**Encapsulating Security Payload (ESP)**: ESP provides confidentiality, integrity, and authentication of IP packets. It encrypts the payload of the IP packets to protect the data from eavesdropping. Additionally, ESP can provide integrity checks to ensure data integrity and authentication of the sender.


**Security Associations (SA)**: SAs are established between IPsec peers to define the security parameters and establish a secure communication channel. The parameters include encryption and authentication algorithms, key exchange methods, and security protocols. SAs are identified by Security Parameter Index (SPI) and can be unidirectional or bidirectional.


**Key Management**: IPsec requires the management of cryptographic keys used for encryption, integrity, and authentication. Key management protocols and mechanisms, such as Internet Key Exchange (IKE), are employed to securely negotiate and exchange keys between IPsec peers.


**Tunnel Mode and Transport Mode**: IPsec can be used in two modes: tunnel mode and transport mode. In tunnel mode, the entire IP packet is encapsulated within a new IP packet, adding an additional layer of security. In transport mode, only the payload of the original IP packet is encrypted and authenticated, while the IP header remains intact.


**Compatibility and Interoperability**: IPsec is supported by a wide range of network devices, including routers, firewalls, and VPN gateways. It ensures compatibility and interoperability between different vendors' equipment, enabling secure communication across heterogeneous networks.

## What is Internet Security Association and Key Management Protocol (ISAKMP)?
Provies background security support for IPSEC by negotiating, establishing, modifying and deleting Security Associations (SAs)


## What is RADIUS?
Here's how RADIUS works:

- Client Authentication Request: When a user attempts to connect to a network resource, such as accessing the internet through a Wi-Fi network, the network access server (NAS) acting as a RADIUS client sends an authentication request to the RADIUS server.


- RADIUS Server Authentication: The RADIUS server receives the authentication request and verifies the user's credentials. The server can use various methods to authenticate the user, such as username and password, digital certificates, token-based authentication, or other authentication mechanisms.


- Authentication Response: After validating the user's credentials, the RADIUS server sends an authentication response to the RADIUS client. The response can be "Access Accept" if the authentication is successful or "Access Reject" if the authentication fails.


- Authorization and Accounting: If the authentication is successful, the RADIUS server can also provide authorization information to the RADIUS client, specifying the user's access privileges and restrictions. Additionally, RADIUS supports accounting functionality, allowing the server to log and track network resource usage, such as session duration, data transferred, and other relevant information.

Key features and benefits of RADIUS include:
- Centralized Authentication: RADIUS enables centralized user authentication and eliminates the need for separate authentication systems in different network access points. This simplifies the management of user credentials and improves security.
- Scalability: RADIUS is scalable and can handle a large number of users and network access points. It allows organizations to efficiently manage authentication and authorization for a large user base and multiple network devices.
- Standardization: RADIUS is an industry-standard protocol, ensuring interoperability and compatibility between different networking vendors and devices. This facilitates the deployment and integration of RADIUS in various network environments.
- Accounting and Auditing: RADIUS provides accounting functionality, allowing organizations to monitor and track network resource usage. This data can be used for auditing, billing, or troubleshooting purposes.


## Ports
- 2^16 or 65536 total
- 0 to 1023: service, well known, or privileged ports
- 1024 to 49151: registered software ports. [IANA](https://wwwiana.org) lets you register the port with them.
- 49152 to 65535: random or dynamic ports
