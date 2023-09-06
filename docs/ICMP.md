# ICMP

## What are the ICMP Field types? 
ICMP (Internet Control Message Protocol) is a network protocol used to send error messages and operational information about network conditions. ICMP operates at the network layer of the OSI model and is commonly used for diagnostics and troubleshooting in networking. ICMP responses are generated by routers, switches, or hosts to communicate various conditions and errors. 

Here are some common ICMP response types:

- **Echo Reply (Type 0)**: This is commonly known as a "ping" response. When a host receives an ICMP Echo Request, it responds with an Echo Reply, indicating that the destination host is reachable and operational.
- **Destination Unreachable (Type 3)**: This response indicates that the requested destination is unreachable for various reasons. There are different codes within this type that specify the reason for the unreachability, such as network unreachable, host unreachable, port unreachable, and more.
- **Redirect (Type 5)**: A router sends this response to inform a sender that a better route to a destination is available. It's used to optimize routing in a network.
- **Echo Request (Type 8)**: This is the "ping" request. A host sends an ICMP Echo Request to check if another host is reachable and operational.
- **Router Advertisement (Type 9)**
- **Router Solicitation (Type 10)**

- **Time Exceeded (Type 11)**: This response is generated when the Time-to-Live (TTL) field in an IP packet reaches zero. It indicates that the packet was discarded because it spent too much time in the network, likely due to routing loops or other network issues.
- **Parameter Problem (Type 12)**: This response indicates that there is an issue with the header of an IP packet, such as incorrect field values or options.
- **Source Quench (Type 4)**: This is used to request the sender to reduce the rate of sending packets to a specific destination, usually because the network is congested.

- **Timestamp Request (Type 13)**: A host sends this request to another host to request a timestamp from it. The receiving host responds with a Timestamp Reply.
- **Timestamp Reply (Type 14)**: This is the response to a Timestamp Request, providing the requested timestamp.
- **Address Mask Request (Type 17)**: A host sends this request to discover the subnet mask of another host. The receiving host responds with an Address Mask Reply.
- **Address Mask Reply (Type 18)**: This is the response to an Address Mask Request, providing the subnet mask information.