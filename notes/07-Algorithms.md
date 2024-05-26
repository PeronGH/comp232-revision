# Algorithms: RSA, DH, MAC

## RSA Public-Key Encryption Algorithm
- Developed in 1977 by R. Rivest, A. Shamir, and L. Adleman
- Block cipher where plaintext and ciphertext are integers between $0$ and $n-1$
- Encryption: $C = M^e \mod n$
- Decryption: $M = C^d \mod n$
  - $M$: plaintext block, $C$: ciphertext block, $(e, n)$: public key, $(d, n)$: private key

### Key Generation
1. Select two prime numbers $p$ and $q$
2. Calculate $n = p \times q$
3. Calculate $\phi(n) = (p-1)(q-1)$
4. Select integer $1 < e < \phi(n)$ and relatively prime with $\phi(n)$
5. Calculate $d$ such that $de \equiv 1 \mod \phi(n)$
6. Public key $KU = (e, n)$
7. Private key $KR = (d, n)$

### Fermat-Euler Theorem
- Used to prove the correctness of RSA
- For prime $p$ and integer $x$ not divisible by $p$: $x^{p-1} \equiv 1 \mod p$

### Chinese Remainder Theorem
- For relatively prime $p$ and $q$ and any $x$ and $y$:
  - $x = y \mod p \and x = y \mod q \implies x = y \mod pq$


### Breaking RSA
- Brute-force approach: try all possible private keys (infeasible for large $n$)
- Factor $n$ to find prime factors $p$ and $q$ (believed to be computationally difficult)

### Security of RSA
- Relies on the complexity of the factoring problem
- No known efficient algorithm for factoring large numbers
- RSA Challenge: factoring large composite numbers (e.g., RSA-250 with 829 bits)

### Common Attacks on RSA
- Common factors attack (2012): exploiting insufficiently random key generation
- Shor's factorization algorithm for quantum computers (future threat)

## Diffie-Hellman Key Exchange
- Algorithm for key exchange, not encryption
- Secure due to the difficulty of computing discrete logarithms
  - DLP: For $A=g^a\mod p$, know $A, g, p$, infeasible to compute $a$

- Publicly known numbers: prime $q$, primitive root $\alpha$ of $q$
- Key exchange process:
  1. A selects random integer $X_A$, computes $Y_A = \alpha^{X_A} \mod q$, sends $Y_A$ to B
  2. B selects random integer $X_B$, computes $Y_B$ = $\alpha^{X_B} \mod q$, sends $Y_B$ to A
  3. A computes $K = {Y_B}^{X_A} \mod q$
  4. B computes $K = {Y_A}^{X_B} \mod q$
  5. $K$​​ is the shared secret key
- Attack: compute $X_A$ from $\alpha,q,Y_A$, then compute $K$

## Message Authentication Code (MAC)
- Verifies the authenticity (genuineness and origin) of a message
- Uses a shared secret key between sender and receiver
- $\text{MAC} = F(K, M)$, where $K$ is the key and $M$ is the message
- MAC is appended to the message and sent
- Receiver computes MAC and compares it with the received MAC

### One-Way Hash Functions
- Alternative to MAC for message authentication
- Compute a hash value $h = H(M)$ without using a secret key
- Properties:
  - $H$ can be applied to data of any size
  - $H$ produces a fixed-length output
  - $H(x)$ is easy to compute for any $x$
  - Infeasible to find $x$ given $H(x)$ (one-way property)
  - Infeasible to find collisions:
    - Weak collision resistance: For $x$, infeasible to find $y$ so that $H(x) = H(y)$
    - Strong collision resistance: Infeasible to find $(x,y)$ so that $H(x) = H(y)$

### Simple Hash Function
- XOR of every block of the input
- Does not satisfy weak and strong collision resistance

### SHA-1 Secure Hash Algorithm
- Produces a 160-bit message digest from an input $< 2^{64}$ bits
- Processes input in 512-bit blocks
- Compression function with 4 rounds of 20 steps each

### Birthday Attack
- Finding collisions in a hash function
- Average number of steps needed: $~1.25 × \sqrt{2^n}$, where $n$ is the hash length

### Problems and Solutions
- Mathematical weaknesses found in SHA-1 (2005)
- Development of SHA-2 (SHA-224, -256, -384, -512) and SHA-3 (2012)
- SHA-1 deprecated as a NIST standard in 2011 and disallowed for digital signatures in 2013
- Recent collision attacks on SHA-1: freestart collision (2015), full collision (2017), chosen prefix attack (2020)