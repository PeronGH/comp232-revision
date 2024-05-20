# Monitoring and Intrusion Detection

## Information Protection
- Several approaches and techniques for information protection have been discussed, mainly focusing on making security/privacy attacks difficult
- Not all attacks can be prevented
- How to deal with attacks that still occur?

## Defence Lines: Anti-Intrusion Methods
- Taxonomy of anti-intrusion methods:
  - Prevention
  - Pre-emption
  - Deterrence
  - Deflection
  - Detection
  - Countermeasures

## Anti-Intrusion Methods
1. Prevention: preclude or seriously reduce the likelihood of a particular attack
   - Internal prevention: controlled by the system itself (system owner)
   - External prevention: takes place in the environment of the system
2. Pre-emption: strike against the threat before it could strike against us
3. Deterrence: persuade an attacker not to launch an attack or to stop an ongoing attack, usually by increasing the risk of negative consequences for the attacker
4. Deflection: trick an intruder away from where they could do damage ("honeypot" techniques)
5. Detection: find intrusion attempts and launch countermeasures
6. Countermeasures: actively counter an intrusion

## Intrusion Detection
- The most important of anti-intrusion methods
  - Prevention, pre-emption, and deterrence are not absolute, and attacks happen
  - For countermeasures, one has to detect an attack
- General principles, structure, and functionality of Intrusion Detection Systems (IDSs) are considered

## Typical Intrusion Detection System (IDS)
- Elements of a typical IDS:
  1. Audit collection: collect data for intrusion detection (keyboard input, log files, network activity data)
  2. Audit storage: store data for further processing (amount of data may be a problem)
  3. Processing: execute algorithms based on collected data to find evidence of suspicious behavior
  4. Configuration data: specify how the IDS works (data collection, attack response, etc.)
  5. Reference data: information about known intrusion signatures, bad/normal behavior
  6. Active/Processing data: intermediate results stored during processing
  7. Alarm

## Types of IDS
1. Network-based IDS:
   - Monitor network backbones
   - Distributed among different nodes in the network
   - Usually passive, making them difficult for attackers to detect
   - May not be able to analyze traffic in large, busy networks
2. Host-based IDS:
   - Operate on hosts
   - Defend and monitor operating and file systems for signs of intrusion
   - Usually monitor activities with a higher level of detail
3. Application-based IDS:
   - Deal with events appearing inside a particular application (e.g., database management systems, content management, accounting systems)

## Intrusion Detection Methods
1. Anomaly-based intrusion detection:
   - System reacts to abnormal behavior
   - Uses behavior profiles and can learn what is "normal" behavior
   - Advantages:
     - Possibility of detecting novel attacks as intrusions
     - Less dependence on operating environment
     - Ability to detect abuse of user privileges
   - Disadvantages:
     - Substantial false alarm rate
     - User behaviors can vary with time, requiring constant updates to the normal behavior profile database
2. Knowledge-based detection (policy-based, signature-based, specification-based):
   - System tries to match explicit policies/signatures with collected data to find evidence of suspicious behavior
   - Example of a signature:
     ```
     alert icmp $EXTERNAL_NET any -> $HOME_NET any (msg:"MISC large ICMP"; dsize: >800; reference:arachnids,246; classtype:bad-unknown; sid:499;)
     ```
     Alarm raised if an ICMP packet incoming from the external network, associated with any port, and having a size greater than 800 bytes
   - Advantages:
     - Very low false alarm rate
     - Simple algorithms, easy implementation
   - Disadvantages:
     - Difficulties in updating information on new types of attacks
     - Unable to detect unknown attacks (knowledge-based)

Intrusion detection is a crucial component of an organization's cybersecurity strategy. By monitoring systems and networks for suspicious activities and anomalies, IDSs can help detect and respond to intrusion attempts in a timely manner. A combination of different types of IDSs and detection methods can provide a more comprehensive defense against various types of attacks.