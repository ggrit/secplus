# Chapter 15 - Digital Forensics

---

## Domain 4.0: Security Operations

**4.8. Explain appropriate incident response activities.**

- Digital forensics (Legal hold, Chain of custody, Acquisition, Reporting, Preservation, E-discovery)

---

# Digital Forensic Concepts

- Digital forensics
	- Responding to legal cases
	- Conducting internal investigations
	- Support incident response processes

- Key element of digital forensics
	- Acquisition and analysis of digital forensic data
		- Data can be in form of
			- Drives, files, copies of life memory, and any of the other multitude of digital artifacts
	- Since forensic information can be found in many different places
		- Planning forensic information gathering is crucial

- The creation of documentation
	- What you have observed
	- What conclusions can be made from data
	- What evidence exists to support those conclusions 
	- Timelines and sequences of events 
	- Looking for clues
	- What occurred and why
	- Use time stamps, file metadata, event logs, and multitude of clues to piece together a complete picture

- The human side
	- Interviews with individuals involved in the activity

## Legal Holds and e-Discovery

- Forensics starts when litigation is pending or is anticipated
- Legal counsel can send a **legal hold** or litigation hold
	- **Notice that informs an organization that they must preserve data and records**
		- That might be destroyed or modified in normal operations
	- Backups, paper documents, and electronic files of all sorts must be preserved

- Key concept for legal hold and preservation 
	- Is **"spoliation of evidence"**
		- Which means intentionally, recklessly, or negligently altering, destroying, fabricating, hiding, or withholding evidence relevant to legal matters 
	- Legal hold 
		- Gives a notice that they must preserve that data
	- Ignoring the notice or mishandling data
		- Can be a negative blow against an organization in court
	- Strong legal hold process is important before a hold shows up

- Legal holds
	- First part of an electronic discovery or **e-discovery** process
- Discovery process
	- Allow each side of a legal case to obtain evidence from each other and other parties involved in the case
- E-discovery
	- Electronic discovery process 
- In addition to legal cases
	- Discovery processes are also used for 
		- Public records, Freedom of Information Act request and investigations

- E-discovery framework
	- **Electronic Discovery Reference Model (EDRM)**
		1. **Information governance**
			- Before the fact to assess what data exists and to allow scoping and control of what data needs to be provided
		2. **Identification of electronically stored information**
			-  So that you know what you have and where it is
		3. **Preservation of the information**
			- To ensure that it isn't changed or destroyed
		4. **Collection of the information**
			- So that it can be processed and managed as part of the collection process
		5. **Processing of the data**
			- To remove unneeded or irrelevant information, as well as preparing it for review and analysis by formatting or collating it 
		6. **Review of the data**
			- To ensure that it only contains what it is supposed to, and that information that should not be shared is not included
		7. **Analysis of the information**
			- To identify key elements like topics, terms, and individuals or organizations
		8. **Production of data to provide**
			- The information to third parties or those involved in legal proceedings
		9. **Presentation of the data**
			- Both for testimony in court and for further analysis with experts or involved parties

- Preservation of electronic information
	- Tools with abilities to capture data
		- Often come with desktop, mobile device, and server *agents*
			- Can gather data, track changes, and document appropriate data handling throughout the legal hold time frame

- Cloud operations have made e-discovery even more complex
	- Cloud vendors will not permit you to place an intrusive legal hold and discovery agent in their cloud service
	- Must address how you would deal with legal holds for those services

>[!TIP] Exam outline focuses on legal holds, chain of custody, and e-discovery-related activities in very broad terms. You should be prepared to explain each of these as well as how they are related to incident response.

# Conducting Digital Forensics

- Forensic tools
	- Disk and memory imagers
	- Image analysis and timelining tools
	- Low-level editors 
		- Can display detailed information about the contents and structure of data on a disk
	- Other specialized tools

## Acquiring Forensic Data

- **The order of volatility**
	- Document what data is most likely to be lost due to system operations or normal processes
- Is important to remember which items will disappear when a system is powered down or rebooted
	- In general, that occurs at position 4

**From most volatile to least**
1. CPU cache and registers
2. Routing table, ARP cache, process table, kernel statistics 
3. System memory - RAM
4. Temporary files and swap space
5. Data on the hard disk
6. Remote logs
7. Backups

