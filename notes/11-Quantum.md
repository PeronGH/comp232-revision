# Quantum Cryptography

## Introduction
- Code-makers and code-breakers have been competing for supremacy for thousands of years
- Quantum mechanics may soon become a powerful new weapon in their arsenals (Daniel Gottesman and Hoi-Kwong Lo, 2001)

## Quantum Mechanics (QM) Principles
- A particle can be in a superposition of several states at the same time
  - Example: an electron may be in a combination of states "at H1" and "at H2"
  - When measured, we always get a definite state
- Particle characteristics are best described as blends or superpositions of base values
- When characteristics are measured, the superposition collapses into a single state, losing any information about the state before measurement
  - Special importance for quantum cryptography: you cannot measure the system without disturbing it

## Qubits
- Qubit (quantum bit): a quantum system with two discrete states, usually denoted by |0⟩ and |1⟩
- A state of a qubit is an arbitrary superposition of basis states, i.e., a linear combination a|0⟩ + b|1⟩, where a and b are complex numbers called amplitudes
- The norm squared of the amplitude of a state is the probability of measuring the system in that state: |a|² for |0⟩ and |b|² for |1⟩

### Example
- If an electron has equal probabilities to go through either H1 or H2, its position might be a superposition of two states: |H1⟩ + |H2⟩
- If one tries to measure the electron's position at H1 or H2, the probability of finding the electron there would be ½
- Measurements destroy the superposition of states, resulting in the following distribution: |H1⟩ or |H2⟩

## Measurements
- Measuring any quantum system (e.g., qubit) projects the state vector of the system onto a new state vector
- Measurements in a set, called a "basis," describe what can be observed
  - Example: basis states |H1⟩ and |H2⟩
- Any measurement is defined by a basis, and the result of the measurement is a (state) vector of the basis
- The probability of getting a particular result is defined by the amplitude assigned to a specific basis state vector
- Quantum systems can often be described with many different but related bases

### Photon Measurement with Different Bases
- Polarization of a photon: superposition of two basis states
- Many possible bases, but we consider two:
  1. |↔⟩ and |↕⟩, denoted by +
  2. |⤢⟩ and |⤡⟩, denoted by ×

## Quantum Key Distribution (QKD)
- Charles H. Bennett and Gilles Brassard, 1984 (BB84)
- QKD protocol ensures:
  - The distributed key will be perfectly secure, or
  - The parties will learn that someone is listening and therefore not use the key
- Alice and Bob agree in advance on the representation of 0 and 1 in each of two bases for photon polarization, e.g.:
  - |↔⟩ and |⤡⟩ represent 0
  - |↕⟩ and |⤢⟩ represent 1

### BB84 Protocol: General Scheme
- Alice and Bob use two channels: quantum and classical
- Both channels may be overheard by Eve, the adversary

### BB84 Protocol Steps
1. Alice sends Bob a stream of polarized photons, randomly choosing between |↔⟩, |↕⟩, |⤢⟩, and |⤡⟩ polarizations (quantum channel)
2. Upon receiving a photon, Bob randomly chooses between + and × bases to measure the photon
3. After transmission, Bob sends Alice the sequence of bases he used (public channel)
4. Alice tells Bob which bases were the same as hers (public channel)
5. Alice and Bob discard measurements for which Bob used a different basis
6. The remaining ~50% of measurements form a shared key; Bob will get the same polarization that Alice sent

### BB84 Protocol: Eavesdropping
- If Eve listens only on the public channel, she cannot learn anything about the key itself (because Alice sends random polarizations for a given basis)
- If Eve tries to listen on the quantum channel:
  - She has to guess the correct basis at each step (~50% on average) to make measurements
  - When Eve measures a photon, its state is altered to conform to the basis she used, so Bob will get the wrong result in approximately half of the cases where he and Alice have chosen the same basis

### BB84 Protocol: Error Detection
- Alice and Bob publicly compare small parts of their raw keys to estimate the error rate, then delete these publicly disclosed bits from their key, leaving the tentative final key
- If the error rate exceeds a pre-determined threshold, indicating possible interception by Eve, they start over from the beginning to attempt a new key

## Practical Implementations
- Los Alamos Laboratory:
  - Implementation of the protocol with a quantum channel; distance = 184.6 km (fiber optic), September 2006
  - Quantum channel through the air; distance > 10 km
- University of Munich: quantum key exchange with an airplane (>20 km, 300 km/h), 2012
- Italian Space Agency, Padova University, & Chinese Space Agency: quantum communication with a satellite; distance > 1,000 km, 2015
- Commercial implementations: ID Quantique
- Quantum Random Number Generation: ID Quantique

## Quantum Crypto Hacking
- In theory, QKD is very secure; in practice, attackers may go outside the assumptions
- Quantum hacking: instead of passively measuring quantum exchange, attackers use active probing
  - Example: large pulse attack (~2001) uses a powerful laser to send a beam to either Bob or Alice, to get some reflected photons back and learn their settings (base choices) just before they use them

## Quantum Computing
- Quantum systems may be used to perform computations
- Computations involve:
  - Performing controlled evolution of a quantum system
  - Suitable measurements
- Quantum models of computation and quantum algorithms:
  - R. Feynman, 1982: the idea of using quantum effects to perform massive computations
  - D. Deutsch, 1985: formal model of Universal Quantum Computer
  - P. Shor, 1994: quantum computers could factor large numbers efficiently, in polynomial time

## Quantum Cryptanalysis
- Shor's algorithm for factoring large numbers has O((log N)³) complexity, so it is polynomial in the length of the input number N
- Could be used for efficient breaking of RSA encryption, if implemented
- Many technical difficulties, but:
  - Implemented by IBM in Dec 2001 on a 7-qubit computer to factorize 15
  - Michigan University, Dec 2005: first quantum chip (1 qubit)
  - Innsbruck University, Dec 2005: first Quantum Byte (8-qubit system)
  - Bristol University, 2011: implementation of Shor's algorithm, factorized 21
  - First commercial quantum computer (annealer) by D-Wave Systems; the company claims to have a 2000-qubit processor in their 4th generation quantum computer (not of the type required for factoring large numbers)
  - IBM Q experience (online): https://quantumexperience.ng.bluemix.net/qx/experience
- Estimated: to make a threat to current RSA standards, one needs ~5,000-10,000 qubits (of high quality)
- Post-quantum cryptography: active development of methods for which quantum attacks are not known