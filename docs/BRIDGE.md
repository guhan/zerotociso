# Bridge
A bridge, in the context of computer networking, is a network device that operates at the Data Link Layer (Layer 2) of the OSI (Open Systems Interconnection) model. Its primary function is to connect and filter traffic between two or more network segments, making it possible for devices on those segments to communicate with each other.

## Segmentation
Bridges are used to segment a larger network into smaller, more manageable segments. Each network segment, often referred to as a collision domain, is connected to one of the bridge's ports. This segmentation helps reduce network traffic and collisions, improving overall network performance.
## Filtering
Bridges examine the MAC (Media Access Control) addresses of data frames to determine whether they should be forwarded or filtered out. MAC addresses are unique identifiers assigned to network interface cards (NICs) of devices. The bridge maintains a MAC address table (also known as a bridge table or forwarding table) that maps MAC addresses to the port on which they were last seen.
## Forwarding Decisions
When a data frame arrives at a bridge, the bridge checks the MAC address of the source and destination devices. If the MAC address of the destination device is found in the bridge's MAC address table and is associated with a different port than the one on which the frame arrived, the bridge forwards the frame to the appropriate port. If the destination is on the same segment as the source, the frame is filtered out and not forwarded, reducing unnecessary traffic on other segments.
## Loop Prevention
Bridges use a protocol called the Spanning Tree Protocol (STP) to prevent network loops. Loops can occur when multiple bridges or switches are connected together, potentially causing broadcast storms and network instability. STP ensures that only one path is active in the network at a time, while other paths are placed in a blocked state. If the active path fails, STP dynamically reconfigures the network to use an alternate path.
## Traffic Isolation
Bridges provide a level of traffic isolation between network segments. Devices on one segment typically cannot directly communicate with devices on other segments unless the bridge forwards the traffic between them.
## Broadcast and Multicast Handling
Bridges forward broadcast and multicast frames to all segments except the one from which the frame originated. This allows broadcast messages to reach all devices on a network, as well as multicast groups.
## Transparent Operation
Bridges operate transparently, meaning that devices connected to them are unaware of their presence. Bridges do not assign IP addresses or perform higher-layer (Layer 3) routing functions, which are typically the responsibilities of routers.
