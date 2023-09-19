# Hub
A hub, in the context of computer networking, is a basic networking device that operates at the [Physical Layer (Layer 1) of the OSI (Open Systems Interconnection) model](OSI.md). Hubs are used to connect multiple network devices, such as computers, printers, or other networking equipment, within a local area network (LAN). 

## Physical Connectivity
Hubs have multiple ports (typically ranging from 4 to 48 ports) into which network cables are plugged. Each port serves as a connection point for a network device.
## Data Broadcasting
When a hub receives data on one port, it broadcasts that data to all other ports, regardless of the destination MAC (Media Access Control) address. This means that all devices connected to the hub receive all network traffic, including data not intended for them.
## Simple Operation
Hubs are simple and inexpensive devices that require little configuration or management. They are essentially plug-and-play devices.
## Collision Domain
All devices connected to a hub are part of the same collision domain. This means that if multiple devices attempt to transmit data simultaneously, collisions can occur, leading to network performance degradation.
## No Intelligence
Hubs do not have any intelligence to make forwarding decisions based on MAC addresses or network traffic. They lack the ability to learn and store MAC address tables like switches do.
## Limited Network Efficiency
Due to their broadcast nature and lack of traffic filtering, hubs are not efficient in managing network traffic. All devices on a hub segment receive all network packets, including those not addressed to them, which can lead to network congestion.


