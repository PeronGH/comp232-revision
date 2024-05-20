# Security Architecture

## Goals of Network Security - CIA Triad
- Confidentiality: Protecting data from unauthorized access
- Integrity: Ensuring data remains unaltered by unauthorized parties
- Availability: Ensuring systems and data are accessible to authorized users

## OSI Security Architecture (ITU-T Recommendation X.800)
- Defines a systematic way to define security requirements and characterize approaches to satisfy them
- Key concepts:
  - Security attack: Actions that compromise the security of information owned by an organization or person
  - Security mechanism: Mechanisms designed to detect, prevent, or recover from a security attack
  - Security service: Services that enhance the security of data processing systems and information transfers, using one or more security mechanisms

## Security Attacks
- Passive attack: Aims to learn or use information from the system without affecting system resources (e.g., interception of messages, traffic analysis)
- Active attack: Attempts to alter system resources or affect their operation (e.g., interruption, modification, fabrication)

## Security Services/Security Attributes (X.800 Recommendation)
1. Authentication: Assuring communication is authentic (source identity, connection integrity)
2. Access control: Controlling access to resources based on conditions and permissions
3. Data confidentiality: Protecting data from unauthorized disclosure (connection, connectionless, selective field, traffic-flow)
4. Data integrity: Assuring received data is exactly as sent by an authorized entity (no modification, insertion, deletion, replay)
5. Nonrepudiation: Protecting against denial of participation in communication (origin, destination)
6. Availability service: Protecting a system to ensure its availability, addressing denial-of-service attacks

## Mapping Attacks to Security Services
- Release of message contents: Confidentiality
- Traffic analysis: Traffic flow confidentiality
- Masquerade: Peer entity authentication, access control
- Replay: Data origin authentication, data integrity
- Modification of messages: Data integrity
- Denial of service: Availability

## Security Mechanisms (X.800)
- Encipherment
- Digital signature
- Access control mechanisms
- Data integrity mechanisms
- Authentication exchange
- Traffic padding
- Routing control
- Notarisation

These security mechanisms are used to implement the various security services to protect against attacks and ensure the confidentiality, integrity, and availability of systems and data.