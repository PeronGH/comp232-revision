# Authentication

## Identification, Authentication, and Authorization
- Identification: Claiming an identity
- Authentication: Proving the claimed identity
- Authorization: Granting access rights based on the authenticated identity

## Authentication Techniques
1. Knowledge-based (something you know)
   - Password-based techniques
2. Possession-based (something you have)
   - Token-based authentication
3. Biometrics-based (something you are)
   - Physical or behavioral characteristics

## User vs. Machine Authentication
- User authentication: Verifying the identity of a human user
- Machine authentication: Verifying the identity of a machine or device

## Password-based Techniques
- Most common form of user authentication
- User provides a secret password to prove their identity
- Problems with passwords:
  - Weak passwords, password reuse, password sharing
  - Susceptible to guessing, dictionary attacks, social engineering
  - Shoulder surfing, keylogging, phishing
  - Forgotten passwords, password management issues

## Token-based Authentication
- User possesses a physical token that proves their identity
- Types of tokens:
  - Memory cards, smart cards
  - One-time password (OTP) generators
  - Cryptographic keys, digital certificates
- Problems with tokens:
  - Loss, theft, or damage of tokens
  - Cost of token distribution and management
  - User inconvenience and resistance

## Multi-factor Authentication Techniques
- Combines two or more authentication factors (e.g., password + token)
- Provides stronger security by requiring multiple forms of evidence
- Mitigates the weaknesses of individual authentication methods

## Biometrics-based Techniques
- Uses unique physical or behavioral characteristics to authenticate users
- Examples: fingerprints, facial recognition, iris scans, voice recognition, keystroke dynamics
- Advantages: uniqueness, convenience, non-repudiation
- Problems with biometrics:
  - False acceptance and false rejection rates
  - Biometric data privacy and security concerns
  - Spoofing and mimicry attacks
  - Enrollment and maintenance costs

## Multi-modal Architecture
- Combines multiple biometric modalities for enhanced accuracy and security
- Fusion of biometric data at various levels (sensor, feature, score, decision)
- Provides redundancy and resilience against individual biometric failures

## Recent Advances: Authentication by Brainwaves
- Uses electroencephalography (EEG) to measure unique brain activity patterns
- Potential for highly secure and spoof-resistant authentication
- Currently in research and development stage, with challenges in accuracy and practicality

User authentication remains a critical component of cybersecurity, with ongoing research and innovation aimed at developing more secure, convenient, and reliable authentication methods.