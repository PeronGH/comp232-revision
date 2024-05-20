# Firewalls

## Security Threats and Networks
- Many serious security threats come from networks
- Firewalls implement hardware or software solutions based on the control of network connections between local networks and other networks

## Types of Firewalls
- Hardware firewalls
- Software firewalls

## Layers in Network Connections (OSI Model)
- Firewalls work at the IP (network) and TCP (transport) layers

## Firewall Characteristics
- All traffic from inside to outside, and vice versa, must pass through the firewall
  - All access to the local network is blocked except via the firewall
- Only authorized traffic, defined by the local security policy, is allowed to pass in either direction

## Types of Control Used by Firewalls
1. Service control: determines what types of services can be accessed
2. Direction control: determines in which direction particular service requests may be initiated
3. User control: determines access to a service according to a user
4. Behavior control: controls how particular services are used

## Limitations of Firewalls
- Cannot protect against attacks that bypass the firewall
- Does not protect against internal threats
- Cannot protect, in general, against the transfer of virus-infected programs or files

## Types of Firewalls
1. Packet filtering router (works at the network layer, IP)
2. Circuit-level gateway (works at the transport layer, TCP)
3. Application-level gateway (works at higher layers)

### Packet-Filtering Router
- Applies a set of rules to each incoming IP packet and then forwards or discards the packet
- Filtering is based on information contained in a network packet
- Filtering rules are based on:
  - Source IP address
  - Destination IP address
  - Source and destination transport-level address (transport level port number)
  - IP protocol field (defines the transport protocol)
- Default policies:
  - Discard: that which is not explicitly permitted is prohibited (more conservative)
  - Forward: that which is not explicitly prohibited is permitted (more convenient but less secure)
- Pros:
  - Simple
  - Transparent for users
  - Very fast
- Cons:
  - Lack of upper-layer functionality
  - Do not support advanced user authentication schemes
  - Cannot block specific application commands (either the application is disallowed, or all its functions are permitted)

### Circuit-Level Gateway
- Traffic is filtered based on specified session rules, such as a session initiated by a recognized computer
- Sets up two connections:
  - One between itself and a TCP user on the inner host
  - One between itself and a TCP user on the outer host
- Once connections are established and security criteria are met, both connections are linked by the gateway
- Pros:
  - Relatively inexpensive
  - Have the advantage of hiding information about the private network they protect
- Cons:
  - Do not filter individual packets

### Application-Level Gateway (Proxy)
- Can filter packets at the application layer of the OSI model
- Incoming or outgoing packets cannot access services for which there is no proxy
  - Example: an application-level gateway configured as a web proxy will not allow any FTP, telnet, or other traffic through
- Can filter application-specific commands such as HTTP POST and GET
- Pros:
  - Offer a high level of security
  - Application-specific protection
- Cons:
  - Significant impact on network performance
  - Not transparent to end users
  - Require manual configuration of each client computer

## Firewalls: Benefits and Problems
- Benefits:
  - Protect private local area networks from hostile intrusion from the Internet
  - Flexibility in implementing security policies
  - Relatively inexpensive solution
- Possible problems:
  - Potential traffic bottleneck
  - Security concentrated in one spot

## Key Next-Generation Firewall Requirements (Palo Alto Networks Firewall Overview)
1. Identify applications, not ports
2. Identify users, not just IP addresses
3. Inspect content in real-time (deep packet analysis)
4. Simplify policy management
5. Deliver multi-gigabit throughput

Firewalls are an essential component of network security, acting as a barrier between trusted internal networks and untrusted external networks. They provide a means to enforce security policies and control access to network resources based on various criteria. However, firewalls have limitations and should be used in conjunction with other security measures to create a comprehensive security strategy.