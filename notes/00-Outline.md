## COMP232 Cybersecurity Outline

**I. Introduction & Foundational Concepts**

* Cybersecurity: Definition, Scope & Importance
* Security in Cyberspace & Privacy
* Cost & Global Impact of Cybersecurity
* Jobs in Cybersecurity
* What Hackers Do with Stolen Information
* Security Architecture for OSI
  * Security Attacks (Passive & Active)
    * Examples: Interruption, Interception, Modification, Fabrication
  * Security Services & Attributes
    * Authentication, Access Control, Data Confidentiality, Data Integrity, Nonrepudiation, Availability
  * Security Mechanisms
    * Encipherment, Digital Signature, Access Control, Data Integrity, Authentication Exchange, Traffic Padding, Routing Control, Notarisation

**II.  Identification & Authentication**

* Identification, Authentication & Authorization
* User vs. Machine Authentication
* Authentication Techniques
  * Password-Based Techniques (Strengths & Weaknesses)
  * Token-Based Authentication (Types & Problems)
  * Multi-factor Authentication
  * Biometrics-Based Techniques (Definition, Applications & Problems)
    * Multi-modal Biometric Architecture
    * Authentication by Brainwaves

**III. Cryptography**

* **Symmetric Encryption** 
  * Definition, Components & Requirements
  * Substitution & Transposition Ciphers
    * Examples: Rail Fence Cipher
  * Cryptanalysis & Computationally Secure Schemes
    * Types of Attacks: Brute-Force Approach
  * Block vs. Stream Ciphers
  * Feistel Cipher Structure & Decryption
    * Factors in Cipher Design: Block Size, Key Size, Number of Rounds, Subkey Generation, Round Function
  * Algorithms: DES, 3DES, AES (Strengths & Weaknesses)
  * Block Cipher Modes: ECB, CBC, CFB (Descriptions & Applications)
  * Key Distribution
    * Manual vs. Automated Techniques

* **Public-Key (Asymmetric) Encryption**
  * Definition, Components & Applications
    * Encryption/Decryption, Digital Signature, Key Exchange
  * Authentication using Public-Key Systems

* **Algorithms**
  * RSA
    * Encryption & Decryption
    * Key Generation
    * Mathematical Foundations: Fermat-Euler Theorem, Chinese Remainder Theorem
    * Security Analysis & Attacks
    * RSA Challenge & Recent News
    * Applications & Standards: PKCS 2.2
  * Diffie-Hellman Key Exchange
    * Discrete Logarithms
    * Key Generation & Exchange Process
    * Security Analysis

* **Message Authentication & Hash Functions**
  * Message Authentication Techniques
    * Using Conventional Encryption
    * Using Authentication Tags
  * Message Authentication Codes (MAC)
    * MAC Algorithms & Properties
  * One-Way Hash Functions
    * Definition & Properties
    * Methods of Authentication using Hashes
  * Simple Hash Function & its Weaknesses
  * SHA-1 Algorithm
    * Description & Scheme
    * Security Analysis & Birthday Attack
  * Evolution of Hash Standards: SHA-2, SHA-3
  * Recent News on SHA-1 Attacks

**IV. Advanced Cryptography**

* Computing over Encrypted Data
  * Homomorphic Encryption (Partial vs. Fully)
    * Breakthroughs & Recent Developments
    * Potential Applications
  * CryptDB
    * Onion-Layered SQL-Aware Encryption
    * Querying in CryptDB

* Steganography
  * Definition & Information Hiding
  * Digital Watermarking
  * Cover Objects
    * Texts, Images, Audio/Video Files, Network Packets
  * Steganographic Methods
    * LSB Substitution
    * Stochastic Modulation
    * Transform Space Algorithms (e.g. Jsteg)
  * Strengths & Weaknesses of Steganography

* Quantum Cryptography & Computing
  * Principles of Quantum Mechanics
  * Qubits & Measurements
  * Quantum Key Distribution (BB84 Protocol)
    * Practical Implementations & Quantum Hacking
  * Quantum Computing & Cryptanalysis
    * Shor's Algorithm & its Implications
    * Post-quantum Cryptography

**V. Security Protocols & Analysis**

* Definition & Examples (e.g. Needham-Schroeder)
* Correctness of Protocols & Assumptions
* Formal Methods & Logical Representation
* Automated Verification & Analysis
  * Model Checking (State Exploration)
  * Theorem Proving (Automated & Interactive)
  * Specialized Approaches (e.g., ProVerif)
* Attack on Needham-Schroeder Protocol

**VI. Network Security**

* Firewalls
  * Definition & Types (Hardware & Software)
  * Firewall Characteristics & Types of Control
  * Limitations of Firewalls
  * Firewall Types & Functionality
    * Packet Filtering Router
    * Circuit-level Gateway
    * Application-level Gateway (Proxy)
  * Next-Generation Firewall Requirements

* Monitoring & Intrusion Detection
  * Defense Lines & Anti-Intrusion Methods
    * Prevention, Pre-emption, Deterrence, Deflection, Detection, Countermeasures
  * Intrusion Detection Systems (IDS)
    * Types: Network-Based, Host-Based, Application-Based
  * Intrusion Detection Methods
    * Anomaly-Based vs. Knowledge-Based (Signature-Based)
  * Techniques for Intrusion Detection
    * Statistical Analysis
    * Neural Networks & Machine Learning
    * Rule-Based (Expert) Systems
    * Signature-Based Methods
    * State-Transition Analysis
    * Computer Immunology
    * User Intention Identification
    * Data Mining

**VII. Attacks & Defenses**

* Malicious Software
  * Taxonomy: Trapdoors/Backdoors, Logic Bombs, Trojan Horses, Zombies, Viruses, Worms
  * Types of Viruses & their Characteristics
  * Infamous Examples: Creeper, Reaper, Melissa, Morris Worm, Blaster, Slammer
* Antivirus Approaches
  * Prevention, Detection, Identification, Removal
  * Generations of Antivirus Software
    * Simple Scanners, Heuristic Scanners, Activity Traps, Full-Featured Protection
* Advanced Antivirus Techniques
  * Generic Decryption & Simulation
  * Behavior-Blocking Software
* Monitoring & Detection of Internet Worms
  * Worm Monitoring System & Detection Methods
    * Anomaly Detection: Threshold-Based & Trend-Based

* Insertion Attacks
  * SQL Injection
    * Countermeasures: Input Validation, Prepared Statements
  * Cross-Site Scripting (XSS)
    * Countermeasures: Input Sanitization

**VIII. Data Aggregation, Privacy & Anonymity**

* Privacy Concerns & Information Privacy Threats
* Personal vs. Private Information
  * GDPR & Data Protection
* Personally Identifiable vs. Anonymized Information
* Aggregate Information & Privacy Risks
* Open Source Intelligence Gathering (OSINT)
* Sources of Personal & Private Information
  * User-Provided Data
  * Data Obtained by Observation & Traces

* Anonymity in Communications
  * Anonymizers (Proxy Servers)
  * Mix-Networks
  * Crowds
  * Tor Network