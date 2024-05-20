# Symmetric Cryptography: Part 2

## Block Cipher Modes
Block ciphers may be used in different modes. The most common modes are:
1. Electronic Codebook Mode (ECB)
2. Cipher Block Chaining (CBC)
3. Cipher Feedback Mode (CFB)

### Electronic Codebook Mode (ECB)
- Simple mode: each block (e.g., 64 bits) is encrypted with the same key
- For a given block of plaintext and key, the result of encryption is unique
- If a block of plaintext is repeated several times, the ciphertext contains several copies of the same encrypted block
- Encryption of lengthy (regular) messages might be insecure

### Cipher Block Chaining Mode (CBC)
- Fixes the disadvantage of ECB mode: the same blocks of plaintext may produce different blocks of ciphertext
- Before encryption, a block of plaintext is XOR'ed with the result of encryption of the previous block
- For the first block encryption, an initialization vector (IV) is used
- It is better to keep both the key and IV secret
- CBC encryption and decryption processes involve XOR operations and block cipher encryption/decryption

### Cipher Feedback Mode (CFB)
- Transforms a block cipher into a stream cipher
- Has a parameter s (the size of the transmission unit), e.g., s = 8 for 8-bit characters
- Uses a shift register with a size equal to the block size of the block cipher (typically 64 bits)
- Requires an initialization vector (IV)
- CFB encryption and decryption processes involve XOR operations, block cipher encryption, and shift register operations

## Key Distribution

### Manual Key Delivery
- For two parties A and B:
  - A key could be created by A and delivered physically to B (or vice versa)
  - A key could be created by a third trusted party C and delivered physically to A and B
- Difficult to use in wide area distributed systems when dynamic connections are needed

### Automated Key Distribution
- Involves key distribution centers (KDCs) or key translation centers (KTCs)
- KDC generates keys and distributes them securely to the communicating parties
- KTC receives keys from one party, encrypts them with the key of the other party, and sends the encrypted keys to the other party
- Requires secure channels between the KDC/KTC and the communicating parties

Proper key management is essential for the security of symmetric encryption systems. Key distribution, storage, and updates should be performed securely to maintain the confidentiality and integrity of the encrypted data.