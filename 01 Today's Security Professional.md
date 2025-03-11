
 # Chapter 1 - Today's Security Professional

---

## Domain 1.0: General Security Concepts

**1.1. Compare and contrast various types of security controls.**

- Categories (Technical, Managerial, Operational, Physical)
- Control Types (Preventive, Deterrent, Detective, Corrective, Compensating, Directive)

**1.2. Summarize fundamental security concepts.**

- Confidentiality, Integrity, and Availability (CIA)
- Non-repudiation
- Gap analysis

**1.4. Explain the importance of using appropriate cryptographic solutions.**

- Obfuscation (Tokenization, Data masking)

## Domain 3.0: Security Architecture

**3.3. Compare and contrast concepts and strategies to protect data.**

- General data considerations (Data states, Data at rest, Data in transit, Data in use)
- Methods to secure data (Geographic restrictions, Encryption, Hashing, Masking, Tokenization, Obfuscation, Segmentation, Permission restrictions)

## Domain 5.0: Security Program Management and Oversight

**5.2. Explain elements of the risk management process.**

- Risk identification

---

# Cybersecurity Objectives

## CIA Triad

- **Confidentiality**
- **Integrity**
- **Availability**

- **Nonrepudiation** (cannot later deny having taken that action)

# Data Breach Risks 

- Security incidents occur when an organization experiences a breach of the CIA

## The DAD Triad

- **Disclosure**
	- Exposure of sensitive information to unauthorized individuals
	- Otherwise known as dataloss
	- Violation of **Confidentiality**
	- When remove data from the organizations are data exfiltration
- **Alteration**
	- Unauthorized modification of information
	- Violation of **Integrity**
- **Denial**
	- Disruption of an authorized user's legitimate access to information
	- Violate the **Availability**
	- DDoS attack comes from multiple source

## Breach Impact

- Financial
- Reputational
- Strategic
- Operational
- Compliance

### Financial Risk

- Monetary damage 
- Direct or indirect

### Reputational Risk

- Negative publicity
- Loss of trust

### Identity Theft

- The effect of breach often extend beyond the breached organization
- Risk of **identity theft** posed by the exposure of **Personally Identifiable Information (PII)**
	- Full name, address, credit card, driver license numbers...

### Strategic Risk

- Become less effective in meeting its major goals and objectives
	- Product development delays
	- Competitors gain access to data breached
	- Jeopardized the organization's ongoing viability

### Operational Risk

- Risk to carry out its day-to-day functions
	- Slow down business process
	- Inefficiency and delay

### Compliance Risk

- Run afoul of legal or regulatory requirements
	- HIPAA requires to protect CIA of protected health information (PHI)

### Risks Often Cross Categories

- In most cases, a risk will cross multiple risk categories

# Implementing Security Controls

- Security controls are specific measures that fulfill the security objectives
	- Analyzes risk environment
	- Technical and business leader determine the level of protection

## Gap Analysis

- Review the control objectives
- Examines the controls designed to achieve those objectives
- Where the controls do not meet the control objective, that is an example of a gap
- Should be treated as potential risks and remediated as time and resources permit

## Security Control Categories

- **Technical Controls**
	- Enforce CIA in the digital space
		- Firewall, ACL, IPS, encryption...
- **Operational Controls**
	- Manage technology in a secure manner
		- User access review, log monitoring, vulnerability management...
- **Managerial Controls**
	- Procedural mechanism
		- Periodic risk assessment, Security planning exercises...
- **Physical controls**
	- Controls that impact the physical world
		- Fences, perimeter lighting, locks...

## Security Control Types

- **Preventive controls**
	- Stop a security issue before it occurs
		- Firewall, Encryption
- **Deterrent controls**
	- Prevent an attacker from attempting to violate security policies
		- Guard dogs, barbed wire fences
- **Detective controls**
	- Identify security events that have already occurred
		- IDS
- **Corrective controls**
	- Remediate security issues that have already occurred
		- Restoring backups
- **Compensating controls**
	- Mitigate the risk
- **Directive controls**
	- Inform employees and other what they should do

>[!TIP] Know the various security control categories and types

## Exploring Compensating Controls

- Finds alternative means to achieve an objective when the organization cannot meet the original control requirement
- In many cases, to address a temporary exception to a security requirement

# Data Protection

- **Data at rest**
	- HD, tapes, cloud, or other storage media
- **Data in transit**
	- Motion/transit over a network
- **Data in use**
	- Actively in use, in memory

## Data Encryption

- Algorithms to protect information

### Data Loss Prevention

- DLP systems help enforce information handling policies and procedures
- Search unencrypted sensitive information and monitor traffic network
- Block traffic
- Apply encryption
- Agent-based (software on systems)
	- Can also monitor system configuration, user actions and blocking undesirable actions
- Agentless (Network-based)

- **Pattern matching**
	- Data formatted like credit card
	- Database of sensitive terms (Top Secret, Confidential...)
- **Watermarking**
	- Systems or administrator apply electronic tags

## Data Minimization

- Destroy data when it is no longer necessary
- De-identification
	- Removes the ability to link data back to an individual
- Data obfuscation
	- Hashing
	- Tokenization (lookup table)
	- Masking (replace some or all sensitive fields)

- **Rainbow table attack**
	- Checks to see if those hashes already exist

## Access Restrictions

- Geographic restrictions
	- Based on physical location
- Permission restriction
	- Based on the user's role or level of authorization

## Segmentation and Isolation

- Segmentation
	- Place sensitive systems on separate networks
	- They may communicate with each other but have strict restrictions
- Isolation
	- Completely cuts a system off from access to or from outside networks

# Exam Essentials

**The three core objectives of cybersecurity are confidentiality, integrity, and availability.**
- Confidentiality 
	- Unauthorized individuals are not able to gain access to sensitive information
- Integrity 
	- There are no unauthorized modification to information or systems, either intentionally or unintentionally
- Availability
	- Information and systems are ready to meet the needs of legitimate user at the time those users request them

**Non-repudiation prevents someone from denying that they took an action.**
-  Digital signatures
	- Allow to confirm that a message truly originated with its purported sender

**Security controls may be categorized based on their mechanism of action and their intent.**
- Controls categories
	- Managerial
	- Operational
	- Physical
	- Technical
- Control types
	- Preventive
	- Detective
	- Corrective
	- Deterrent
	- Compensating
	- Directive

**Data breaches have significant and diverse impacts on organizations.**
- Financial
- Reputational
- Strategic
- Operational
- Compliance

**Data must be protected in transit, at rest, and in use.**
- Encryption

**Data Loss Prevention (DLP) systems block data exfiltration.**
- Enforces information handling policies
- Search the presence of sensitive information
- Agent-based (host level)
- Agentless (network level)
- Pattern-matching and/or digital watermarking (tag)

**Data Minimization reduces risk by reducing the amount of sensitive information that we maintain.**
- Discard unnecessary information
- De-identification
- Data obfuscation
	- Hashing
	- Tokenization
	- Masking

#cybersecurity 