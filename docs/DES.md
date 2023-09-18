# Data Encryption Standard (DES)
Published by US Government in 1977 and is no longer considered secure

- 56 bit key
- 64 bit block cipher (56 bit key + 8 bits for a parity check

## Electronic Code Book Mode (ECB)
  - Simply encrypts the block using the chosen secret key
  - Possible to build a code book as same message generates same ciphertext

## Cipher Block Chaining Mode (CBC)
  - Unencrypted text is XORed with the block of ciphertext _immediate preceding it_ before encrypted with the cipher
  - Errors propagate

## Cipher Feedback Mode (CFM)
  - Streaming version of Cipher Block Chaining (CBC) mode, uses memory buffers of the same block size

## Output Feedback Mode (OFM)
  - Streaming, but first XORs the plaintext with a seed value.
  - An initialization vector is used to create the seed value. 
  - No chaining, _transmission errors do not propagate_

## Counter Mode
  - Stream cipher
  - uses a simple counter instead of a seed value
