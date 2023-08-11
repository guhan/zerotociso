# Cryptographic Hardware

## Hard Drive Encryption
**Windows**
- Bitlocker
- Encrypting File System (EFS)

**Mac OS X**
- FileVault

**Linux**
- LUKS (Linux Unified Key Setup), which is a widely used disk encryption specification

## Trusted Platform Module
a specialized hardware component that provides security-related functions for the purpose of securing hardware and software through 
integrated cryptographic keys and other security features. TPMs are typically found in modern computers and other devices to enhance 
security by enabling features like secure boot, disk encryption, and more.

Key features and functions of a TPM include:

- **Hardware-based Security**: TPM is a dedicated microcontroller that is separate from the main CPU and memory, making it resistant 
  certain types of software-based attacks.
- **Secure Boot**: TPM can ensure the integrity of the boot process by verifying the digital signatures of boot components, preventing
  unauthorized or malicious software from running during startup.
- **Storage of Encryption Keys**: TPM can securely generate, store, and manage cryptographic keys used for encryption, authentication, and
- digital signatures. These keys are kept within the TPM and are difficult to extract.
- **Disk Encryption**: TPM can be used in combination with software encryption tools (such as BitLocker on Windows or dm-crypt on Linux) to
  provide full-disk encryption. The encryption keys are stored in the TPM, and the drive is unlocked only if the correct platform
  configuration is detected.
- **Remote Attestation**: TPM can generate cryptographic evidence about the state of a system's hardware and software, allowing remote
  parties to verify the system's integrity before establishing a secure communication channel.
- **Secure Storage**: TPM can provide a secure storage area for sensitive data, such as passwords or certificates, offering protection
  against unauthorized access.
- **Password Protection**: TPMs can be used to securely store and manage user authentication credentials, reducing the risk of password
  theft or brute-force attacks.
- **Random Number Generation**: TPMs often include a hardware-based random number generator, which is useful for generating secure cryptographic keys.


## Hardware Security Modules (HSM)
Hardware devices that store and manage encryption keys in a secure manner that prevents humans from ever needing to work 
directly with the keys.HSMs provide a secure environment for generating, storing, and managing cryptographic keys and performing various 
cryptographic operations, such as encryption, decryption, digital signatures, and authentication.

HSMs are used in various industries, including financial institutions, government organizations, healthcare, and more, to ensure the security 
and integrity of sensitive information. 

They offer several benefits, including:

- Key Management: HSMs help organizations generate, store, and manage cryptographic keys securely, reducing the risk of key compromise.
- Encryption and Decryption: HSMs can perform encryption and decryption operations, ensuring that data remains confidential during storage and transmission.
- Digital Signatures: HSMs can create and verify digital signatures, which are crucial for ensuring the authenticity and integrity of digital documents.
- Authentication: HSMs can assist in user and device authentication by securely storing and processing authentication credentials.
- Regulatory Compliance: HSMs often help organizations meet regulatory and compliance requirements by providing a secure platform for cryptographic operations.
- Secure Transactions: In the context of financial institutions, HSMs are commonly used to secure electronic payment transactions and protect sensitive financial data.

