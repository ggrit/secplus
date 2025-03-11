# Chapter 9 - Resilience and Physical Security

---
## Domain 1.0: General Security Concepts

**1.2. Summarize fundamental security concepts.**

- Physical security (Bollards, Access control vestibule, Fencing, Video surveillance, Security guard, Access badge, Lighting, Sensors)

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.4. Given a scenario, analyze indicators of malicious activity.**

- Physical attacks (Brute force, Radio frequency identification (RFID) cloning, Environmental)

## Domain 3.0 Security Architecture

**3.1. Compare and contrast security implications of different architecture models.**

- Considerations (Availability, Resilience, Cost, Responsiveness, Scalability, Ease of deployment, Risk transference, Ease of recovery, Patch availability, Inability to patch, Power, Compute)

**3.4. Explain the importance of resilience and recovery in security architecture.**

- High availability (Load balancing vs. clustering)
- Site considerations (Hot, Cold, Warm, Geographic dispersion)
- Platform diversity
- Multi-cloud systems
- Continuity of operations
- Capacity planning (People, Technology, Infrastructure)
- Testing (Tabletop exercises, Fail over, Simulation, Parallel processing)
- Backups (Onsite/offsite, Frequency, Encryption, Snapshots, Recovery, Replication, Journaling)
- Power (Generators, Uninterruptible power supply (UPS))

---

# Resilience and Recovery in Security Architectures

- Continuity of operations
- **Redundancy**
	- Geographic dispersion
	- Separation of servers and other devices in datacenters
	- Use of multiple network paths (multipath)
	- Redundant network devices 
		- Multiple routers, Firewalls, IPSs as part of HA (high availability)
		- Load balancing
			- Redundancy and resource distribution
		- Clustering
	- Protection of power
		- Uninterruptible Power Supply (UPS)
		- Generator
		- Dual-supply hardware
		- Managed Power Distribution Units (PDU)
	- Systems and storage redundancy
	- Platform diversity
		- Diversity of technologies and vendors

>[!TIP] Understand High Availability (HA), differences between and advantages of load balancing and clustering. Site considerations, platform diversity, and continuity of operations. Modern architectures also rely on multicloud systems, and you'll want to be able to explain how multicloud works and the issues it can create.

## Architectural Considerations and Security

- Availability
- Resilience
- Cost
- Responsiveness (respond in time)
- Scalability
- Ease of deployment
- **Risk transference** (Insurance, contracts...)
- Ease of recovery
- Patch availability and vendor support
- Inability to patch
- Power consumption
- Compute requirements

## Storage Resiliency

- RAID
	- Striped (spread across disks)
	- Mirrored (duplicated)
	- Ensure not corrupted or lost (parity)

| **RAID**                         | **Description**                                                                                                                      | **Pro**                                                                                                                  | **Cons**                                                                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **RAID 0**  Striping             | Data is spread across all drives in the array                                                                                        | Better I/O performance (speed); all capacity used                                                                        | Not fault tolerant                                                                                                |
| **RAID 1** Mirroring             | All data is duplicated to another drive                                                                                              | high read speeds from multiple drives; data available if a drive fails                                                   | Uses twice the storage for the same amount of data                                                                |
| **RAID 5** Striping and parity   | Data is striped across drives, with one drive used for parity (checksum) of the data. Parity is spread across drives as well as data | Data reads are fast; data writes are slightly slower. Drive failures can be rebuilt as long as only a single drive fails | Can tolerate only a single drive failure. Rebuilding arrays after a drive loss can be slow and impact performance |
| **RAID 10** Mirroring and parity | Requires at least four drives, with drives added in pairs. Data is mirrored, then striped across drives                              | Combines the pro and cons of both RAID 0 and RAID 1                                                                      | Combines the pro and cons of both RAID 0 and RAID 1                                                               |

- Backups
	- Full backup
	- **Incremental backup**
		- Changes since the **last backup**
		- Faster backup, slower recovery
	- **Differential backup**
		- Changes since the **last full backup**
		- Slower backup, faster recovery

