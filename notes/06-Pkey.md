# Public-Key Encryption

## Asymmetric Encryption
- One key is used for encryption (usually publicly known, public key)
- Another key is used for decryption (usually private or secret key)

### Process
1. Alice and Bob agree on a public-key algorithm
2. Alice sends Bob the public key (or key is retrieved from a repository)
3. Bob encrypts a message with Alice's public key and sends it to Alice
4. Alice decrypts Bob's message with the private key

## Components of Public-Key Encryption
- Plaintext
- Encryption algorithm (RSA, ECDSA, DSA, DH)
- Public and private keys
- Ciphertext
- Decryption algorithm

## Advantages and Disadvantages
### Advantages
- All keys (public and private) are generated locally
- No need for key distribution
- Each user can change their own pair of public/private keys at any time

### Disadvantages
- More computationally expensive than symmetric encryption

## Applications of Public-Key Cryptosystems
1. Encryption/decryption: the sender encrypts a message with the recipient's public key
2. Digital signature (authentication): the sender "signs" the message with their private key; a receiver can verify the identity of the sender using the sender's public key
3. Key exchange: both sender and receiver cooperate to exchange a (session) key

## Authentication Using Public-Key Systems
- RSA allows for verification
- Only the private key holder can generate a message that can be decrypted by the public key
- A secure method of authenticating the owner of the private key is the person who sent the message

## Two-Way Secure Communication
1. A encrypts with A's private key and then B's public key
   - Provides authenticity that A's key is the only key pair that can be used to decrypt
   - B's private key is the only key that can unlock the other encryption
2. No one other than the owners of these two private keys could view this message
3. No modification to the message has taken place as it would require the keys

Public-key encryption provides a secure way to communicate and authenticate without the need for key distribution. However, it is more computationally expensive than symmetric encryption and is often used in combination with symmetric encryption for efficient and secure communication.