# Symmetric Cryptography: Part 1

## Cryptography
- A collection of mathematical techniques for protecting information
- Encryption/decryption is the most important cryptographic technique

## Cryptography for Information Protection
- Encryption is used directly at the level of communication channels
- Encryption is also an important ingredient at the levels of message authentication and secure communication protocols

## Two Categories of Encryption Algorithms
1. Symmetric encryption (symmetric key encryption):
   - The same key is used to encrypt and decrypt a message
2. Asymmetric encryption (asymmetric key encryption):
   - One key (public key) is used for encryption
   - Another key (private or secret key) is used for decryption

## Components of Symmetric Encryption
- Plaintext
- Encryption algorithm
- Secret key
- Ciphertext (encrypted text)
- Decryption algorithm

## Security of Symmetric Encryption
- Security depends on the secrecy of the key, not the secrecy of the algorithm
- Producing keys is easier than inventing and keeping new algorithms secret

## Requirements for Symmetric Encryption
- Strong encryption algorithm: adversary should be unable to decrypt ciphertext even if they know several (plaintext, ciphertext) pairs
- Secure key distribution and management between sender and receiver

## Classifications of Cryptosystems
1. Type of operations used:
   - Substitutions
   - Transpositions
2. The way in which plaintext is processed:
   - Block cipher: input block of elements is transformed to output block at once
   - Stream cipher: processes input elements continuously, one element at a time

## Classics: Substitutions and Transpositions
- Substitutions: each element of plaintext is mapped to another element
- Transpositions: rearrangement of letters in plaintext to create ciphertext

## Cryptanalysis and Computationally Secure Schemes
- Cryptanalysis: the process of attempting to discover plaintext or key
- An encryption scheme is computationally secure if:
  - The cost of breaking the scheme exceeds the value of encrypted information
  - The time required to break the scheme is more than the lifetime of information

## Types of Attacks (Cryptanalysis)
- Depends on the information known to the attacker

## Brute-Force Approach in Cryptanalysis
- Try every possible key until correct translation of ciphertext into plaintext is obtained
- Main issue: time required for brute-force search

## Block vs. Stream Ciphers
- Block cipher: input blocks of elements are transformed to output blocks all at once
- Stream cipher: processes input elements continuously, one element at a time

## Feistel Cipher
- Structure used by most symmetric block algorithms
- Input is divided into blocks of even numbers of elements
- Multiple stages of substitutions and transpositions are applied
- Multiple keys (derived from a master key) are used at various rounds

## Symmetric Encryption Algorithms
- DES (Data Encryption Standard)
- 3DES (Triple DES)
- AES (Advanced Encryption Standard)

## AES (Advanced Encryption Standard)
- Designers: J. Daemen, Vincent Rijmen
- Key size: 128, 192, or 256 bits
- Number of rounds: 10, 12, or 14
- Steps in each round: Substitution, ShiftRows, MixColumns, AddRoundKey
- Considered secure for classified information, but some concerns exist regarding its algebraic foundations and side-channel attacks.