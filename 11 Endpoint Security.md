# Chapter 11 - Endpoint Security

---

## Domain 1.0:  General Security Concepts

**1.4. Explain the importance of using appropriate cryptographic solutions.**

- Tools (Trusted Platform Module (TPM), Hardware security module (HSM), Key management system, Secure enclave)

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.3. Explain various types of vulnerabilities.**

- Operating system (OS)-based
- Hardware (Firmware, End-of-life, Legacy)
- Misconfiguration

**2.5. Explain the purpose of mitigation techniques used to secure the enterprise.**

- Patching
- Encryption
- Configuration enforcement
- Decommissioning
- Hardening techniques (Encryption, Installation of endpoint protection, Host-based firewall, Host-based intrusion prevention system (HIPS), Disabling ports/protocols, Default password changes, Removal of unnecessary software)

## Domain 3.0 Security Architecture

**3.1. Compare and contrast security implications of different architecture models.**

- Architecture and infrastructure concepts (IoT, Industrial control systems (ICS)/supervisory control and data acquisition (SCADA), Real-time operating system (RTOS), Embedded systems)

## Domain 4.0 Security Operations

**4.1. Given a scenario, apply common security techniques to computing resources.**

- Secure baselines (Establish, Deploy, Maintain)
- Hardening targets (Workstations, Servers, ICS/SCADA, Embedded systems, RTOS, IoT devices)

**4.2. Explain the security implications of proper hardware, software, and data asset management.**

- Acquisition/procurement process
- Assignment/accounting (Ownership, Classification)
- Monitoring/asset tracking (Inventory, Enumeration)
- Disposal/decommissioning (Sanitization, Destruction, Certification, Data retention)

**4.4. Explain security alerting and monitoring concepts and tools.**

- Tools (Antivirus, Data loss prevention (DLP))

**4.5. Given a scenario, modify enterprise capabilities to enhance security.**

- Operating system security (Group Policy, SELinux)
- Endpoint detection and response (EDR)/extended detection and response (XDR)

---

# Operating System Vulnerabilities

- OS vulnerabilities
- Default password and insecure settings
- Configuration can introduce vulnerabilities
- Misconfiguration

>[!TIP] Exam outline is vague about OS-based vulnerabilities. As you're studying, you'll want to think about how your choice of OS, its defaults, security configuration, and support model all impact your organization's security.

# Hardware Vulnerabilities

- Challenging or even impossibile to deal with directly
- Compensating controls can limit the impact 

>[!TIP] Test takers should be able to explain various types of vulnerabilities, including hardware vulnerabilities related to firmware, end-of-life hardware, and legacy hardware.

- **Firmware**
	- Embedded software
	- May or not be possible to update
	- Attacks
		- Executable updates
		- Download malicious update that appears to be legitimate
		- Remote network-enabled updates
	- Important tool
		- Firmware validation

- **End-of-life or legacy hardware**
	- Lack of support
	- Vendor terms
		- End of sales
			- Last date at will be sold, often remain in the supply chain
		- End of life
			- No longer sold, on a patch to retirement, but it has some usable lifespan left
		- End of support
			- Last date support and/or updates
		- Legacy
			- Unsupported

# Protecting Endpoints

## Preserving Boot Integrity

- If untrusted or malicious components are inserted into the boot process, the systems cannot be trusted
- UEFI firmware can leverage two different techniques
	- **Secure boot**
		- Only software that the Original Equipment Manufacturer (OEM) trusts
		- The system have database **listing the secure signatures of trusted software and firmware**
	- **Measured boot**
		- Measure each component
			- Starting with the firmware and ending with the boot start drives
		- It relies on the UEFI firmware
			- To **hash firmware, bootloader, drivers, and anything else** is part of the boot process
		- **Data gathered** is store in the **Trusted Platform Module (TPM)**
			-  And the logs can be **validated remotely to let security administrators know the boot state** 
