# Internet Protocol
IP is the fundamental network layer protocol of the Internet. It provides logical addressing (IP addresses) for devices and defines how data packets are routed and delivered between networks. 

Two prevalent versions of the protocol: 
- IPv4 (Internet Protocol version 4)
- IPv6 (Internet Protocol version 6) 


## What are the IP header protocol field values?
The Protocol field in the IP header is an 8-bit field that indicates the protocol of the data carried in the IP packet's payload. This field specifies which higher-level protocol is being used to interpret the data in the packet's payload. Here are some common Protocol field values along with their corresponding protocols:

- ICMP (Internet Control Message Protocol) - Protocol Number: 1
ICMP is used for sending error messages, operational information, and diagnostic messages about network conditions.
- IGMP (Internet Group Management Protocol) - Protocol Number: 2
IGMP is used by IP hosts to report their multicast group memberships to routers.
- TCP (Transmission Control Protocol) - Protocol Number: 6
TCP provides reliable, connection-oriented communication between devices. It is commonly used for data transmission in applications like web browsing, email, and file transfer.
- UDP (User Datagram Protocol) - Protocol Number: 17
UDP is a connectionless, lightweight protocol used for sending datagrams that don't require the same level of reliability as TCP. It's commonly used for streaming media, online gaming, and other applications where some packet loss is acceptable.
- IPv6 (Internet Protocol version 6) - Protocol Number: 41
This value indicates that the packet carries an IPv6 header in the payload. IPv6 is the successor to IPv4 and is designed to address the limitations of IPv4's address space.
- GRE (Generic Routing Encapsulation) - Protocol Number: 47
GRE is a tunneling protocol used to encapsulate a wide variety of network layer protocols into point-to-point connections.
- ESP (Encapsulating Security Payload) - Protocol Number: 50
ESP is used in IPsec to provide confidentiality, integrity, and authentication for the data in the packet.
- AH (Authentication Header) - Protocol Number: 51
AH is used in IPsec to provide authentication and integrity for the entire packet.
- ICMPv6 (Internet Control Message Protocol version 6) - Protocol Number: 58
ICMPv6 is the version of ICMP used in IPv6 networks to perform similar functions as ICMP does in IPv4.

