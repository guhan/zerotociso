# Federal Infomration Processing Standard (FIPS)


## FIPS 140-2
FIPS 140-2, or Federal Information Processing Standard Publication 140-2, 
is a U.S. government standard that specifies security requirements for cryptographic modules.

FIPS 140-2 is published by the National Institute of Standards and Technology (NIST) in the United States and is widely recognized internationally as a benchmark for cryptographic security. The standard defines four levels of security, with each level corresponding to increasing levels of security requirements and assurances. The levels are:

- Level 1: Basic security requirements. Focuses on the use of approved algorithms and basic physical security mechanisms.
- Level 2: Provides increased levels of tamper-evidence and tamper-detection mechanisms to protect against unauthorized access and physical tampering.
- Level 3: Adds further physical security mechanisms to defend against both tampering and bypassing security mechanisms.
- Level 4: The highest level of security, with stringent requirements for physical security mechanisms and protections against environmental attacks.

## FIPS 186-4
Specifies the Digital Signature Algorithm (DSA), which is a widely used asymmetric cryptographic algorithm for generating digital signatures.Digital signatures are essential for ensuring the authenticity, integrity, and non-repudiation of electronic documents and messages

Key aspects covered in FIPS 186-4 include:

- DSA Key Generation: The standard defines the process for generating DSA key pairs, consisting of a private key and a corresponding public key.
- DSA Signature Generation: FIPS 186-4 specifies how to create a digital signature using the private key, based on the DSA algorithm.
- DSA Signature Verification: The standard outlines the steps to verify the authenticity of a digital signature using the corresponding public key.
- Random Number Generation: Secure random number generation is a critical component of cryptographic algorithms. FIPS 186-4 provides guidelines for generating random numbers to be used in DSA key generation and signature operations.
- Parameter Selection: The standard includes recommendations for selecting appropriate parameters for the DSA algorithm, such as prime numbers and other parameters used in the calculations.
- Key Sizes: FIPS 186-4 specifies the key sizes for DSA, which are typically 1024 bits, 2048 bits, or higher.