- **Hardware root of trust**
	- Contains the **cryptographic keys** that secure the boot process
	- Common implementation
		- **TPM chip** built into many computers
			- Provide build-in encryption
			- Remote attestation, allowing hw and sw configurations to be verified
			- Binding, which encrypts data
			- Sealing, which encrypts data and sets requirements for the state of the TPM chip before decryption 
	- Other implementation
		- **Serial numbers** that cannot be modified or cloned
		- Physically Unclonable Functions (PUF)
			- HW that provide a **unique identifier or digital fingerprint**
			- Based on the unique features of a microprocessor that are created when it is manufactured and is not intentionally created or replicated 
- **Secure Enclave**
	- Dedicated secure element that is **build into system-on-chip (SoC)**

## Protecting the Keys to the Kingdom

- Hardware Security Modules (HSM)
	- Typically external devices or plug-in card
	- Used to **create, store, and manage digital keys**
		- For cryptographic solutions and authentication, as well as to offload cryptographic processing
	- Used in high-security environments
	- Certified
		- FIPS 140 or ISO/IEC 15408

	- Cryptographic **Key Management Systems** (KMS)
	- Store key and certificates
	- **Manage them centrally**
	- Cloud providers provide KMS as a service

>[!TIP] Keep in mind the roles that TPM, HSM, key management services (KMS) and secure enclaves play in system security and organization operations.<br> Remember that TPM are used for system security; <br>HSM are used to create, store and manage keys for multiple systems; <br>KMS is a service used to manage secrets.

## Endpoint Security Tools

### Antivirus and Antimalware

- **Signature-based** detection
	- Hash or pattern-based signature
- **Heuristic-based, or behavior-based** detection
	- Actions the malicious software takes and matches them to profiles of unwanted activities
	- Can identify new malware based on what it is doing
- **Artificial Intelligence (AI) and Machine Learning (ML)**
	- Large amounts of data to find way to identify malware
	- Include heuristic, signature, and other detection capabilities
- **Sandboxing**
	- Isolate and run sample malicious code
	- Protected environment

### Allow Lists and Deny Lists

- Control application that can be installed or used

>[!TIP] Exam uses the terms allow list and deny list or block list. You may also still encounter the terms whitelist used to describe allow lists and blacklist used to describe deny or block lists, since these terms have been in broad use, and changing terminology across the industry will take some time.

### Endpoint Detection and Response and Extended Detection and Response

- **Endpoint Detection and Response (EDR)**
	- Tools combine monitoring on endpoint devices and systems
	- Client or software agents
	- **Network monitoring and log analysis**
		- Collect, correlate, and analyze events
	- **Search and explore the collected data and to use it for investigations** as well and ability to **detect suspicious data** 
	- Look for anomalies and Indicators of Compromise (IoC)
	- Detection and reporting for organization that are dealing with very large quantities of security data

- **Extended Detection and Response (XDR)**
	- Not only endpoints but the full breadth of technology stack
		- Cloud services, security services and platforms, email, and similar components
	- Logs and other information from the broad range of components
	- Detection algorithms, AI, ML to analyze the data to find issue

### Data Loss Prevention

- DLP tools
	- Deployed to endpoints in form of clients or applications
	- Network and server-resident components to ensure that data is managed throughout its life cycle and various handling processes
	- Ability to classify data so know which data should be protected
		- Data labeling or tagging functions, to support classification and management practices
		- Policy management and enforcement functions used to manage data
		- Monitoring and reporting capabilities
			- To notify administrators or security practitioners
	- Additional function
		- Encrypt data when it is sent outside
		- Tokenizing, wiping, or modifying data to permit it's use without violation
		- Track user behaviors to identify questionable behavior or common mistake
	- Mapping data
		- Data classification system or policy

>[!TIP] Exam outline leans into detection tools via EDR and its broad-based relative, XDR. EDR or XDR is increasingly found in most organizations due to the significant threats posed by ransomware and other malicious software that exceed the capabilities of traditional antivirus to counter. You'll also need to know about Data Loss Prevention (DLP) as a tool to ensure that data doesn't leave the organization.

### Network defenses

- **Host-based firewalls**
	- Built-in in most OS and enabled by default
	- Simply block or allow
		- Application, services, ports, or protocols

