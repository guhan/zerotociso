# Authentication (AuthN)
The process of verifying the identify of a user

## Protocols
- **Challenge Handshake Authentication Protocol (CHAP)**:
  - used in PPP links
  - encrypts usernames and passwords
  - cannot be replayed
  - periodic reauthentication
- **Password Authentication Protocol (PAP)**:
  - transmits usernames and passwords in cleartext

- **Extensible Authentication Protocol (EAP)**:
  - framework instead of actual protocol
- **Protected Extensible Authentication Protocol (PEAP)**: encapsulates EAP in a TLS tunnel
- **OpenID**
- **OAuth**
- **Shibboleth**
