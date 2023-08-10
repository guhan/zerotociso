# Cryptography

## Goals of Cryptography
- Confidentiality
- Integrity: enforced through encrypted message digests (or _digital signatures_)
- Authentication
- Nonrepudiation: only works with assymetric encryption

## Key Concepts
- Confusion: the relationship between the plaintext and the key is so complicated the attacker can't alter the plaintext
  and try to figure out the key
- Diffusion: A change in the plaintext results in multiple changes across the ciphertext

### Initialization Vector (IV): 
A fixed-size random or pseudo-random value used in cryptography to initialize certain encryption algorithms and ensure that each message encrypted with the same key produces a different ciphertext. The IV adds an extra layer of security and randomness to encryption processes, especially in situations where the same key is used to encrypt multiple messages.

The primary purposes of an initialization vector are:

- Uniqueness: By using a different IV for each encryption operation, even when using the same key, you can ensure that identical plaintexts will have different ciphertexts. This helps prevent patterns from emerging in the ciphertext that could potentially be exploited by attackers.
- Randomness: The IV introduces an element of randomness, making it more difficult for an attacker to predict the ciphertext produced by a given plaintext.

## Kerchoffs Principle
A cryptographic system should be secure even if everything but the keys are public knowledge.

## Caesar Cipher
ROT(3)

Most common letters in English are ETANORISH

## Cryptographic Math
- **Boolean:** Either 0 (off) or 1 (on)
  - AND all must be true
  - OR only one must be true
  - NOT
  - XOR exclusive or, meaning only one must be true
- **One way function**: makes impossible to retrieve the inputs for the function
- **Nonce:** a single use random number

## Zero Knowledge Proofs
Allows one party (the prover) to prove to another party (the verifier) that a certain statement is true without revealing any specific information about the statement itself

Zero-knowledge proofs have several important properties:

- **Completeness:** If the statement is true, an honest prover can convince the verifier of its truth.
- **Soundness:** An untrusted prover cannot convince the verifier of a false statement.
- **Zero-knowledge:** The verifier learns nothing about the underlying information being proved except for the fact that the statement is true.


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

### Polyalphabetic substition
Polyalphabetic substitution is a cryptographic technique used to encrypt plaintext by _substituting letters with multiple sets of cipher letters_, based on a keyword or keyphrase. This method provides a higher level of security compared to simple monoalphabetic substitution ciphers, where each letter is replaced with a single fixed cipher letter.

In a polyalphabetic substitution cipher:

- Keyword or Keyphrase: A keyword or keyphrase is chosen, and its letters determine the number of alphabets used in the substitution. For example, if the keyword is "KEY," there would be three different alphabets: one shifted by "K," one shifted by "E," and one shifted by "Y."
- Multiple Alphabets: Each alphabet is a shifted version of the standard alphabet. The first alphabet is not shifted (shift value 0), the second alphabet is shifted by the numerical position of the first letter of the keyword in the alphabet, the third alphabet is shifted by the second letter's position, and so on.
- Encryption: To encrypt a message, each letter of the plaintext is substituted with the corresponding letter from the appropriate alphabet based on the keyword. Non-alphabetic characters (such as punctuation and spaces) are usually left unchanged.
- Decryption: Decryption involves reversing the process. Each letter of the ciphertext is replaced with the corresponding letter from the appropriate alphabet, based on the keyword.
- Polyalphabetic substitution ciphers are more secure than monoalphabetic substitution ciphers because they introduce variability and complexity into the encryption process. They make frequency analysis (a common method of breaking monoalphabetic ciphers) more difficult, as the same plaintext letter can be encrypted differently based on its position in the message and the keyword.

One well-known example of a polyalphabetic substitution cipher is the **Vigenère cipher**, where the keyword determines the shift for each letter in the plaintext.
use multiple alphabets in the same message to hinder decryption efforts

### One time pads (Vernam Cipher)
Use a different substitution alphabet for each letter of the plaintext
- One time pad must be random
- Must be protected against disclosure
- Each one time pad must be used only once
- Key must be at least as long as the original message


### Running Key (Book Cipher)
Encryption key is as long as message and is often chosen from a common book
  
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



## Symmetric Key Encryption
Same secret key is used to encrypt and decrypt the data

#### Problems: 
- Key distribution is a problem
- does not allow for nonrepudiation
- algorihgm is not scalable to large groups (each pair of people needs one)
- key must be regenerated often

#### Best practices:
- Offline distibution
- **Never store the encryption key on the same system that the data resides**

#### Algos, block and keysize  

|Algo|Block Size|Key Size|
|----|----------|--------|
|AES| 128|128,192,256|
|Rijndael|Variable|128,192,256|
|Blowfish|64|32-448|
|DES|64|56|
|IDEA|64|128|
|Rivest Cipher 2|64|128|
|Rivest Cipher 5|32,64,128|0-2040|
|Skipjack|64|80|
|3DES|64|112 or 168|
|Twofish|128|1-256|


### Data Encryption Standard (DES)
Published by US Government in 1977 and is no longer considered secure

- 56 bit key
- 64 bit block cipher (56 bit key + 8 bits for a parity check

- **Electronic Code Book Mode (ECB)**
  Simply encrypts the block using the chosen secret key
  Possible to build a code book as same message generates same ciphertext

- **Cipher Block Chaining Mode (CBC)**
  Unencrypted text is XORed with the block of ciphertext _immediate preceding it_ before encrypted with the cipher
  Errors propagate

- **Cipher Feedback Mode (CFM)**
  Streaming version of Cipher Block Chaining (CBC) mode, uses memory buffers of the same block size

- **Output Feedback Mode (OFM)**
  Streaming, but first XORs the plaintext with a seed value. An initialization vector is used to create the seed value. 
  No chaining, transmission errors do not propagate

- **Counter Mode**
  Stream cipher, uses a simple counter instead of a seed value

### Triple DES (3DES)
Run DES multiple times

Has a few different variants and all are as secure: 

- Encrypt 3 times
- Encrypt Decrypt and Encrypt
- Encrypt with only 2 keys
- Encrypt with only 2 keys and use a decryption in the middle

### International Data Encryption Algorithm (IDEA)
Starts with a 128 bit key, split into 52 16bit sub keys

### Blowfish
Operates on 64bit blocks of text, uses variable length keys from 32bits to 448 bits

### Skipjack
Approved for FIPS 185
Operates on 64 bit blocks of text, and uses and 80 bit key

### Rivest 5 (RC5)
block sizes 32,64, or 128
key sizes 0 to 2040

### Advanced Encryption Standard (AES)
block size is 128
- 128 bit keys with 10 rounds of encryption
- 192 bit key with 12 rounds of encryption
- 256 bit key with 14 rounds of encryption

### Twofish
block size is 128
key size is 256 bits 
- **Prewhitening**: XORing the plaintext with a separate subkey before first round
- **Postwhitening**: similar operation after 16th round



## Assymetric Key Encryption
Public and Private Key

## Diffie Hellman
When parties have no way to exchange a secret key and no PKI
1. Richard and Sue agree on two large numbers, p (prime) and g (int) 1 < g < p
2. Richard choses a random int r and does
   R= g^r mod p
3. Sue chooses a random large int s
   S = g^s mod p
4. Richards sends R to Sue and Sue sends S to Richard
5. Richard them performs
   K = S^r mod p
6. Sue performs
   K= R^s mod p


## Key Escrow
- Fair Cryptosystems: secret keys are divided and given to an independent third party
- Escrowed Encryption Standard: Gives the government a way to decrypt ciphertext
