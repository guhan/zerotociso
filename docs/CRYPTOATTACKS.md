# Cryptographic Attacks


## General Types
- **Analytic Attack**: algebraic manipulation that reduces the complexity of the algorithm
- **Implementation Attack**: exploits weaknessness in the implementation of the crypto system
- **Statistical Attack**: exploits statisitical weakness like floating point error or not truly random number
- **Brute Force**: trying every valid combination of a key/password

## Rainbow Tables
Precomputed values for cryptographic hashes. These are compared with the hash desired to crack and then the 
plaintext is revealed. 

## Cryptographic Salt
A random value added to the end of the password before the password is encrypted. The salt is stored in the password
file alongside the hashed/encrypted password. 
- These increase the complexity involved when using a rainbow table

## Frequency Analysis
Counting the number of times each letter appears in the ciphertext and using the knowledge of most commonly
used letters ETAOIN

- **known plaintext**: attacker has a copy of the plain and ciphertext
- **chosen ciphertext**: attacker can decrypt portiions of the ciphertext message and use the decryption position
  to discover the key
- **chosen plaintext**: attacker can encrypt plaintext messages of their choosing
- **Meet in the Middle**: attacker uses a known plaintext message encrypts with all possible keys k1 and then
  decrypts with all possible keys k2. When a match is found the key pair (k1,k2) represents both portions of the double encryption.
- **Man in the Middle**: attacker intercepts all communications between two parties, A and B. Intercepts A's origination requests,
  and setups up a secure connection with A. Then establishes a secure connection with B. Sits in the middle and
  reads all communication.
- **Birthday or Collision**: Uses brute force to find flaws in the 1-1 nature of hashing functions.
- **Replay**: attacks cryptographic algortithms that don't employ temporal protections. An example is captures a
  request for authentication and replays it to open a new session. These can be defeated with a timestamp and expiration
  period on each message. 
