# Chapter 4 - Social Engineering and Password Attacks

---

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.2. Explain common threat vectors and attack surfaces.**

- Human vectors/social engineering (Phishing, Vishing, Smishing, Misinformation/disinformation, Impersonation, Business email compromise, Pretexting, Watering hole, Brand impersonation, Typosquatting).

**2.4. Given a scenario, analyze indicators of malicious activity.**

- Password attacks (Spraying, Brute force)

---

# Social Engineering and Human Vectors

- Key principles
	- Authority
	- Intimidation
	- Consensus-based
	- Scarcity
	- Familiarity-based
	- Trust
	- Urgency

>[!TIP] The exam doesn't expect you to be able to categorize attacks based on the principle they rely on, but those principles are extremely helpful as a tool to think about why an attack might succeed and how it can be prevented or limited.

## Social Engineering Techniques

### Phishing

- Fraudulent acquisition of information
- Often via email
- **Spear phishing**
	- Targets specific individuals or groups
- **Whaling**
	- Big fish phishing
- Awareness

### Vishing

- Voice or voicemail messages phishing
- Rely on phone calls, urgency

### Smishing

- SMS
- Rely on clicking link in a text message

### Misinformation and Disinformation

- **Misinformation**
	- Incorrect information without malice
- **Disinformation**
	- Incorrect information intentionally

### Impersonation

- Pretending to be someone else
	- Identity fraud/theft
- Specific or non-specific identity

### Business Email Compromises

- Often called **BEC** (or EAC: Email Account Compromise)
- Relies on using apparently legitimate email
- Scams or other attacks
	- Invoice scams
	- Gift card scams
	- Data theft
	- Account compromise/account access attacks
- Multiple methods
	- Using compromised accounts
	- Sending spoofed emails
	- Using common fake but similar domain techniques
	- Using malware or other tools
- Mitigation methods
	- Multi-factor authentication
	- Awareness
	- Policies

### Pretexting

- Justify why you are approaching an individual
- Made-up scenario
- Make impersonator more believable

### Watering Hole Attacks

- Use website that targets frequent to attack them
	- Compromising it

### Brand Impersonation

- Or brand spoofing
- Commonly uses email that are intended to appear to be from a legitimate brand
	- Rely on name recognition
	- Using email templates used by the brand itself
- Attempts to get users to log into their existing accounts
- May request payment
- Gather password or other sensitive information
- Attach malware

### Typosquatting

- Misspelled and slightly off but similar to the legitimate site URL
- **Pharming** changing systems *hosts* file to change IP from hostname

# Password Attacks

- Brute-force
	- Trying different password until it succeeds
	- Words specifically picked or variation of common password
- Password spraying
	- Single or small set of password agains many accounts
	- Effective when targeting default passwords or context-specific terms related to the target.
- Dictionary attacks
	- Uses a wordlists (dictionaries)

>[!TIP] Exam focus on just two types of password attacks: spraying and brute force. Dictionary attacks and the use of rainbow tables remain common as well.

- *Rainbow table* 
	- Database of precomputed hashes

# Exam Essentials

**Many techniques are used for social engineering.**
- Phishing
	- Smishing
	- Vishing
	- Whaling
- Misinformation & disinformation
- Impersonation
- Pretexting
- Business Email Compromise (BEC)
- Brand Impersonation
- Watering hole attacks
- Typosquatting

**Passwords can be acquired and cracked in many ways.**
- Brute-force
- Password spraying
	- One or small set of password for multiple account
- Dictionary attacks
- Password cracker
	- John the Ripper

#cybersecurity 