- Common forensics locations
	- **CPU cache and register**
		- Rarely directly captured
		- Capture using specialized hardware or software
			- Most investigations do not need this level of detail
		- CPU cache and registers are constantly changing as processing occurs
			- Volatile
	- **Process table, kernel statistics, the system's ARP cache, and similar**
		- Captured through a combination of memory and disk acquisition 
		- The capture will only be of the moment in time when the acquisition is done
	- **The Random Access Memory (RAM)**
		- Can be very helpful for both investigations and incident response
		- Can contain
			- Encryption keys
			- Ephemeral data from applications
			- Information that may not be written to the disks but that can be useful to an investigation
	- **Swap and pagefile information**
		- Disk space used to supplement physical memory
		- Like capturing information from RAM
			- Swap and pagefile insight into running process
		- Actively used by the system
			- Changes more quickly than many files on disk
	- **Files and data on disk**
		- Change more slowly
			- But are the **primary focus of many investigations**
		- Important to capture the entire disk
	- **Operating System**
		- **Windows Registry** is a common target for analysis
			- Since many activities in Windows modify or update the Registry
	- **Devices such as smartphone, tablets, IoT devices, and embedded or specialized systems**
		- May contain data that can also be forensic targets
	- **Firmware**
		- Less frequently targeted forensic artifact
		- But can be necessary if the firmware was modified as part of an incident
			- Or may have forensically relevant data
		- Often accessible using a hardware interface
			- Serial cable or direct USB connection or via memory forensic techniques
	- **Snapshots from VM**
		- Increasingly common artifact that forensic pratitioners must deal with
	- **Network traffic and logs**
		- Can provide detailed information or clues
			- About what was sent or received, when, and via what port and protocol, among other useful details
	- **Artifacts**
		- Like devices, printouts, media, and other items related to investigation can all provide additional useful forensic data

- **Chain-of-custody** documentation
	- If the forensic case may result in a legal case
	- Forms are simple sing-off and documentation forms
	- Each time the drive, device, or artifact is accessed, transferred, or otherwise handled
		- It is documented 

- Evidence in court cases is typically legally admissible
	- Offered to prove the fact of a case
	- Not violate the law
- To determine if evidence is admissible
	- Relevance and reliability
	- Obtained legally
	- Authentic
- Must be the best evidence available
- Process and procedures should stand up to challenges in court

- **Admissibility** for digital forensics
	- Data intact and unaltered
	- Have provably remained unaltered before and during the forensic process
	- Analysts must be able to demonstrate that they have appropriate skills
		- Appropriate tools and techniques
		- Documented their actions in a reliable and testable way 
			- Via an auditable trail
		- Their efforts and findings must be repeatable

## Preventing Malicious USB Cloning and Data Acquisition

- Obtain data from devices isn't restricted to legitimate uses
- Organizations that face targeted attacks
	- Focus on access to their devices 
		- When those devices are plugged into untrusted or unknown USB chargers and cables
- USB data blockers
	- Prevent USB data signals from being transferred 
	- Allowing USB charging

### Cloud Forensics

- **Right-to-audit clauses**
	- Part of the contract between the cloud service and an organization
	- Ability to audit the cloud provider
	- Agreement to use a third-party audit agency
	- Standard contracts not agree for smaller organizations
		- Instead provide access to regularly updated third-party audit statements
	- If specific audit requirements
		- Address them in contract if possible

- **Regulatory and jurisdiction concerns in the adoption of cloud services**
	- Regulatory requirements 
		- Depending on where the cloud service provider operates and where it is headquartered
		- The law that covers your data, services, or infrastructure may not be the laws that you have in your locality, region, or country.
	- Jurisdictional concerns
		- May extend beyond which laws cover the overall organization
	- Cloud provider
		- Sites around the world
			- Data replication and other services elements
				- Mean that your data or services may be stored or used in a similarly broad set of locations
		- Local jurisdictions
			- May claim rights to access that data
				- With a search warrant or other legal instrument
			- Organization with significant concerns about this
				- Address them with contractual terms
				- Host data or systems in specific areas or countries 
				- Technical controls such as handling their own encryption keys
					- To ensure they know if the data is accessed
- **Data breach notification laws**
	- Vary from country to country
	- Contracts often cover the maximum time that can elapse before customers are notified
	- Ensuring an appropriate breach notification clause in place that meets your needs can be important

- Acquiring forensic data from a cloud provider is unlikely
	- May be able to recover forensic data
		- Logs
		- Systems and infrastructure you maintain in an IaaS provider's environment
		- Forensic data from the service itself is rarely handed over to customers

## Acquisition Tools

- dd, FTK Imager, and WinHex
- Linux
	- dd is a cli utility
