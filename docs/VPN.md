# Virtual Private Network (VPN)
A VPN, or Virtual Private Network, is a technology that provides a secure and encrypted 
connection between your device and a private network over the internet. It allows you to access 
resources and services as if you were physically present on that private network, even if you're 
connecting from a remote location.

## Types of VPNs:

- **Remote Access VPN**:
Remote access VPNs are used by individuals or employees to connect securely to a company's internal network
from outside locations. This enables remote workers to access resources as if they were in the office.
- **Site-to-Site VPN**:
Site-to-site VPNs connect different physical locations (such as branch offices) of an organization's
network. This allows secure communication between these locations over the internet.

## VPN Protocols
- **Point to Point Tunneling Protocol (PPTP)**:
  - developed from PPP and encapsulates those packets
  - Layer 2
  - same AuthN as PPP
  - intial tunnel negotiation is _not encrypted_
- **Layer 2 Forwarding Protocol (L2F)**:
  - Mutual authentication tunneling mechanism
  - does not offer encryption
  - Layer 2
- **Layer 2 Tunneling Protocol (L2TP)**:
  - lacks built in encryptoin scheme
  - combination of both PPTP and L2F
- [IP Security (IPSEC)](IPSEC.md)
