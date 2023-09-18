# Hash Function
- Take a long message and generate a unique output derived from the message
- Messages must be identical for hashes to match

## Requirements
- Input can be any length
- Output must be a fixed length
- Relatively easy to computer
- One way function
- Collision free (_not always the case_)

### Secure Hash Algorithm (SHA)
- SHA1: 512bit block, not secure
- SHA256: 512bit block size, 256bit message digest
- SHA224: 512bit block size, 224bit message digest
- SHA512: 1024bit block size, 512bit message digest
- SHA384: turncated verson of SHA-512 1024bit block size to produce a 384bit digest

### Message Digest 2 (MD2)
- made for 8 bit processors
- pads message so it is a multiple of 16 bytes
- adds a 16byte checksum
- uses message and checksum to generate a 128 bit digest

### Message Digest 4 (MD4)
- supported 32bit processors
- pads message to length of 512 bits - 64bits
- 3 rounds of computation
- outputs a 128bit message digest
- issues were found with collisions

### Message Digest 5 (MD5)
- 512 bit bloks of the message
- 4 distinct rounds to get a 128 bit digest
- subject to collisions
