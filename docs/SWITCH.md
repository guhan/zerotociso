# Switch
A switch, in the context of computer networking, is a network device that operates at the Data Link Layer (Layer 2) and sometimes at the Network Layer (Layer 3) of the OSI (Open Systems Interconnection) model. Switches are used to connect multiple network devices within a local area network (LAN) or data center, enabling them to communicate with each other efficiently and intelligently. Unlike hubs, which broadcast data to all connected devices, switches make forwarding decisions based on MAC (Media Access Control) addresses, improving network performance and security.

## Port Connectivity
Switches have multiple ports (ranging from a few to hundreds) into which network cables are plugged. Each port serves as a connection point for a network device, such as computers, printers, servers, or other networking equipment.
## MAC Address Learning
Switches maintain a MAC address table (also known as a forwarding table or CAM table) that maps MAC addresses to the switch ports to which devices are connected. As devices communicate, the switch learns the MAC addresses of devices on its ports and updates the table accordingly.
## Frame Forwarding
When a device sends a data frame to another device within the same LAN, the switch uses its MAC address table to determine the appropriate port to forward the frame. This process is more efficient than broadcasting data to all ports, as done by hubs.
## Collision Domains
Switches create separate collision domains for each of their ports. This means that devices connected to a switch experience fewer collisions and can communicate simultaneously without interfering with one another. This improves network performance compared to hubs.
## Broadcast and Multicast Handling
While switches forward unicast frames only to the appropriate destination, they still broadcast broadcast and multicast frames to all ports to ensure that all devices on the network receive these types of messages.
## VLAN Support
Many switches support Virtual LANs (VLANs), which enable the logical segmentation of a physical network into multiple virtual networks. VLANs can enhance network security and management by isolating traffic and devices.
## Quality of Service (QoS)
Switches can prioritize certain types of network traffic (e.g., voice or video traffic) by implementing QoS policies. This ensures that critical traffic receives the necessary bandwidth and low latency.
## Port Mirroring
Some switches offer port mirroring or port monitoring capabilities, which allow network administrators to monitor traffic on a specific port or set of ports for troubleshooting, analysis, or security purposes.
## Managed and Unmanaged Switches
Switches come in two main categories
managed and unmanaged. Managed switches provide greater control and configurability, including features like VLANs, SNMP (Simple Network Management Protocol) support, and security features. Unmanaged switches are simpler and offer no user configuration.