- Replication
	- Synchronous
		- Real time
	- Asynchronous
		- After the fact
	- Unlike backup that **always occurring as changes are made**

- Journaling
	- **Log of changes**
	- Common for database and similar 
	- Virtual Machine
	- Needs to be **backed up somewhere**

- Backup frequency
	- Continuous, daily, weekly, monthly...

- Recovery process
	- Recovery Point Objective (RPO)
	- Recovery Time Objective (RTO)

>[!TIP] Make sure you understand recovery replication, and journaling. What is involved in recovery processes, and what impacts them? What is the difference between replication and journaling, and where would each be used?

- Snapshot
	- Captures the full state of a system or device
	- Depends on origin
	- Common in VM
	- Can restore to the point in time that it was taken

- Images
	- Complete copy of a system or server
	- Bit level
	- Independent
	- Cloning or restoration in a short time

- Virtualization systems and Virtual Desktop Infrastructure (VDI)
	- Use images to create nonpersistent systems
		- Which are using a "gold master" image

- Backup media
	- Tape
	- Disks
	- Optical media like Blu-ray and DVDs
	- Flash media like microSD card and USB drives

- Online backups
	- Quick retrieval and accessibility
- Offline backup
	- Can be kept in secure location
	- Without power and other expenses
	- Cannot have complete data loss
- Cloud backup
	- Maintained without infrastructure
- Nearline backup
	- Not immediately available but reasonable period of time
	- Usually without a human involved
	- Tape robots 

- Off-site storage
	- Geographic diversity

- Cloud and off-site third-party backup
	- Bandwidth requirements for both
	- Time to retrieve
	- Cost to retrieve
	- Reliability
	- New security models required for backups
		- Separation of accounts, additional controls, and encryption

- Encryption is important
	- At rest
		- Encryption key required for restore
	- In transit 
		- Transport layer encryption
- Security and accessibility of the keys

# Response and Recovery Controls

- Non persistence
	- Spun up and shut down as needed
- Reversion to a know state
	- When restarted
	- Snapshot
- Return to a last-known good configuration
- Change management processes
	- Last-known good configuration checkpoint
	- Backups
	- Snapshots
- To handle
	- Misconfiguration
	- Bad patches
- Live boot media
	- Bootable OS from USB drive or DVD
- High-availability
	- Load balancing
	- Content distribution networks
	- Clustered systems

- **Scalability**
	- Vertical scalability
		- Larger or **more powerful system** or device
		- When need all the task need to be handled on the same system or infrastructure
		- Expensive
	- Horizontal scaling
		- Smaller systems or devices but **adds more of them**
		- **Transparently** add and remove, upgrades, patching, and even incident response
		- Not every software or hardware can suite this scenario
- Cloud and virtualization can done easily 

- **Site considerations**
	- Site resilience
	- **Hot sites**
		- Fully ready to go
	- **Warm sites**
		- Waiting for data and staff
		- System ready to go and mostly configured
	- **Cold sites**
		- Have space, power, and network connectivity
		- Not prepared with systems or data
		- Need effort and deployment of technology
		- Least expensive

- Restoration order
	- Network connectivity and a bastion or shell host
	- Network security devices (Firewall, IPS)
	- Storage and database services
	- Critical operational servers
	- Logging and monitoring service
	- Restore other services as possible 

- Cloud infrastructure
	- IaaS (Infrastructure as a Service)
	- Design across multiple geographic regions
	- Also multiple datacenter linked inside a region
	- Can help with capacity and disaster recovery
	- Multicloud to operate even if a cloud vendor has a problem

- Geographic dispersion
	- Natural and human made disaster
	- Have benefits even in the cloud

>[!TIP] Know what hot, warm, cold sites are and why an organization might select each based on cost versus functionality. Explain geographic dispersion and why organizations choose their location to avoid disasters impacting multiple sites at the same time.


## Capacity Planning for Resilience and Recovery

- Resilience
	- Planning staff, technology, and infrastructure is available
	- Investment in physical infrastructure
		- Primary location or datacenter were taken offline

