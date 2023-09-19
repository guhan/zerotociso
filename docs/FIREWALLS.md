# Firewalls
Essential tools for managing and controlling network traffic. Filter traffic based on a defined set of rules. 

## Types
- **Static Packet Filtering**: examines header and filters
- **Application Level Gateway**:
  - filters traffic based on the application used to transmit or receive the data
  - group of reverse proxies that filter traffic and forward to specific ports
- **Circuit Level Gateway**:
  - Layer 5 OSI
  - Establish communication between trusted partners
  - Permit and deny based on endpoint designation
- **Stateful Inspection**: examining state and context of network traffic
- **Deep Packet Inspection**: examines the payload as well as the header and works on the application level
- **Next Gen**: has additional components like IDS, IPS, TLS proxy, web filtering, QoS Management, rate limiting,
  NAT, VPN anchoring and antivirus.
- **Multihomed**: more than one interface


## Tiers
![Tiers](/images/FIREWALLTIERS.png)


