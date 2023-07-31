# Cryptography

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
