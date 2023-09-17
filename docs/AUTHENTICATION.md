# Authentication (AuthN)
The process of verifying the identify of a user


## Key Terms
- **Identity proofing**: Identity proofing, also known as identity verification or identity authentication, is the process of confirming and validating the identity of an individual, typically before granting them access to certain resources, services, or systems.
  
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

- **Password Authentication Protocol (PAP)**:
  - transmits usernames and passwords in cleartext


- **Protected Extensible Authentication Protocol (PEAP)**: encapsulates EAP in a TLS tunnel
- **OpenID**
- **OAuth**
- **Shibboleth**
