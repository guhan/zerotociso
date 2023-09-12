# Networking Basics


## Key Concepts
- **Intranet**: private network designed to host some services
- **Extranet**: both a private network and also serves up some services for public/Internet consumption
- **Encapsulation**: addition of a header, and possibly footer to the data received by each layer from the layer above it
- **Distance vector routing protocol**: maintain a list of destination networks along with metrics of direction and distance (hops)
- **Link state routing protocol**: maintain a topography map of all connected network and use the map to determine the shortest path to the destination
- **TCP Wrapper**: an application that serves as a basic firewall by restricting access to ports and resources based on user IDs or system IDs.
- **Socket**: combination of IP address and port number
- **Converged protocols**: merging of speciality and proprietary protocols with standard protocols
- PAN: Personal Area Network
- LAN: Local Area Network
- WAN: Wide Area Network
- MAN: Metropolitan Area Network
- GAN: Global Area Network


## What are the different modes of communication?
- **Simplex**: goes only one way
- **Half Duplex**: goes both ways but only one way at a time
- **Full Duplex**: goes both ways at the same time

## What is Multicast? 
One packet is sent and the network equipment replicates it to the multiple subscribers

## What is Unicast?
One packet is sent to one recipient

## Ports
- 2^16 or 65536 total
- 0 to 1023: service, well known, or privileged ports
- 1024 to 49151: registered software ports. [IANA](https://wwwiana.org) lets you register the port with them.
- 49152 to 65535: random or dynamic ports