- **Host-based Intrusion Prevention System (HIPS)**
	- Analyzes traffic before services or applications on the host process it
	- Can **take action on that traffic**
		- Filtering or blocking
	- Look multiple packets or an entire series of communications
	- Misconfiguration can block legitimate traffic 

- **Host-based Intrusion Detection System (HIDS)**
	- **Cannot take action to block traffic**
	- Can **report and alert**

# Hardening Techniques 

## Hardening 

- Changing settings to increase level of security
- Hardening tools and script
	- Organizations provide guides
		- Center for Internet Security (CIS)
		- National Institute of Standards and Technology (NIST)

>[!TIP] Exam outline lists encryption, installing endpoint protection, host-based firewalls and host-based IPS, disabling ports, and protocols, changing default passwords, and removing unnecessary software as key hardening items you should be able to explain.

## Service Hardening

- Disabling ports and protocols
- Using firewall or better disable them entirely

| **Port**    | **Protocol** | **Service**                   | **Windows**      | **Linux**        |
| ----------- | ------------ | ----------------------------- | ---------------- | ---------------- |
| **22**      | TCP          | Secure shell (SSH)            | Uncommon         | Common           |
| **53**      | TCP and UDP  | DNS                           | Common (servers) | Common (servers) |
| **80**      | TCP          | HTTP                          | Common (servers) | Common (servers) |
| **125-139** | TCP and UDP  | NetBIOS                       | Common           | Occasional       |
| **389**     | TPC and UDP  | LDAP                          | Common (servers) | Common (servers) |
| **443**     | TCP          | HTTPS                         | Common (servers) | Common (servers) |
| **3389**    | TCP and UDP  | Remote Desktop Protocol (RDP) | Common           | Uncommon         |

>[!TIP] You should understand the concept fo disabling services to reduce the attack surface of systems and that ongoing review and maintenance is required to ensure that new services and applications do not appear over time.

## Network Hardening

- Virtual Local Area Network **(VLAN)**
	- **Segment** different trust levels, user groups or system
	- For guest networks
	- Isolate VoIP

## Default Passwords

- Changing default password
- Vulnerability scanners will note default passwords

## Removing Unnecessary Software

- Removes the potential for a disabled tool to be reenabled
- Reduces amount of patching and monitoring

# Operating System Hardening

- Changing settings to match the desired security stance
- Reduce attack surface
- Tool and scripts can help
- CIS benchmarks for Windows
	- Password history to remember 24 or more passwords
	- Maximum passwords age to "365 or fewer day, but not 0" preventing users from simply changing their passwords 24 times to get back to the same password while requiring password changes every year
	- Minimum password length to 14 or more characters
	- Requiring password complexity
	- Disabling the storage of passwords using reversible encryption

### Hardening the Windows Registry

- Is the core how Windows tracks what is going on
- Important target
	- Can automatically start programs
	- Gather information
	- Take malicious action
- Hardening
	- Configuring permissions
	- Disallow remote access
	- Limiting access

### Windows Group Policy and Hardening

- Windows **Group Policy** 
	- Provide control settings through **Group Policy Objects (GPO)**
		- Wide range of options
		- Disabling guest accounts
		- Setting password minimum lengths
		- Restricting software installation
	- Locally or via Active Directory

- Microsoft provides
	- Security Compliance Toolkit (SCT)
		- Set of tools 
		- Security configuration
		- Windows and other Microsoft applications

### Hardening Linux: SELinux

- SELinux (Security-Enhanced Linux)
	- Linux kernel-based security module
	- On top of existing Linux distributions
- Capabilities
	- Mandatory Access Control (MAC)
		- Enforced at the user, file, system service, and network layer 
		- Least privilege-based security implementations
	- Enforces user right
		- Based on a username, role, and type or domain for each entity
	- Files and other resources like network ports are labeled
		- Using name, role, and type

## Configuration, Standards, and Schemas

- Configuration management tools
	- Help enforce standards, manage systems, and report 
	- Start with **baseline configuration**
		- **Establishing** a baseline
			- Often done using an existing industry standard like the CIS benchmark with modification and adjustments to fit
		- **Deploying** using central management tools or even manually
		- **Maintaining** using central management tools and enforcement capabilities as well as making adjustments
	- **Configuration enforcement**
		- Not only monitors for changes but makes changes to system configurations as needed

