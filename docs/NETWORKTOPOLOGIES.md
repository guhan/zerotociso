# Network Topologies

![Network Toplogies](/images/network_topology.jpg)

## Ring
In a ring topology, devices are connected in a closed loop. Each device is connected to exactly two other 
devices, creating a circular pathway for data. Failure of one device can disrupt the entire network.

## Bus
In a bus topology, all devices are connected to a single central cable (the "bus"). Devices receive data 
intended for them and ignore data intended for others. A break in the cable can disrupt the entire network.

## Star
In a star topology, all devices are connected to a central hub or switch. Communication between devices goes 
through the hub. If one device fails, it doesn't affect the rest of the network, but the hub itself 
becomes a single point of failure.

## Mesh
Mesh topologies involve every device being connected to every other device in the network. Full mesh and 
partial mesh are two variations. Full mesh offers high redundancy but can be expensive and complex to 
implement.

## Tree (Hierarchical) Topology:
Tree topologies combine multiple star topologies connected in a hierarchical manner. This offers 
scalability but can be vulnerable to the failure of the central hub connecting the star segments.

## Hybrid Topology:
Hybrid topologies combine two or more different topologies. For example, a star-bus hybrid might 
have multiple star-configured networks connected via a bus.

## Point-to-Point Topology:
Point-to-point topology involves a direct connection between two devices, such as a dedicated link 
between routers or a computer and a printer.

## Daisy Chain Topology:
In a daisy chain topology, devices are connected in sequence, one after the other. Data flows 
sequentially from one device to the next. A failure in any device can disrupt the entire chain.
