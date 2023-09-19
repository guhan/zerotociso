# Extensible Authentication Protocol (EAP)
EAP, which stands for Extensible Authentication Protocol, is a framework for various authentication methods used in network communication. EAP allows network clients and servers to securely exchange authentication credentials and establish a network connection. It is commonly used in wireless networks, virtual private networks (VPNs), and other network security protocols.

- framework instead of actual protocol
- originally designed to run on isolated networks so did not have TLS

## Extensibility
EAP is extensible, meaning it supports a wide range of authentication methods, also known as EAP methods. Different EAP methods can be used to suit various authentication requirements and security levels.
## Flexibility
EAP is highly flexible and can be used in a variety of network protocols, including IEEE 802.1X (for wired and wireless LANs), EAP over LAN (EAPOL), and VPN protocols like L2TP, IPsec, and PPTP.
## Mutual Authentication
EAP enables mutual authentication, ensuring that both the client and the server verify each other's identities before establishing a network connection. This helps prevent unauthorized access.
## Secure Key Exchange
EAP allows for secure key exchange between the client and server, which is essential for encryption and data protection in secure network communications.
## Support for Various Authentication Methods
EAP supports a wide array of authentication methods, including username/password, digital certificates, smart cards, token-based authentication, biometrics, and more. Each EAP method defines how authentication credentials are exchanged and verified.
## Protection Against Eavesdropping
EAP methods can use encryption to protect the authentication process against eavesdropping and man-in-the-middle attacks, ensuring the confidentiality of authentication credentials.
## Challenge-Response Mechanism
Many EAP methods use a challenge-response mechanism, where the server challenges the client with a request, and the client responds with an appropriate authentication credential or proof.


## Some common EAP methods

- **EAP-TLS** (Transport Layer Security): Uses digital certificates for authentication.
- **EAP-PEAP** (Protected Extensible Authentication Protocol): Provides an extra layer of security by encapsulating other EAP methods within a secure tunnel.
- **EAP-MSCHAPv2** (Microsoft Challenge Handshake Authentication Protocol version 2): Often used for username/password-based authentication.
- **EAP-TTLS** (Tunneled Transport Layer Security): Similar to PEAP, it encapsulates other EAP methods within a secure tunnel.

## Wireless LANs
EAP is widely used in securing wireless LANs (WLANs), where it is a fundamental component of the IEEE 802.1X authentication framework. It allows users and devices to securely connect to Wi-Fi networks while ensuring proper authentication and encryption.