- FTK Imager
	- Formats
		- Raw (dd)-style 
		- SMART (ASR Data's format for their SMART forensic tool)
		- E01 (EnCase)
		- AFF (Advanced Forensics Format)
	- Supports
		- Physical drives
		- Logical drives
		- Image files
		- Folders
		- multi-CD/DVD VOLUMES

- MD5 and SHA1 hashes
	- Confirmation that there were no bad blocks
		- No data loss or problems

- Capture live memory on a system
	- FTK Imager

- WinHex
	- Acquire disk images in raw format

### Acquiring Network Forensic Data

- Capturing network traffic often requires a direct effort to capture and log the data in advance

- Other source
	- Firewall logs
	- IDS and IPS logs
	- Email server logs
	- Authentication logs
	- Other secondary source 

- Network traffic information
	- Packet analyzer
		- Wireshark
			- In-depth analysis of packets
			- Traffic flows
			- Metadata 

- Allowing copies of network traffic to be sent to collection servers
	- Taps
	- Span ports
	- Port mirrors used for network security devices
- Can result in massive amount of data
	- Capturing all or selected network traffic
	- Most organizations end up relying on
		- Logs, metadata, traffic flow information, and other commonly collected network information

### Acquiring Forensic Information from Other Sources

- Virtual Machines
	- Often in a shared environment
	- Removal of the system would cause disruption to multiple other servers and services
	- Imaging the entire underlying virtualization host would include more data and systems then may be needed
	- Snapshot will provide the information that forensic analyst need
		- Can be captured and then imported into forensic tools

- Containers
	- Designed to be ephemeral
	- Resources are often shared
	- Create fewer forensic artifacts than a virtual or physical machine
	- Though can be paused, capturing them and returning them to a forensically sound state can be challenging

## Validating Forensic Data Integrity

- Have a complete, accurate copy before you begin forensic analysis
- Documenting the provenance of data
- Ensuring that the data and process cannot be repudiated (nonrepudiation)

- Create a **hash** of the copy as well as hash of the original drive
	- Then compare them
	- MD5 and SHA1
		- Outmoded for purpose where attackers might be involved
		- Useful for quickly hashing forensic images

- Building provenance of the copy
	- MD5 or SHA1 hash of both drives
	- Documentation of the process and procedures used

- Hashes and other related information will be store as part of the chain-of-custody and forensic documentation for the case 

- Hash value can also be used as a **checksum**
	- Ensure that it has not changed 

- Careful documentation for cases is a critical part of the forensic process
	- Associating images with case numbers
	- Which examiner created the file

- Documenting the **provenance** or where an image or drive came from
	- What happened with it
		- Forensics suites have built-in documentation processes
		- Manual process
			- Picture, notes, documentation about chain of custody, processes, and steps made in the creation and analysis of forensic images
- With documentation like this
	- You can help ensure that inappropriate handling or processes do not result in the repudiation of the images or process

## Forensic Copies vs. Logical Copies

- Simply copying a file, folder, or drive will result in a logical copy
	- Data will be preserved
	- But it will not exactly match the state of the drive or device it was copied from
- When conduct forensic analysis
	- Important the preserve the full content of the drive 
		- At a bit-by-bit level
		- Preserving the exact structure of the drive
			- With deleted file remnants, metadata, and time stamps

## Making Sure the Data Doesn't Change

- Write blockers
	- Allow a drive or image to be read and accessed without allowing any writes to it

## Data Recovery

- The ability to recover data
	- Relies on the fact that deleting a file from a drive or device is nondestructive 
- When a file is deleted
	- Simple deleted the file's information from the drive's file index
	- And allow the space to be reused when it is needed 
- Quick formatting a drive
	- Only deletes the file index instead of overwriting or wiping the drive
- Recovering files
	- Require reviewing the drive
	- Finding files based on headers or metadata
	- Then recovery those files and file fragments

- File has been partially overwritten
	- Still possible to recover fragments of the files
- Files are stored in blocks
	- Block sizes depending on the drive and OS

- Forensic analyst rely on this when files have been intentionally deleted to try to hide evidence
	- They refer to the open space on a drive as **slack space**
		- Slack space analysis is critical
			- Because of the *wealth of data about what has previously occurred* on a drive that it can provide

- Antiforensic techniques and data security best practices
	- Overwriting deleted data

## Flash Media and SSDs: What About Wear Leveling?

- Completely removing data from devices like SSDs and flash media
	- That have space they use for wear leveling can be difficult
- Since wear leveling will move data to less worn cells (blocks of reserved spare space) as needed
	- Those cells that have been marked as unusable due to wear
		- May still contain historic or current data on the drive

- Large drive can contain a significant percentage of space wear leveling capacity
	- Which means that attempts to securely delete information on an SSD may fail

- Techniques like full-disk encryption
	- Ensure that even if data remains, it cannot be easily recovered

## Forensic Suites and a Forensic Case Example

- Forensic suites are complete forensic solutions
	- Data acquisition
	- Analysis
	- Reporting
- FTK and EnCase are major commercial options
- Autopsy is open source
	- Start creating a new case
		- Information about the investigators
		- The case
		- Other details that are important to tracking investigation
		- Then import files into the case
	- Timelines are very important
		- Allow you to see when filesystem changes and events occurred
		- Useful if you know when an incident happened
		- You need to find events as part of an investigation
		- Once you know when a person was active or the events started
			- You can then review the timeline for changes that were made near that time
		- Identify active times where other events were likely to be worth reviewing

- Timelining capabilities rely on accurate time data
	- Inaccurate time settings can cause problem for forensic timelines
- Incorrect time settings
	- Particularly in machines in the same environment
		- Can cause one machine to appear to have been impacted an hour earlier than others
			- Leading practitioners down an incorrect path
- Always check 
	- Make sure that the time stamps for files and time settings for machines are what you expect to be
		- Before jumping to conclusions about what happened at a specific time

- Other useful features
	- Distributed cracking of encryption
	- Hash cracking
	- Steganographic encoding detection

# Reporting

- A typical forensic report will include
	- Summary of the forensic investigation and findings
	- An outline of the forensic process, including tools used and any assumptions what were made about the tools or process
	- A series of sections detailing the findings for each device or drive.
		- Accuracy is critical when findings are shared, and conclusions must be backed up with evidence and appropriate detail
	- Recommendations or conclusions in more detail then the summary included

- Forensic practitioners may also provide a report with full detail of the analysis as part of their documentation package

>[!TIP] The exam outline includes acquisition, preservation, and reporting aligned with incident response activities. As you review this section, focus on how acquisition and preservation processes work, how they would be used in an incident response scenario, what information would be needed, and how it would be used when reporting is done.

# Digital Forensics and Intelligence

- Digital forensics primarily used for
	- Legal cases
	- Internal investigations
	- Incident Response (IR)
- Also play role
	- Strategic intelligence
	- Counterintelligence 

- Ability to analyze 
	- Adversary actions and technology
	- Components and behaviors of APT tools and processes
- Key tool in the arsenal for national defense and intelligence groups

- Forensic capabilities can be used
	- Intelligence operations
		- When systems and device are recovered or acquired
		- Allowing to recover data and provide it for analysis

- Many tools used by traditional forensic practitioners
	- Used by intelligence and counterintelligence organizations
- In addition
	- Advance methods of breaking encryptions
	- Analyzing software and hardware
	- Recovering data from systems and devices 
		- Designed to resist or entirely prevent tampering 

>[!TIP] Exam won't quiz you on specific intelligence and counterintelligence tools or techniques, but you should remember that forensic techniques play an important role in both communities.

# Exam Essentials

- **Legal holds and e-discovery drive some forensic activities.**
	- Organizations face legal cases and need to respond to legal holds
		- Require them to preserve and protect relevant information for the active or pending case
	- E-discovery
		- Also require forensic and other data to be provided as part of a legal case
	- Organization must build the capability and technology to respond to these requirements in an appropriate manner
		- Avoid losing cases in court
		- Support incident response processes

- **Acquisition techniques and procedures ensure usable and admissible forensic data.**
	- Different system components and resources are more likely to be changed or lost during the time it takes for a forensic acquisition
		- Forensic practitioners refer to the order of volatility
			- Determine what to capture first

- **There are many options for acquisition tools, and selecting the right tool combines technical needs and skillsets.**
	- Image acquisition tools
		- Ability to copy disks and volumes using a bit-by-bit method
			- Capture the complete image including unused or slack space
	- Acquisition processes vary 
		- Based on where the data is located
		- Snapshots of VMs
		- Data volume copies for cloud environments
		- Disk images for workstation and mobile devices
	- Incident Responders
		- Maintaining a chain of custody
		- Specific technical requirements of the system or devices they are capturing data from

- **Validation and preservation of forensic data is key part of the forensic process.**
	- Hashing drives and images
		- Ensure that the acquired data matches its source
		- Commonly use MD5 or SHA1
			- Adversarial techniques are rarely at play in forensic examinations
	- Checksums
		- Ensure that data is not changes
	- Preservation
		- Chain-of-custody 
		- Forethought about
			- Write blockers
			- Forensic copies
			- Documented processes and procedures

- **Forensic reports must be well organized and to the point.**
	- Forensic analysis doens't end when the technical examination of devices and drives is over
	- Forensic reports
		- Summarize key findings
		- Explain the process, procedures and tools
		- Any limitations or assumptions that impact the investigation
		- Detail the findings
			- With appropriate evidence
			- Detail to explain how conclusions were reached
		- Conclude with recommendations or overall conclusions in more detail than the summary provided

#cybersecurity 