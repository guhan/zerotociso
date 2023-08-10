# Cryptography

## Goals of Cryptography
- Confidentiality
- Integrity: enforced through encrypted message digests (or _digital signatures_)
- Authentication
- Nonrepudiation: only works with assymetric encryption

## Key Concepts
- Confusion: the relation ship between the plaintext and the key is so compliated the attacker can't alter the plaintext
  and try to figure out the key
- Diffusion: A change in the plaintext results in multiple changes across the ciphertext

## Kerchoffs Principle
A cryptographic system should be secure even if everything but the keys are public knowledge.

## Caesar Cipher
ROT(3)

Most common letters in English are ETANORISH

## Cryptographic Math
- Boolean: Either 0 (off) or 1 (on)
  - AND all must be true
  - OR only one must be true
  - NOT
  - XOR
- **One way function**: makes impossible to retrieve the inputs for the function
- Nonce: a single use random number

## Zero Knowledge Proofs
Allows one party (the prover) to prove to another party (the verifier) that a certain statement is true without revealing any specific information about the statement itself

Zero-knowledge proofs have several important properties:

- Completeness: If the statement is true, an honest prover can convince the verifier of its truth.
- Soundness: An untrusted prover cannot convince the verifier of a false statement.
- Zero-knowledge: The verifier learns nothing about the underlying information being proved except for the fact that the statement is true.


## Split Knowledge
Dividing sensitive information or knowledge into multiple parts or components and distributing them among different individuals or entities. The goal of split knowledge is to ensure that no single entity has complete access or knowledge of sensitive information, thereby enhancing security and preventing unauthorized access.

**M of N**: Max number M of total people N is required 

## Work Function 
Time and effort required to perform a brute force attack against a cryptographic system

The size of the work function must be just marginally bigger than the data it is trying to protect

## Ciphers

### Transposition Cipher
Transpose plaintext to make ciphertext (apple --> elppa)

### Substitution Cipher
Substitute one character for another 

- Polyalphabetic substition: use multiple alphabets in the same message to hinder decryption efforts

### One time pads (Vernam Cipher)
Use a different substitution alphabet for each letter of the plaintext
- One time pad must be random
- Must be protected against disclosure
- each one time pad must be used only once
- key must be at least as long as the original message


### Running Key (Book Cipher)
Encryption key is as long as message and is often chosen from a common book
  
## What is the difference between a stream and block cipher? 

### Stream Cipher
- Stream ciphers encrypt data bit by bit or byte by byte.
- They generate a stream of pseudorandom bits or bytes, often called the keystream.
- The keystream is combined with the plaintext (or ciphertext) using bitwise operations (usually XOR) to produce the encrypted (or decrypted) output.
- Stream ciphers are typically faster and more suitable for real-time applications or scenarios where data is processed in a continuous stream.
- They can be more vulnerable to certain cryptographic attacks, especially if the keystream is compromised or reused.

### Block Cipher
- Block ciphers encrypt data in fixed-size blocks, typically in chunks of 64 or 128 bits.
- The input plaintext is divided into blocks, and each block is independently encrypted or decrypted using a specific algorithm.
- Block ciphers operate on fixed-size blocks, regardless of the input length. Padding may be required if the plaintext length is not an exact multiple of the block size.
- Popular block cipher algorithms include AES (Advanced Encryption Standard) and DES (Data Encryption Standard).
- Block ciphers are generally considered more secure and are commonly used in cryptographic protocols, disk encryption, and secure communication channels.
- They are slower in real-time applications and require additional modes of operation (such as ECB, CBC, CTR) to handle data that is larger than the block size or to provide security features like encryption chaining and initialization vectors.
