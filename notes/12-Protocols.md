# Security Protocols

## Security Protocols
- A set of rules adhered to by communication parties to ensure achieving various security or privacy goals (e.g., establishing a common cryptographic key, achieving authentication)
- Example: Diffie-Hellman protocol for key exchange

## Needham-Schroeder Protocol
- Goal: establish mutual authentication between two parties A and B in the presence of an adversary who can intercept, delay, read, copy, and generate messages, but does not know the secret keys of principals shared with the authentication server S
- A and B obtain a shared secret key through authentication server S
- The protocol uses shared-key encryption/decryption
- Message exchange:
  1. A → S: A, B, N_A
  2. S → A: {K_AB, B, N_A, {K_AB, A}_Kb}_Ka
  3. A → B: {K_AB, A}_Kb
  4. B → A: {N_B}_Kab
  5. A → B: {N_B - 1}_Kab
- K_a and K_b are keys of A and B shared with S, respectively
- N_A and N_B are nonces introduced by A and B, respectively
- K_AB is a secret session key for A and B provided by S

## Correctness of Protocols
- Establishing correctness is challenging due to the presence of a malicious agent (intruder or adversary) who may have complete or partial control over the communication network and different computational capabilities
- Correctness depends on assumptions about the capabilities of the possible intruder, which are often left implicit
- Formal methods can help establish correctness by:
  - Making explicit all assumptions involved in a protocol
  - Creating a formal model of the protocol and its execution
  - Applying formal reasoning to establish correctness

## Logical Representation and Analysis
- Formal aspects of reasoning are an important part of logic
- Logical representation and analysis of security protocols is a particularly successful approach for protocol verification
- Non-classical modal epistemic logics dealing with notions such as "belief" and "knowledge" are more suitable than classical logics dealing primarily with "truth"

## Automated Verification/Analysis
- Manual formal analysis is difficult and error-prone
- Development of methods for automated or semi-automated (interactive) validation and verification is important, especially for security protocols
- Different directions:
  - Model checking (state exploration tools)
    - Specific (NRL Protocol Analyzer, etc.)
    - General-purpose (SMV, SPIN, Mocha, etc.)
    - General-purpose combined with specific translators (Casper/FDR, etc.)
  - Unbounded model checking for crypto protocols (ProVerif, Tamarin, etc.)
  - Theorem proving
    - Automated (TAPS, etc.)
    - Interactive (Isabelle, PVS, etc.)
  - Combinations of above techniques (Athena, etc.)
  - Others: decision procedures for specific theories, infinite-state model checking, etc.

## Model Checking
- A protocol (system executing a protocol) is represented as a transition system M with finitely many states
- A property to be analyzed is expressed by a formula of a logic (temporal, modal, etc.) f
- Verification amounts to checking whether the formula f is true in M
- Model checking is done via efficient state exploration techniques
- Advantages: fully automated procedures, very efficient state exploration
- Disadvantages: finite-state abstraction is not always adequate, especially for protocols with an unbounded number of participants or rounds

## Attack on Needham-Schroeder Protocol
- A flaw in the Needham-Schroeder protocol based on public-key cryptography was discovered using model checking methods (Gavin Lowe, 1995-1996)
- The attack involves a corrupt participant I impersonating A

## Theorem Proving
- A protocol (system) to be verified is described by a formula Fs of a logic (classical first-order, higher-order, modal, temporal, etc.)
- A property to be verified is expressed by a formula P of the same logic
- To establish the required property, it is enough to prove the theorem Fs → P
- Potential benefits: systems with an unbounded (infinite) number of states can be analyzed
- Challenges: problems are, in general, undecidable; procedures are incomplete and of high complexity
- Approaches:
  - Apply automated procedures for fragments of first-order and higher-order logic (e.g., E. Cohen, TAPS system, Microsoft Research)
  - Use interactive theorem proving (e.g., L. Paulson, Cambridge: using Isabelle; J. Bryans, S. Schneider: using PVS)

## Specialized Approaches
- Bruno Blanchet, INRIA: approach based on ideas from Logic Programming (ProVerif)
  - A protocol is represented as a set of Horn clauses (like a program in Prolog), defining capabilities of all participants
  - Verification amounts to checking whether a security-breaching goal can be reached (derived) from the set of clauses
  - If the system detects the goal is unreachable, the protocol is correct
  - Novel operational semantics (search strategy) is defined to avoid undesirable looping
  - Recent versions use pi-calculus as a language for the front-end

Formal analysis of security protocols is crucial for establishing their correctness and identifying potential flaws. Various techniques, such as model checking and theorem proving, have been successfully applied to verify security protocols. Automated and specialized approaches, like ProVerif, have also been developed to facilitate the verification process. However, the correctness of protocols is only established within the context of the formal model and the explicit assumptions made about the capabilities of participants and adversaries.