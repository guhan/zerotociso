# Authentication (AuthN)
The process of verifying the identify of a user

## Types
- **Type 1: Something you know**
  - Static Passwords
  - Passphrases
  - One time passwords
  - Dynamic passwords
- **Type 2: Something you have**
  - Syncronous Dynamic Token
  - Asyncronous Dynamic Token
- **Type 3: Something you are**
  - Biometrics
    - False Reject Rate (FRR)
    - False Accept Rate (FAR)
    - Crossover Error Rate (CER) = where FRR is equal to FAR
    - Fingerprints
    - Retina Scan
    - Iris Scan
    - Hand Geometry
    - Keyboard dynamics (key pressure)
    - Dynamic Signature
    - Voiceprint
    - Facial scan
    - **A reference template**: stored sample of a biometric factor
  - **Type 4: Somewhere you are**
    - GPS coordinates
    - Landline
      
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
