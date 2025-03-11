# Chapter 3 - Malicious Code

---

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.4. Given a scenario, analyze indicators of malicious activity.**

- Malware attacks (Ransomware, Trojan, Worm, Spyware, Bloatware, Virus, Keylogger, Logic bomb, Rootkit)

---

# Malware

- Wide range of malicious software

>[!TIP] Know the distinctive characteristics of each type of malware, and what might help you tell them apart. Pay attention to the differences between each type of malware, what common indicators of compromise are associated with them.

### Ransomware

- Demands a ransom
- Crypto malware
- IoCs
	- C&C to know malicious IP
	- Legitimate tools in abnormal way
	- Lateral movement
	- Encryption of files
	- Notices with demands for ransom
	- Data exfiltration behaviors, large file transfer
- Defence
	- Backup separate location

### Trojans

- Disguised as legitimate software
- Provides user and device information to C&C and then downloads additional malicious plugins
- IoCs
	- Signature for the specific malware
	- C&C system hostname and IP
	- Folders or files created on target device
- **RATs**: Remote Access Trojans
	- Provide remote access to systems
	- Some legitimate remote access tools
		- Make difficult to identify
- Defence
	- Endpoint detection and Response (EDR)
	- Anti-malware
	- Attention to software and application source

### Bots, Botnets, and Command and Control

- Command & Control (C&C)
- Botnet
	- Groups of systems under central command
- Bot
	- Individual system 

### Worms

- Spread themselves on networks
- Self-install
- Spread by
	- Email attachments
	- Network file shares
	- IoT
	- Phone
- IoCs
	- Known malicious files
	- Download of additional components from remote system
	- C&C contact to remote systems
	- Malicious behaviors using system commands for injection
	- Hands-on-keyboard attacker activity
- Defence
	- Network level controls
	- Firewall
	- IPS
	- Segmentation
	- Anti-malware
	- Endpoint Detection and Response (EDR)

### Spyware

- Obtain information about user or system
- Track users browsing habits
- Spy installed software
- Associated with
	- Remote access to web cameras
	- Identity theft and fraud
	- Advertising and redirection of traffic
	- Digital Rights Management (DRM) monitoring
- Stalkerware
	- Illicitly monitor partners
- Defence
	- Anti-malware/anti-spyware
	- User awareness
- IoCs
	- Remote-access and remote-control-related indicators
	- Known software file fingerprints
	- Malicious processes, often disguised as system processes
	- Injection attacks against browser

### Bloatware

- Unwanted application, usually preinstalled
- Usually isn't malicious
- Adding another attack surface
- May call home with information about your system or usage
	- Spyware

>[!TIP] Spyware's primary intention is to gather information about user, their use of the system and Internet, and the configuration of the system. whereas bloatware is simply unwanted programs.
>

### Viruses

- Malicious programs that self-copy and self-replicate once activated
- Don't spread themselves
- Infect only local system
- Require user action
- Trigger
	- Set the conditions for when the virus will execute
- Payload
	- What the virus does, delivers, or the actions it permors
- Many varieties
	- Memory-resident
	- Non-memory-resident
	- Boot sector
	- Macro viruses
	- Email
- Fileless virus
	1. Spam email
	2. Malicious website exploit browser vulnerability
	3. Download and execute payload
	4. Payload runs in memory
	5. No local storage usage
- Defence
	- IPS
	- Awareness
	- Anti-malware
- IoCs
	- Available in threat feeds
		- VirusTotal

### Keyloggers

- Capture keystrokes from a keyboard
- Other input such as
	- Mouse movement
	- Touchscreen inputs
	- Credit card swipes
- IoCs
	- File hashes and signatures
	- Exfiltration activity to C&C systems
	- Process names
	- Known reference URLs
- Software or hardware

### Logic Bombs

- Not independent malicious programs
- Functions or code placed inside other programs
- Activate when set conditions are met
- Require analysis of the code or logic in the application

## Analyzing Malware

- Online analysis tool
	- VirusTotal
- Sandbox to analyze malware behavior
- Manual code analysis
- Using tool
	- Strings

### Rootkits

- Allow access through a backdoor
- IoC
	- File hashes and signature
	- C&C domain, IP, and systems
	- Behavior-based
		- New services
		- Executables
		- Configuration changes
		- File access
		- Command invocation
		- Opening ports or creation of reverse proxy tunnel
- One technique to find them is to remove the drive and connect to another system

# Exam Essentials

**Understand and explain the different types of malware.**
- What identifies each type of malware, what controls are deployed, what to do
- Ransomware
- Trojans
- Worms
- Spyware
- Bloatware
- Viruses
- Keylogger
- Logic Bombs
- Rootkits

**Explain common indicators of malicious activity associated with malware types.**
- Indicators of compromise (IoCs)
	- C&C traffic patterns
	- IP
	- Hostname
	- Domains
	- Use of systems utilities in unexpected way
	- Lateral movement
	- Creation of file and directories
	- Encryption of files
	- Data Exfiltration
	- Signatures

**Understand the methods to mitigate malware.**
- Manual removal
- Tools
- Reinstallation
- Restoration from backup

#cybersecurity 