- **Capacity planning**
	- **People**
		- Staff and skillsets
		- Hire staff in multiple locations
	- **Technology**
		- Understanding the technologies deployed and it's ability to scale
		- Capabilities of a web server tool, load balancer, or storage device's throughput
	- **Infrastructure**
		- Underlying systems and networks may need to scale
		- Network connectivity, storage 

## Testing Resilience and Recovery Controls and Designs

- In order of how much potential they have to disrupt and organization's operations
- **Tabletop exercises**
	- Discussions between personnel
- **Simulation exercises**
	- Drills or practices in which personnel simulate what they would do in an actual event
- **Parallel processing exercises**
	- Move processing to a hot site or alternate backup system or facility to validate that the backup can perform as expected
- **Failover exercise**
	- Test full failover to an alternate site or system

>[!TIP] Explain he importance and know the differences between the various testing exercise, including tabletop, simulation, parallel, and failover processing.

# Physical Security Controls

- Like fences, Lighting, and locks
- Physical access to systems, facilities, and networks

## Site Security

- Security through obscurity
	- Not preferred control, but it can be helpful
- Deterrent
	- Fences
	- Barber wire or razor wire
	- Bollards
	- Lighting
- Access badges
- Access control vestibules
	- Also called **Mantraps**
	- Do not use piggybacking

### Guards

- Security guards
- Detection and response
- Visitor log

### Video Surveillance, Cameras, and Sensors

- Video surveillance
	- Motion recognition cameras
	- Object detection
	- Closed-circuit television (CCTV)

- Sensors
	- Infrared sensor
		- Changes in infrared radiation
		- Well-controlled smaller indoor spaces
	- Pressure sensors
		- Detect object or someone move
		- Pressure-plate or pad
	- Microware sensors
		- Baseline for a room change will trigger
		- More sensitive and more capable then infrared
		- **Detect through material**
		- Broader range of **temperature**
		- **More sensitive** so more error prone than infrared
	- Ultrasonic sensors
		- Can be set off by machinery or other **vibrations**
		- Environmental effects on human occupants
		- **Proximity** detection

## Detecting Physical Attacks

- Brute-force attacks
	- Breaking down doors
	- Cutting off locks
- Radio frequency identification **(RFID) cloning**
- Environmental attacks
	- Targeting heating and cooling systems
	- Maliciously activating a sprinkler system 

# Exam Essentials

- **Redundancy build resilience.**
	- Need to address the organizational risks and priorities
	- Best trade-offs between costs and capabilities
	- Geographic dispersal
	- Load balancer and clustering
	- Power protection and redundancy
	- RAID
	- Backups
	- Diversity of technology, systems, cloud service provider, and platforms
- Considerations
	- Availability
	- Resilience 
	- Cost
	- Responsiveness
	- Scalability
	- Ease of deployment
	- Risk transference
	- Ease of recovery
	- Patch availability
	- Inability to patch
	- Power
	- Compute
- Capacity planning
	- Enough capacity to handle issues and outage
	- Enough people, technology, and infrastructure
- Multicloud
	- Single technology or provider's outage or issue does not take offline
	- Create complexity and costs

- **Backups help ensure organizations can recover from events and issues.**
	- Backup location and frequency
	- Offsite backups
	- Snapshots
	- Journaling
	- Replication
	- Encryption to keep secure in-transit and at rest

- **Response and recovery are critical when failures occur.**
	- Disaster recovery location
		- Hot, warm, or cold site
	- Redundant cloud or hosted location
	- Predetermined restoration order
	- Testing
		- Tabletop 
		- Simulation 
		- Parallel
		- Failover

- **Physical security control are a first line of defence.**
	- Fences
	- Lighting
	- Alarms
	- Bollards
	- Access control vestibules (Mantrap)
	- Camera
	- Sensors
		- Infrared
		- Pressure
		- Microware
		- Ultrasonic
	- Locks
	- Badges
	- Guards
- Attack types
	- Brute-force
	- RFID clone
	- Environmental

#cybersecurity 