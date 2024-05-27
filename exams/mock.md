# Mock Exam Paper

## 1.(a)

What are potential problems with the security protection based on the secrecy of an encryption algorithm?

Answer:

- It is called "security by obscurity"
- Difficult to keep the algorithm secret
- Limited expert scrutiny
- If leaked, the whole system collapse, no fallback 

## 1.(b)

A simple way of finding a collision in a hash function H is as follows

1. Pick initial value I and calculate H(I);
2. Pick randomly further value J an compare H(J) to H(I);
3. Repeat step 2 until H(J) = H(I).

Suggest an improvement of this attack, which would likely lead to faster discovery of the collision.

Answer:

- cache value and hash results in a table
- avoid picking the same value

## 1.(c)

Describe the Diffie-Hellman (DH) Key Exchange algorithm and the attack on this algorithm that uses the computation of discrete logarithms. Why is DH considered secure?

Answer:

[Notes](../notes/07-Algorithms.md#Diffie-Hellman Key Exchange)

## 2.(a)

Define passive security attacks. Explain how the development of quantum cryptography may change the way of dealing with passive attacks.

Answer:

- passive security attacks listen the communication without modification. it aims to gather information.
- traditional way relies on encryption.
- quantum cryptography allows for effective detection of passive attacks, as qubit changes its state when measured.

## 2.(b)

Explain why RSA can be considered as a partially-homomorphic encryption algorithm.

Answer:

RSA is homomorphic with respect to multiplication.

- $C_1 = {M_1}^e \mod N$
- $C_2 = {M_2}^e \mod N$

Then:

- $C_1 \times C_2 = ({M_1}^e \mod N) \times ({M_2}^e \mod N)$

- $C_1 \times C_2 = ({M_1} \times {M_2})^e \mod N$

## 2.(c)

What is wrong in the following algorithm for computing a hash function? Take a message M, generate a random private RSA key K. Encrypt M with K and take the first 240 bits of the result as a hash of M.

Answer:

- The major problem is that it is not deterministic
- Also the output length may not be fixed, as the encrypted message may be shorter than 240bits
- For message less than 240bits, one can comp the original message if public key is known
- RSA is much slower

## 3.(a)

Explain what are the advantages and disadvantages of using quantum generator of random numbers in cryptography

Answer:

Advantages:

1. True randomness

Disadvantages:

1. costly hardware
2. slow

## 3.(b)

Describe the RSA-based blind signature technique. Discuss its role in the implementation of electronic payment systems and electronic voting systems.

Answer:

(Skipped. Is it present in syllabus?)

## 3.(c)

Explain what is a zero-knowledge proof (ZKP). What are the possible applications of ZKP?

Answer:

- ZKP is to convince someone that you know something (solution to a problem, a secret password, etc.) without revealing the information itself
- It can be used in blockchain to hide transaction details.
- It can also be used to prove user age without private info

## 4.(a)

What is the common factor attack on RSA and why is it practically possible?

Answer:

Assume there are 2 public keys $(e,n)$ using the common factor:

- $n_1=p \cdot q_1$
- $n_2=p \cdot q_2$

Then we can easily find $p = \text{GCD}(n_1,n_2)$ using Euclid's algorithm

Then we can calculate $q_1 = n_1 \div p$, $q_2 = n_2 \div p$​

Then it is possible to calculate private keys. Both keys are compromised.

The attack is practical because it is very fast, and insufficiently random key generation can give it a chance. 

## 4.(b)

What are the two main categories of intrusion detection methods? Describe advantages and disadvantages of methods from each category.

Answer:

[Notes](../notes/13-Monitoring-IDS.md#Intrusion Detection Methods)

## 4.(c)

A simple key exchange protocol shown below can be used to establish a key over an open channel. Here $K_b$ is a public key of B, $N_a$ and $N_b$ are random numbers (nonces) chosen by A and B, respectively, and $k_{ab}$ is the key for symmetric encryption to be exchanged.

- Message 1. A → B : $N_a$
- Message 2. B → A : $N_b$
- Message 3. A → B : $\{k_{ab},A,N_b\}_{K_b}$
- Message 4. B → A : $\{N_a\}_{k_{ab}}$

What is the possible issue with this protocol? How can it be fixed?

Answer:

Vulnerable to MitM attacks. Use DH for key exchange.

## 5.(a)

For a block cipher, what is the Cipher Block Chaining mode (CBC)? What is the main purpose of using CBC mode? What is the main disadvantage of this mode?

Answer:

- Each block XOR with previous one and then encrypted, then serve as the input for next one (first XOR IV).
- More secure than ECB as identical blocks will not be identical after encryption
- if one block has error, all subsequent blocks will contain error

## 5.(b)

What is a multifactor authentication technique? Give an example and explain the rationale behind it.

[Notes](../notes/03-Authentication.md#Multi-factor Authentication Techniques)

## 5.(c)

What is Fully Homomorphic Encryption (FHE)? What is the main issue with applications of FHE? Give an example of an application which would benefit from using FHE.

-  FHE is a type of encryption that allows computations to be performed on encrypted data without ever decrypting it.
- Computation cost can be high
- Database