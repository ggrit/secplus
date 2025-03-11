# Chapter 2 - Cybersecurity Threat Landscape

---

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.1. Compare and contrast common threat actors and motivations.**

- Threat actors (Nation-state, Unskilled attacker, Hacktivist, Insider threat, Organized crime, Shadow IT)
- Attributes of actors (Internal/external, Resources/funding, Level of sophistication/capability)
- Motivations (Data exfiltration, Espionage, Service disruption, Blackmail, Financial gain, Philosophical/political beliefs, Ethical, Revenge, Disruption/chaos, War)

**2.2. Explain common threat vectors and attack surfaces.**

- Message-based (Email, Short Message Service (SMS), Instant messaging (IM))
- Image-based  
- File-based  
- Voice call  
- Removable device  
- Vulnerable software (Client-based vs. agentless) 
- Unsupported systems and applications 
- Unsecure networks (Wireless, Wired, Bluetooth) 
- Open service ports
- Default credentials
- Supply chain (Managed service providers (MSPs), Vendors, Suppliers)

**2.3. Explain various types of vulnerabilities.**

- Supply chain (Service provider, Hardware provider, Software provider)
- Zero-day

## Domain 4.0: Security Operations

**4.3. Explain various activities associated with vulnerability management.**

- Identification methods (Threat feed, Open-source intelligence (OSINT), Proprietary/third-party, Information-sharing organization, Dark web)

---

# Exploring Cybersecurity Threats

- Threat actors differ significantly in their skills, capabilities, resources, and motivation

## Classifying Cybersecurity Threats

>[!TIP] Every exam question ties back to a specific exam objective and the answer is most likely either found on this list or directly related to one of these attributes.

- Internal vs. External
- Level of Sophistication/Capability
	- Advanced Persistent Threat (APT)
- Resources/Funding
- Intent/Motivation

## The Hats Hackers Wear

- Authorized attackers (White Hat)
- Unauthorized attackers (Black Hat)
- Semi-authorized attackers (Grey Hat)
	- Without authorization, but with the intent of informing

## Threat Actors

>[!TIP] Be certain that you understand the differences between unskilled attackers, hacktivists, organized crime, advanced persistent threats (APTs), includiing nation-state actors; and shadow IT.

- Unskilled attackers
	- Script kiddie
- Hacktivist
	- Activist goal
- Organized Crime
	- Illegal financial gain
- Nation-State Attackers
	- APTs (Advanced Persistent Theats)
- Insider Threat
	- Employee, contractor, vendor...
- Competitors
	- Espionage
		- Search competitors data on darkweb

## Zero -Day Attacks

- APTs attackers try to discover new vulnerabilities to exploit
- No patches are available (unknown to product vendors)

## The Threat of Shadow IT

- Technology services that aren't approved by the organization
- No malicious intent
- Outside of the organizations control

## Attacker Motivations

- Data exfiltration
	- Obtain sensitive or proprietary information
- Espionage
	- Steal secret information from other organizations
- Service disruption
	- Take down or interrupt critical systems or network
- Blackmail
	- Extort money or other concessions
- Financial gain
	- Organized Crime
- Philosophical/political belief
	- Hacktivists
- Ethical 
	- Expose vulnerabilities and improve security
- Revenge 
	- Embarassing or exacting some other retribution
- Disruption/chaos
- War

>[!TIP] It is very likely you will be asked to compare and contrast the various threat actors on the exam. You should know the attributes and motivations behind each.

## Threat Vectors and Attack Surfaces

- Attack surface
	- System, application or service that contains a vulnerability
- Threat vector

### Message-Based Threat Vectors

- Email
- SMS
- Instant Messaging (IM)
- Social media

### Wired Networks

- Physically entering the organization's facilities
	- Public area, lobby, customer store
- Connect to unsecured network hack on the wall
- Unsecured computer 

### Wireless Network

- Sit in parking lot and access wireless network

### Systems

- OS configuration may expose open service ports
- Default credentials
- Software installed 

### Files and Images

 - Contains embedded malicious code

### Removable Devices

- USB

### Cloud

 - Files with improper access controls
 - Systems with security flaws
 - Accidentally published API keys and passwords

### Supply Chain

- Indirect mechanism to attack the organization
- Backdoors

>[!TIP] Be ready to identify and explain the common threat vectors and attack surfaces.

# Threat Data and Intelligence

- Set of activities and resources to learn about changes in the threat environment
- Can be used for predictive analysis
- OSINT (Open Source Intelligence)
- Threat feeds provide up-to-date detail about threats
- Vulnerability databases
- Also provide Indicators of Compromise (IoCs)

## Open Source Intelligence

- Public available sources
- SENKI
- MISP
- CISA
- SANS

## Proprietary and Closed-Source Intelligence

- Commercial security vendors
- Government organizations
- Other security-centric organizations

## Exploring the Dark Web

- Run over standard Internet connection
- Multiple layer of encryption to provide anonymous communication
- Searches data breached from organization

## When a Threat Feed Fails

- Is it critical to have reliable, up-to-date feeds
- You may want to have multiple feed that you can check against each other

## Assessing Threat Intelligence

- Timely? Accurate? Relevant?

### Assessing the Confidence Level of Your Intelligence

- Confirmed (90-100)
- Probable (70-89)
- Possible (50-69)
- Doubtful (30-49)
- Improbable (2-29)
- Discredited (1)

## Threat Indicator Management and Exchange

- Managing threat information requires standardization to be processed and used in automated ways
- Structured markup languages
	- STIX and OpenIOC

## Information Sharing Organizations

 - Threat intelligence communities
	 - Information Sharing and Analysis Centers (ISACs)

## Conducting Your Own Research

- Vendor security information websites
- Vulnerability and threat feeds from vendors, government agencies, and private organizations
- Academic journals and technical publications, such as Internet Request for Comments (RFC) documents
- Professional conferences and local industry group meetings
- Social media accounts of prominent security professionals
- Information on adversary
	- Tactics, Techniques, and Procedures (TTPs)

# Exam Essential

**Threat actors differ in several key attributes.**
- Internal/External
- Level of sophistication and capability
- Available resources and funding
- Different motivations and levels of intent

**Threat actors come from many different sources.**
- Unskilled, quite sophisticated or Advanced Persistent Threat (APTs)
- Hacktivist may seek to carry out political agendas
- Competitor may seek financial gain
- Employees and other users may pose an insider threat
- Shadow IT: systems, applications, or devices used without official approval from the IT department

**Attackers have varying motivations for their attacks.**
- Data exfiltration
- Espionage
- Service disruption
- Black mail
- Financial gain
- Philosophical or political beliefs
- Revenge
- Disruption and chaos
- War

**Attackers exploit different vectors to gain initial access to an organization.**
- Over the Internet
- Wireless connection
- Physical access
- Approach employees over email or social media
- USB memory stick
- Spread exploit through cloud services
- Supply chain

**Threat intelligence provides organization with valuable insight into the threat landscape.**
- Public or private sources
- Seek out detailed Indicator of Compromise (IoCs)
- Perform predictive analytics
- Open source and close source intelligence

**Security team must monitor for supply chain risks**
- Pay particular attention to risk posed by outsourced code development, cloud data storage, and integration between external and internal systems

#cybersecurity 