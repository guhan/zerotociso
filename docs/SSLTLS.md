# SSL/TLS

## What Is SSL encryption?
SSL (Secure Sockets Layer) encryption, also commonly referred to as TLS (Transport Layer Security) encryption, is a cryptographic protocol used to secure communication over a network

- **Handshake**: The SSL/TLS handshake is the initial process where the client and server establish a secure connection. During the handshake, they negotiate encryption algorithms, exchange cryptographic keys, and verify the authenticity of each other's identity (through digital certificates).


- **Encryption**: Once the secure connection is established, SSL/TLS encryption is applied to protect the data transmitted between the client and server. Encryption algorithms, such as symmetric encryption (e.g., AES) and asymmetric encryption (e.g., RSA), are used to encrypt and decrypt data. This ensures that even if intercepted, the data is unreadable without the appropriate decryption keys.


- **Data Integrity**: SSL/TLS also provides data integrity, which means that the data sent between the client and server cannot be altered or tampered with during transit. This is achieved through the use of cryptographic hash functions, such as SHA (Secure Hash Algorithm), which generate unique checksums for the data. These checksums are used to verify the integrity of the received data.


- **Authentication**: SSL/TLS supports server authentication, where the server presents a digital certificate to prove its identity to the client. The certificate is issued by a trusted Certificate Authority (CA) and contains the server's public key. The client verifies the certificate to ensure it is valid and issued by a trusted source, establishing trust in the server's identity.


- **Mutual Authentication** (Optional): SSL/TLS can also support mutual authentication, where both the client and server authenticate each other. In this scenario, the client presents its own digital certificate to the server, allowing the server to verify the client's identity.

## What is the difference between SSL and TLS?

- TLS is the recommended protocol for securing internet communication. TLS provides stronger encryption algorithms, improved key exchange mechanisms, and enhanced security features compared to SSL. 

- TLS 1.0 was introduced as the successor to SSL 3.0, followed by TLS 1.1, TLS 1.2, and TLS 1.3, each providing improved security features and performance enhancements.



## How does a client check a servers SSL certificate?

- **Certificate Validation**: The client receives the SSL certificate from the server during the SSL/TLS handshake process. The certificate contains the server's public key, server information, and is digitally signed by a trusted Certificate Authority (CA).


- **Certificate Chain**: The client checks the certificate chain to establish trust. This involves verifying the authenticity and validity of each certificate in the chain. The chain typically includes the server's SSL certificate, intermediate certificates (if any), and the root certificate.


- **Root Certificate Verification**: The client has a list of trusted root certificates stored in its certificate store or trusted certificate authorities. It verifies if the root certificate that signed the server's SSL certificate is present in this list. If the root certificate is not trusted or missing, the client may display a warning or reject the connection.


- **Certificate Expiry and Revocation**: The client checks the expiration date mentioned in the SSL certificate to ensure it is not expired. It also checks for certificate revocation by verifying if the certificate has been revoked by the issuing CA. This is done by checking Certificate Revocation Lists (CRLs) or using Online Certificate Status Protocol (OCSP) services.


- **Hostname Verification**: The client verifies that the common name (CN) or subject alternative names (SANs) in the certificate match the hostname to which the client is connecting. This ensures that the server's certificate is issued for the correct domain or server.


- **Certificate Integrity**: The client verifies the integrity of the certificate by checking the digital signature. It uses the public key of the issuing CA to validate the signature and ensure that the certificate has not been tampered with or modified.


## How does the SSL/TLS handshake work?

1. Client Hello: The client initiates the handshake by sending a Client Hello message to the server. This message contains information such as the SSL/TLS version supported by the client, a random value (Client Random), and a list of supported cipher suites and compression methods.
2. Server Hello: Upon receiving the Client Hello, the server responds with a Server Hello message. This message includes the SSL/TLS version selected by the server, a random value (Server Random), the chosen cipher suite, and the server's digital certificate (if required).
3. Certificate Exchange: If the server's certificate is required for authentication, it sends its digital certificate to the client. The certificate contains the server's public key, identity information, and is signed by a trusted Certificate Authority (CA).
4. Client Key Exchange: The client generates a pre-master secret and encrypts it with the server's public key from the received certificate. The encrypted pre-master secret is sent to the server, ensuring that only the server can decrypt it with its private key.
5. Server Key Exchange (optional): In some cases, the server may send additional information or parameters required for the key exchange, such as Diffie-Hellman parameters or a server key exchange message.
6. Certificate Verification: The client verifies the authenticity and validity of the server's certificate. It checks the digital signature, expiration date, and checks if the certificate has been revoked or issued by a trusted CA. If the verification fails, the client may display a warning or terminate the connection.
7. Pre-Master Secret Derivation: Both the client and server independently compute the pre-master secret using the exchanged keys. This pre-master secret is used to generate the session keys required for encryption and decryption.
8. Session Key Generation: Using the pre-master secret, the client and server independently generate the session keys used for symmetric encryption and decryption during the secure communication.
9. Handshake Completion: Finally, both the client and server send a Finished message, which includes a hash of all the exchanged messages during the handshake. This allows both parties to verify the integrity of the handshake and ensure that the communication parameters match.