### Patching and Patch Management

- Ensuring that systems and software are up to date
- Timely **patching**
	- Decreases exploits and flaws
	- Also have risks
		- May introduce new flaws or cause issue
- Patch management
	- Control and manage
- Systems management tool
	- Tracking versions and patch status
- Common practice for organization
	- Delay the installation for a period of few days from its release
		- Third-party hopefully providing insight into any issues the patch may create

- Mobile device management tools
	- Managing software for mobile devices
	- Validate software version
	- Update applications
	- Apply patches and software updates
	- Controlling security settings

## Encryption

- Protects data if system or disk is lost or stolen
- **Full-disk encryption (FDE)**
	- Requires that the bootloader or a hardware device provide a decryption key 
	- Software or hardware to decrypt the drive for use 
	- Common implementation
		- Transparent encryption (on-the-fly, or real-time encryption)
	- Implemented at the hardware level
		- Using Self-encrypting Drive (SED)
			-  Require a key to boot from the drive
- **Volume encryption** (filesystem-level encryption)
	- Protects specific volumes
	- Allowing **different trust levels**
	- Additional security beyond that provided by encrypting the entire disk with a single key
	- File and Folder encryption
		- For specific data
- Potential downfalls
	- Lost key
	- Dara corruption or other issue can have a lager impact

# Securing Embedded and Specialized Systems

## Embedded Systems

- Real-time Operating System (RTOS)
	- Priority on processing data as it comes in
- Common issue
	- Default configurations or password
	- Vulnerabilities
	- Lack of patching
## SCADA and ICS

- Industrial Controls System (ICS)
	- Broad term for industrial automation
- Supervisory Control and Data Acquisition (SCADA)
	- Refers to large systems
- Interchangeably terms

- SCADA system (Control and monitoring)
	- Remote Telemetry Unit (RTU)
	- Programmable Logic Controller (PLC)
- Common in industrial and manufacturing environments
- Designed without security in mind
	- **Isolating and protecting** is one of the most effective security measures

## Securing the Internet of Things 

- Type of embedded systems
	- Technologies like Machine Learning, AI, Cloud services, and similar "smart" features
- Poor security practices
	- Default settings
	- Lack of network security (firewalls)
	- Exposed or vulnerable services
	- Lack of encryption for data transfer
	- Weak authentication
	- Embedded credentials
	- Insecure data storage
	- ...and other
- Short support lifespans
	- May not be patched or updated
- Vendor data-handling practice issues

>[!TIP] For the exam consider how you would secure IoT, embedded devices, SCADA and ICS, and similar devices. Make sure you're aware of the challenges of protecting low-power, specialized devices that may not receive patches or support and that can have very long lifespans.

## Communication Considerations

- Many embedded and specialized systems
	- Operate where traditional wired and wireless network aren't available
- Embedded systems need to be secured so that the **cellular network** does not pose a threat
	- Not expose vulnerable service or application via their cellular connections
	- Prevent network exploits
	- Physical securing the SIM
		- SIM removed and repurposed
		- SIM cloning
- Radio frequency protocols
	- Zigbee, Zwave...
	- Do not have strong security models

## Security Constraints of Embedded Systems

- Overall computational power and capacity is usually low
	- No or little compute power for cryptographic processing
	- No additional tools like firewall, antimalware...
- May not connect to a network
	- So inability to patch, monitor, or maintain the devices remotely
	- May need to be secured as an independent unit
- Authentication is also likely to be impossible
	- Other security models need to be identified
- Compensating controls or special design to ensure that the device remain secure
- Implied trust model
	- Physical access

# Asset Management

- Asset
	- Hardware
	- Software
	- Data
- **Asset inventory** and tracked though their lifespan
	- Management tool
- Identify owners or managers for devices, systems, software, and data
- Classification efforts
	- Data
	- Systems
- Knowing systems contains, processes, and sensitive data 

