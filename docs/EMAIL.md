# Email

## Ports
- 25: SMTP
- 143: IMAP

## S/MIME
S/MIME, which stands for Secure/Multipurpose Internet Mail Extensions, is a widely used 
protocol for securing email communications through the use of encryption and digital signatures. 
S/MIME enhances the security and privacy of email messages, ensuring that they remain confidential 
and authentic during transmission.

S/MIME provides two main features:

- **Encryption**:
S/MIME encryption ensures that the content of an email message is only readable by its intended recipient.
When an email is encrypted using S/MIME, it is transformed into ciphertext that can only be decrypted
by the recipient's private key. This prevents unauthorized individuals or entities, including
cybercriminals and eavesdroppers, from reading the message's content while it's in transit.
- **Digital Signatures**:
S/MIME digital signatures provide a way to verify the authenticity and integrity of an email message.
When an email is digitally signed using S/MIME, the sender's digital signature is attached to the
message. This signature is created using the sender's private key and can be verified using the
sender's corresponding public key. A valid digital signature indicates that the message has not
been tampered with and was indeed sent by the claimed sender.

The S/MIME protocol relies on Public Key Infrastructure (PKI) technology to manage the cryptographic 
keys used for encryption and digital signatures. 

Here's how S/MIME works:

- **Key Generation**: Each user generates a pair of cryptographic keys: a private key and a
  corresponding public key.
- **Digital Signature**: When a user sends an email, they can sign the message with their
  private key, creating a digital signature.
- **Encryption**: If the user wants to send a confidential email, they can encrypt the message
  using the recipient's public key. Only the recipient, who has the corresponding private key,
  can decrypt and read the message.
- **Verification**: Upon receiving a digitally signed email, the recipient can use the
  sender's public key to verify the signature and ensure that the message hasn't been altered.
- **Decryption**: If the recipient receives an encrypted email, they can use their private key
  to decrypt the message and read its content.

## TLS for SMTP
TLS (Transport Layer Security) for SMTP (Simple Mail Transfer Protocol) is a security protocol 
that provides encryption and authentication for email communication between email servers. It 
ensures that the data transmitted between the sending and receiving email servers is secure and 
protected from eavesdropping and tampering. TLS for SMTP is commonly referred to as "SMTP over 
TLS" or "SMTPS."

SMTP is the standard protocol used for sending and receiving email messages between email servers. 
However, without encryption, the content of email messages can be intercepted and read by 
unauthorized individuals or entities as it traverses the internet. TLS addresses this security 
concern by encrypting the communication channel between the sending and receiving servers.

Here's how TLS works for SMTP:

- **Negotiation**: When an email server wants to establish a secure connection with another
  server, it initiates a TLS negotiation process. The initiating server indicates its support for
  TLS through an SMTP command.
- **Handshake**: The receiving server responds with a "220 Ready to start TLS" message if it
  supports TLS. The servers then perform a TLS handshake, during which they agree on encryption
  methods, exchange digital certificates, and establish a secure encrypted channel.
- **Secure Channel**: Once the TLS handshake is completed successfully, the SMTP communication
  takes place over a secure encrypted channel. This means that the email content and other data
  are protected from interception and tampering while in transit between the servers.
- **Certificate Verification**: During the TLS handshake, the servers exchange digital certificates
  to establish trust. The receiving server verifies the authenticity of the sender's certificate,
  ensuring that it matches the domain and has not been tampered with.

TLS for SMTP provides several benefits:

- **Confidentiality**: Encrypting email communication ensures that the content of messages
  cannot be intercepted by unauthorized parties during transmission.
- **Integrity**: TLS protects email messages from being tampered with or altered while in transit.
- **Authentication**: Digital certificates used in the TLS handshake help authenticate the
  identity of the email servers, reducing the risk of man-in-the-middle attacks.
- **Compliance**: Many regulations and standards require secure email communication, and TLS
  helps organizations meet these compliance requirements.
- **Data Protection**: TLS is an essential component of data protection strategies,
  especially for sensitive and confidential information.

### What ports does SMTP use for TLS?
SMTP (Simple Mail Transfer Protocol) typically uses port 25 for communication between email servers. 
However, when SMTP communication is secured using TLS (Transport Layer Security), it operates over a 
different port to ensure encrypted transmission. The port commonly used for SMTP with TLS is:

**Port 587**: This is the default port for the submission of outgoing email messages by email clients to 
their email server. It's often referred to as the "submission" port and is specifically designed for 
client-to-server communication using SMTP with TLS. Port 587 is used to send email messages from users' 
devices to the email server, and TLS encryption ensures that the data remains secure during transmission.

It's worth noting that SMTP communication can also be secured using TLS on the traditional port 25, 
which is used for server-to-server communication. However, this approach is becoming less common due to 
the risks associated with opportunistic TLS encryption on port 25.

When using port 587 for SMTP with TLS, the following process generally occurs:

1. The email client establishes a connection to the email server on port 587.
2. The client initiates a TLS handshake with the server.
3. The server responds and provides its digital certificate to the client for verification.
4. The client verifies the server's certificate and, if successful, the TLS-encrypted communication
   channel is established.
5. The email client then sends the email message over the secure TLS connection.

This process ensures that the content of the email message is encrypted during transmission between the email client and the server. This is particularly important when sending sensitive or confidential information over email.

