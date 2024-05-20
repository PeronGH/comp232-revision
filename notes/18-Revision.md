# Revision Outline

## Part 1: Identification and Authentication

1. Passwords
   - Advantages and disadvantages
   - Password-based authentication techniques
   - Problems with passwords (weak passwords, password reuse, social engineering, etc.)
2. Tokens
   - Token-based authentication
   - Types of tokens (memory cards, smart cards, one-time password generators, etc.)
   - Advantages and disadvantages of tokens
3. Biometrics
   - Biometrics-based authentication techniques
   - Types of biometrics (fingerprints, facial recognition, iris scans, etc.)
   - Advantages and disadvantages of biometrics
4. Multifactor Authentication
   - Combining multiple authentication factors (e.g., password + token)
   - Benefits and challenges of multifactor authentication

## Part 2: Cryptography

1. Symmetric Encryption
   - DES (Data Encryption Standard)
     - Key generation, encryption, and decryption process
     - Advantages and disadvantages of DES
   - AES (Advanced Encryption Standard)
     - Key sizes, number of rounds, and structure of AES
     - Advantages and disadvantages of AES
   - Modes for Block Ciphers
     - ECB (Electronic Codebook), CBC (Cipher Block Chaining), CFB (Cipher Feedback) modes
     - Advantages and disadvantages of each mode
2. Asymmetric/Public Key Encryption
   - RSA (Rivest-Shamir-Adleman) algorithm
     - Key generation, encryption, and decryption process
     - Advantages and disadvantages of RSA
3. Key Exchange
   - Diffie-Hellman (DH) key exchange protocol
     - Key exchange process and mathematical principles
     - Advantages and disadvantages of DH key exchange
4. Message Authentication and Hash Functions
   - Message Authentication Codes (MACs)
     - MAC generation and verification process
     - Advantages and disadvantages of MACs
   - Hash Functions
     - Properties of hash functions (one-way, collision-resistant, etc.)
     - Examples of hash functions (SHA-1, SHA-2, etc.)
5. Quantum Cryptography
   - Principles of quantum cryptography
   - BB84 protocol for quantum key distribution
   - Advantages and challenges of quantum cryptography
6. Advanced Cryptography
   - Fully Homomorphic Encryption (FHE)
     - Computing over encrypted data
     - Applications and challenges of FHE
   - Zero-Knowledge Proofs (ZKP)
     - Interactive and non-interactive ZKPs
     - Applications and challenges of ZKPs
   - Secure Multiparty Computations (SMPC)
     - Yao's protocol for secure two-party computation
     - Applications and challenges of SMPC
7. Steganography
   - Hiding information within digital files (text, images, audio, video)
   - Techniques for steganography (LSB substitution, stochastic modulation, etc.)
   - Advantages and disadvantages of steganography

## Part 3: Security Protocols and Their Analysis

1. Needham-Schroeder (NS) Authentication Protocol
   - Protocol description and message exchange
   - Man-in-the-middle attack on the NS protocol
   - Protection against the attack
2. Formal Methods for Protocol Analysis
   - Model checking
     - Representing protocols as transition systems
     - Expressing properties using temporal logic
     - Advantages and limitations of model checking
   - Theorem proving
     - Representing protocols and properties using logic
     - Proving the correctness of protocols
     - Advantages and limitations of theorem proving

## Part 4: Monitoring and Intrusion Detection

1. Audit and Intrusion Detection
   - Audit data collection and storage
   - Intrusion Detection Systems (IDS)
     - Types of IDS (network-based, host-based, application-based)
     - Advantages and limitations of IDS
2. IDS Techniques
   - Statistical analysis
   - Neural networks and machine learning
   - Rule-based and signature-based techniques
   - State-transition analysis
   - Immune system-based techniques
   - Data mining
3. Firewalls
   - Types of firewalls (packet-filtering, circuit-level gateways, application-level gateways)
   - Firewall characteristics and limitations
   - Next-generation firewall requirements

## Part 5: Attacks and Defenses

1. Malware
   - Types of malware (viruses, worms, Trojan horses, logic bombs, etc.)
   - Propagation and infection mechanisms
   - Examples of notable malware (Morris worm, Melissa virus, Stuxnet, etc.)
2. Anti-Virus and Anti-Worm Methods
   - Generations of antivirus software (scanners, heuristic analyzers, activity traps, etc.)
   - Techniques for virus detection and removal
   - Worm monitoring and detection systems
   - Behavioral blocking and generic decryption
3. Insertion Attacks and Countermeasures
   - SQL injection attacks and countermeasures
   - Cross-Site Scripting (XSS) attacks and countermeasures

## Tips

For each topic, consider the following questions:

- What are the key concepts, techniques, or algorithms involved?
- How do they work, and what are their strengths and weaknesses?
- Why are they important in the context of cybersecurity?

Additionally, for topics that involve comparing different solutions or approaches, discuss the advantages and disadvantages of each from the perspectives of security, efficiency, and practicality.

Remember to be precise and concise in your responses, focusing on the essential information for each topic.