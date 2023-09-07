## What is IPSEC?
**Authentication Header (AH)**: AH provides integrity and authentication of IP packets. It verifies that the content of the packet has not been tampered with during transit and confirms the identity of the sender. AH uses cryptographic hash functions to generate a hash-based message authentication code (HMAC) for packet verification.


**Encapsulating Security Payload (ESP)**: ESP provides confidentiality, integrity, and authentication of IP packets. It encrypts the payload of the IP packets to protect the data from eavesdropping. Additionally, ESP can provide integrity checks to ensure data integrity and authentication of the sender.


**Security Associations (SA)**: SAs are established between IPsec peers to define the security parameters and establish a secure communication channel. The parameters include encryption and authentication algorithms, key exchange methods, and security protocols. SAs are identified by Security Parameter Index (SPI) and can be unidirectional or bidirectional.


**Key Management**: IPsec requires the management of cryptographic keys used for encryption, integrity, and authentication. Key management protocols and mechanisms, such as Internet Key Exchange (IKE), are employed to securely negotiate and exchange keys between IPsec peers.


**Tunnel Mode and Transport Mode**: IPsec can be used in two modes: tunnel mode and transport mode. 
- In tunnel mode, the entire IP packet is encapsulated within a new IP packet, adding an additional layer of security.
- In transport mode, only the payload of the original IP packet is encrypted and authenticated, while the IP header remains intact.


**Compatibility and Interoperability**: IPsec is supported by a wide range of network devices, including routers, firewalls, and VPN gateways. It ensures compatibility and interoperability between different vendors' equipment, enabling secure communication across heterogeneous networks.