>[!TIP] Exam outline mentions "enumeration" as well as asset inventory. Enumeration is typically associated with scanning to identify assets, and some organizations use port and vulnerability scans to help identify systems that aren't part of their invetory.

- If not maintain asset inventories
	- Difficult to know what the organization has
	- What missing or lost
	- Where things are
	- Assets may be uncontrolled and invisible
	- Incident happened and nobody knew

## Decommissioning

- Systems and devices are at the end of life cycle
- Decommissioning
	- Remove a device or system from service
	- Remore from inventory
	- Ensuring that no sensitive data remains on the system
		- Dealing with storage media or drive
		- Also entire device or removable media
	- Ensuring disk is **securely wiped** 
	- Sanitizing drives or media
		- Wiping the data
		- Destroying the media

- Tapes and similar magnetic media
	- Wiped using a degausser
		- Strong electromagnetic fields 
	- Scrambling the patterns of bits

- Wiping media overwrites or discards the data in a nonrecoverable way
	- For HD or other magnetic media
		- Series of writes, typically 1s and 0s 

- SSD and other flash media
	- Uses wear-leveling algorithms to spread wear and tear on the drive over more space than the listed capacity
		- Using traditional drive wipe utility that writes to all accessible location will miss sections of the disk where copies of data may remain due to the wear-leveling process
	- Built-in tools have secure Erase command that can help make sure remnant data is not an issue
	- Use full-disk encryption for full life of a drive
		- Then simply discard the encryption key

- Destroying drives is a popular option
	- Shredding, pulverizing, or incinerating 

- Certification
	- What assets were decommissioned
	- Certification process for vendors who destroy devices and media
	- Certificate of destruction

## Retention

- May be required for legal purposes
- Set retention periods determined by law
- Business purpose, compliance or audit component

# Exam Essentials

- **Understand OS and HW vulnerabilities.**
	- Operating Systems
		- Host vulnerable services or applications
		- Weak or insecure configurations
		- Patching
		- Configuration management
		- Security baselines
	- Hardware
		- Firmware update
		- Life cycle management
		- Legacy

- **Hardening and protecting systems relies on security tools and technology to keep systems secure.**
	- Considering the entire device
		- How it boots
		- How data is secured
		- Hot it is configured
		- What services it provides
		- If its communications are secure
		- How it is protected against network threats
	- Wide range of tools
		- Trusted boot
		- Antivirus
		- Antimalware
		- EDR
		- XDR
		- Data Loss Prevention
	- Network security tools
		- Host Intrusion Prevention System (HIPS)
		- Host Intrusion Detection System (HIDS)
		- Host Firewalls

- **Hardening endpoints also relies on configuration, settings, policies, and standards to ensure system security.**
	- Tools and technology are import to protect endpoints
	- Configuration and settings are also important part of the process
		- Disabling unnecessary services
		- Changing default passwords
		- Applying settings in the Windows Registry
		- Operating systems settings in Linux
		- Build-in and add-on configuration option to match security configuration
		- Patch management for OS and applications

- **Specialized systems like SCADA, ICS, and IoT systems exist throughout your organization and require unique security solutions.**
	- SCADA and ICS or industrial control systems
		- Are used to manage and monitor factories, power plants, and manu other major components of modern companies
	- IoT systems	
		- Internet-connected devices that perform a wide variety of tasks
		- From monitoring to home automation and more

- **Explain the importance of asset management for software, data, and hardware.**
	- Asset must be managed from acquisition through their life cycle 
	- Until disposal or decommissioning
	- Ownership and classification are maintained and tracked
	- Inventories of assets are up to date and include appropriate information to support operations, security and incident response needs

- **Drive encryption and sanitization help prevent data exposure.**
	- Encrypting drives and media helps keep them secure
		- If they are stolen or lost
	- Full-disk encryption covers the entire drive
	- Volume- or file-encryption protects portions of the contents
	- Sanitizing drives and media
		- Wiping them using a secure deletion process
		- Or their destruction to ensure that the data cannot be recovered
	- Using appropriate process based on the security requirements for the data and the type of drive or media 

#cybersecurity 