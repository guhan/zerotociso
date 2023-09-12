## What is IPSEC?
**Authentication Header (AH)**: AH provides integrity and authentication of IP packets. It verifies that the content of the packet has not been tampered with during transit and confirms the identity of the sender. AH uses cryptographic hash functions to generate a hash-based message authentication code (HMAC) for packet verification.


**Encapsulating Security Payload (ESP)**: ESP provides confidentiality, integrity, and authentication of IP packets. It encrypts the payload of the IP packets to protect the data from eavesdropping. Additionally, ESP can provide integrity checks to ensure data integrity and authentication of the sender.


**Security Associations (SA)**: SAs are established between IPsec peers to define the security parameters and establish a secure communication channel. The parameters include encryption and authentication algorithms, key exchange methods, and security protocols. SAs are identified by Security Parameter Index (SPI) and can be unidirectional or bidirectional.


**Key Management**: IPsec requires the management of cryptographic keys used for encryption, integrity, and authentication. Key management protocols and mechanisms, such as Internet Key Exchange (IKE), are employed to securely negotiate and exchange keys between IPsec peers.


**Tunnel Mode and Transport Mode**: IPsec can be used in two modes: tunnel mode and transport mode. 
- In tunnel mode, the entire IP packet is encapsulated within a new IP packet, adding an additional layer of security.
- In transport mode, only the payload of the original IP packet is encrypted and authenticated, while the IP header remains intact.


**Compatibility and Interoperability**: IPsec is supported by a wide range of network devices, including routers, firewalls, and VPN gateways. It ensures compatibility and interoperability between different vendors' equipment, enabling secure communication across heterogeneous networks.


## What is Internet Key Exchange (IKE)?
Internet Key Exchange (IKE) is a protocol used in Virtual Private Network (VPN) and IPsec (Internet Protocol Security) implementations to establish secure communication channels between two devices, such as routers, firewalls, or VPN gateways. The primary purpose of IKE is to facilitate the negotiation and exchange of cryptographic keys and security parameters required for secure data transmission over an untrusted network, such as the internet.

IKE performs several essential functions in VPN and IPsec implementations:

- **Authentication**: IKE ensures that both parties involved in the communication are who they claim to be. It supports various authentication methods, including pre-shared keys (PSKs), digital certificates, and Extensible Authentication Protocol (EAP).
- **Key Exchange**: IKE is responsible for securely exchanging cryptographic keys between the communicating devices. These keys are used for encryption and authentication of data exchanged between the devices.
- **Security Association (SA) Establishment**: IKE establishes Security Associations, which are sets of security parameters like encryption algorithms, integrity algorithms, and security protocols that define how data should be protected during communication.
- **Negotiation**: IKE enables the negotiating devices to agree on common encryption and authentication methods and algorithms. This negotiation ensures that both parties can communicate securely using a mutually acceptable configuration.
- **Perfect Forward Secrecy (PFS)**: PFS is a feature in IKE that ensures that even if one set of keys is compromised, past and future communications remain secure. PFS is achieved by regularly renegotiating session keys.

IKE operates in two phases:

- **IKE Phase 1**: In this phase, IKE establishes a secure channel between the two devices, typically by authenticating each other using either pre-shared keys or digital certificates. IKE Phase 1 also negotiates encryption and authentication methods and creates a secure shared secret called the "shared key" or "Diffie-Hellman key." This key is used in Phase 2 to establish the actual IPsec Security Associations.
- **IKE Phase 2**: Phase 2 establishes the IPsec Security Associations (SAs) for data transmission. It negotiates the security parameters for the data packets, such as encryption algorithms, integrity algorithms, and other parameters required for secure communication.

## What is Internet Security Association and Key Management Protocol (ISAKMP)?
Provies background security support for IPSEC by negotiating, establishing, modifying and deleting Security Associations (SAs)
