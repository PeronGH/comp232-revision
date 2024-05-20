# Anonymity

## Privacy Concerns
- Internet and Web technologies were designed to transfer information, not protect privacy or security
- Existing technologies provide opportunities to collect a lot of information about users (e.g., web sites collecting user data)

## Information Privacy
- Alan Westin (1967): "the claim of individuals, groups, or institutions to determine for themselves when, how, and to what extent information about them is communicated to others"
- Information privacy threat: loss of ability to control how and to what extent personal information is communicated to others

## Personal and Private Information
- Personal information: information about a person (e.g., name, date of birth, attended schools)
- Private information: personal information that is not generally known (e.g., bank records)
- GDPR (2018): personal data may not be processed without informed consent or a legal basis

## Personally Identifiable and Anonymized Information
- Personally identifiable information: information from which a person's identity can be derived (e.g., account number)
- Anonymized information: information from which a person's identity cannot be derived (e.g., age)

## Aggregate Information
- Statistical information combined from many individuals to form a single record (e.g., census data)
- No person's identity can be extracted from aggregate information alone
- When combined with other anonymized information, it can help identify and reveal individual characteristics

## Privacy Threats Based on Anonymized Information
- Combining seemingly anonymous information can reveal identity with high probability (e.g., birthday, postcode, age)
- Online examples: screen resolution, battery percentage, operating system, browser version

## Open Source Intelligence Gathering (OSINT)
- Collection and analysis of information gathered from public or open sources
- Examples: news media content, census data, industry journals, public meetings, events open to the public

## "Personal Data for the Taking" (New York Times article)
- John Hopkins University project by Prof. Aviel D. Rubin and students
- Collected personal information on Baltimore citizens using only legal, public sources
- Gathered over a million records with hundreds of thousands of individuals
- Consolidated databases allowed querying multiple layers of information about a single name
- Lessons: personal information is easily available on the Web, and consolidation may violate privacy

## Sources of Personal and Private Information
- User-provided information: names, addresses, passwords, date of birth
- Information obtained by observing user activities or traces: log files, cookies, web bugs, adware, spyware

## Anonymity in Communications
- Protecting privacy by making communication anonymous
- Prevents an adversary from matching a message sender with the recipient (sender-recipient matching)
- Most widespread methods use a trusted third party serving as an anonymizer (special proxy server)

## Anonymizer
- Fetches web pages on behalf of users and displays them within the user's browser
- Replaces sensitive information (e.g., IP address) with its own details
- Provides encryption and blocks potential active privacy and security threats
- Pros: good protection and reasonable cost
- Cons: central proxy "knows everything" about communication, vulnerable to insider attacks

## Mix-Networks (D. Chaum, 1981)
- Mix nodes take incoming messages (packets), modify them, and output in a random order
- Messages are sent through a sequence of mix nodes (a route)
- Each node only "knows" the previous and the next node in the route
- Compromising a single or several (not all) mix nodes does not give an attacker information about sender-receiver matching
- More expensive than anonymizer solutions but provides more privacy protection

## Crowds (M. Reiter, A. Rubin, 1998)
- Based on the idea of "blending into a crowd" by hiding one's actions within the actions of many others
- User joins a "crowd" of other users and passes requests to a random member of the crowd
- The member can either submit the request to the server or forward it to another randomly chosen member
- Identity of the initiator is hidden from external observers and other crowd members
- Pros: no single point of compromise, efficient implementations
- Cons: does not protect against a global adversary able to oversee all communications

## Tor (The Onion Routing Project)
- Practical solution for anonymity protection, free and open-source
- Combination of mix-network and crowd mechanisms
- Uses a set of relay nodes (crowd) and routing using random choice
- Encrypted connections between neighboring nodes using public-key cryptography
- Temporarily available virtual channels
- Traffic routed via encrypted nodes, with each node decrypting one layer of encryption
- Entry point known only by the first link, exit point known only by the last link, nodes aware only of the next link

Protecting privacy in the digital age requires a combination of technological solutions, legal frameworks, and user awareness. Anonymity techniques like mix-networks, crowds, and Tor help users maintain privacy by obscuring the connection between senders and recipients of messages. However, the aggregation of personal data from various sources remains a significant privacy threat that requires ongoing attention and solutions.