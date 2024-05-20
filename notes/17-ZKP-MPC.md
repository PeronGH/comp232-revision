# Zero-Knowledge Proofs and Secure Multi-Party Computations

## Zero-Knowledge Proofs (ZKP)
- Allows convincing someone that you know something (solution to a problem, a secret password, etc.) without revealing the information itself
- Originated from the work of Goldwasser, Micali, and Rackoff in the 1980s

### Example: Interactive Zero-Knowledge Proof of 3-Colorability
- Problem: How to color vertices of a graph such that no neighboring vertices have the same color (NP-hard problem)
- Can the Prover (Peggy) convince the Verifier (Victor) that she knows a 3-coloring of the graph without revealing any information?
- Protocol:
  1. Peggy hides her solution and allows Victor to open the colors of any pair of vertices
  2. Peggy reshuffles actual colors preserving 3-colorability, hides the modified solution, and allows Victor to open the colors of any pair of vertices again
  3. Repeat step 2 until Victor is convinced

### Requirements for ZKP
1. Completeness: Prover should be able to convince Verifier that they have a true solution (with high probability)
2. Soundness: Prover should only be able to convince Verifier of true solutions
3. Zero-knowledge: Verifier should not learn anything except the fact that the Prover has a solution

### Applications of ZKP
- Zero-knowledge authentication
- Zero-knowledge information exchange contracts
- Verifiable computing

### Interactive vs. Non-Interactive ZKP
- zk-SNARK (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge):
  - Prover sends a short message (evidence) to a Verifier to prove they know something without revealing additional information
  - Example: Prover may convince Verifier that they have an input (message, number) which produces a given hash
- Advantages: small proofs and cheap verification
- Disadvantages: expensive prover computations (both time and space)
- Statement to be proved (F(x,w)=true) has to be presented by a circuit (10-20 million gates max as of 2017, taking 1ms per gate to produce a proof)

### DIZK (Distributed Zero-Knowledge Proof System)
- Developed by H. Wu et al. at UC Berkeley (2018)
- Distributes proof computations across a computer cluster (Java & Apache Spark)
- Can generate proofs for statements up to billions of circuits, taking 0.01ms per gate
- Available at https://github.com/scipr-lab/dizk
- Examples of applications: authenticity of edited photos, integrity of machine learning models

## Secure Multi-Party Computations (SMPC)
- Several parties compute something useful with their secret information without sharing the information itself
- Yao's Millionaire Problem (1982): Alice and Bob want to know who is richer without revealing their actual wealth

### Short History of Secure MPC
- Yao (1982): the idea of MPC, Garbled Circuits Protocol for generic MPC introduced in the following years
- Malkhi et al. (2004): Fairplay implementation of generic SMPC (median of two sorted arrays of ten integers in 7s)
- 2004-present: speed of SMPC increased by 5 orders of magnitude (D. Evans et al., "A Pragmatic Introduction to Secure Multi-Party Computation," 2018)

### Applications of SMPC
- Danish sugar beets auction (2009)
- Estonian Student Study (2015)
- Boston Wage Equity study (2017)
- Secure Auctions, Voting, Secure Machine Learning, Privacy-Preserving Genomics, etc.

### Simplified Yao's Protocol
- Goal: compute F(x,y) where P1 holds x ∈ X and P2 holds y ∈ Y as their private values
- Protocol:
  1. P1 calculates and tabulates all values of F(x,y) for x ∈ X and y ∈ Y in the table T = (Tx,y)
  2. P1 encrypts each Tx,y with two random keys kx and ky, randomly permutes the table T, and sends it to P2
  3. For P2 to compute F(x,y), P1 sends kx and ky to P2, who can then complete the computation
- Question: How does P1 know which ky to send to P2? (P1 knows x but not y)
- Answer: It is done using oblivious transfer

### Oblivious Transfer (OT)
- Given: Sender S has input secrets x0 and x1 (binary strings), and Receiver R has a selection bit b ∈ {0,1}
- After executing OT: Receiver gets xb and Sender does not learn anything about b
- Can be implemented using public-key encryption
- The above version is 1-out-of-2 OT; for simplified Yao's protocol, 1-out-of-|Y| OT is needed, which can be implemented similarly

### From Theory to Applications: JIFF Library
- Developed at Boston University (multiparty.org)
- JavaScript library for building applications that rely on secure multi-party computation
- Highly flexible with a focus on usability, can be run in the browser, on mobile phones, or via Node.js
- Developers need not be familiar with MPC techniques or know the details of cryptographic protocols to build secure applications
- Available at https://github.com/multiparty/jiff

## Advanced Cryptography to Applications
- Fully Homomorphic Encryption (FHE)
- CryptDB-like solutions
- Zero-Knowledge Proofs (ZKP)
- Secure Multi-Party Computations (SMPC)
- Verifiable Computing

These advanced cryptographic techniques are at the beginning of exciting applications and have the potential to revolutionize secure computation and privacy-preserving solutions in various domains.