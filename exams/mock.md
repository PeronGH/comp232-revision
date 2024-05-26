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

[Notes](../notes/07-Algorithms.md#Diffie-Hellman%20Key%20Exchange)

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
- Also the output length may not be fixed, as the encrypted message may not have 240bits
- For message less than 240bits, one can comp the original message if public key is known
- RSA is much slower