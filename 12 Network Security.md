# Chapter 12 - Network Security

---

## Domain 1.0:  General Security Concepts

**1.4. Summarize fundamental security concepts.**

- Zero Trust (Control plane (Adaptive identity, Threat scope reduction, Policy-driven access control, Policy Administrator, Policy Engine), Data Plane (Implicit trust zones, Subject/System, Policy Enforcement Point))

- Deception and disruption technology (Honeypot, Honeynet, Honeyfile, Honeytoken)

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.4 Given a scenario, analyze indicators of malicious activity.**

- Network attacks (Distributed denial-of-service (DDoS) (Amplified, Reflected), Domain Name System (DNS) attacks, Wireless, On-path, Credential replay, Malicious code)

**2.5. Explain the purpose of mitigation techniques used to secure the enterprise.**

- Segmentation
- Access control (Access control list (ACL))

## Domain 3.0 Security Architecture

**3.1. Compare and contrast security implications of different architecture models.**

- Architecture and infrastructure concepts (Network infrastructure (Physical isolation (Air-gapped), Logical segmentation, Software-defined networking (SDN)), High availability)

**3.2. Given a scenario, apply security principles to secure enterprise infrastructure.**

- Infrastructure considerations (Device placement, Security zones, Attack surface, Connectivity, Failure modes (Fail-open, Fail-closed), Device attribute (Active vs. passive, Inline vs. tap/monitor), Network appliances (Jump server, Proxy server, Intrusion prevention system (IPS)/Intrusion detection system (IDS), Load balancer, Sensors), Port security (802.1X, Extensible Authentication Protocol (EAP)), Firewall types (Web application firewall (WAF), Unified threat management (UTM), Next-generation firewall (NGFW), Layer 4/Layer 7))
- Secure communications/access (Virtual private network (VPN), Remote access, Tunneling, (Transport Layer Security (TLS), Internet protocol security (IPSec)) Software-defined wide area network (SD-WAN). Secure access service edge (SASE))
- Selection of effective controls

## Domain 4.0 Security Operations

**4.1. Given a scenario, apply common security techniques to computing resources.**

- Hardening targets (Switches, Routers)

**4.4. Explain security alerting and monitoring concepts and tools.**

- Tools (Simple Network Management Protocol (SNMP) traps)

**4.5. Given a scenario, modify enterprise capabilities to enhance security.**

- Firewall (Rules, Access lists, Ports/protocols, Screened subnets)
- IDS/IPS (Trends, Signatures)
- Web filter (Agent-based, Centralized proxy, Universal Resource Locator (URL) scanning, Content categorization, Block rules, Reputation)
- Implementation of secure protocols (Protocol selection, Port selection, Transport method)
- DNS filtering
- Email Security (Domain-based Message Authentication Reporting and Conformance (DMARC), DomainKeys Identified Mail (DKIM), Sender Policy Framework (SPF), Gateway)
- File integrity monitoring
- DLP
- Network Access Control (NAC)

---

# Designing Secure Networks

- Selection of effective controls

>[!TIP] Exam focuses on implementing designs and explaining the importance of security concepts and components. For this exam, focus on the items listed in the exam outline, and consider how you would implement them and why they're important.

- Security design in most environments
	- Concept of defence-in-depth
		- Multiple controls

## Infrastructure Consideration

- **Attack surface**, or a device's attack surface
	- Services, management interfaces, an other

- **Device placement**
	- Secure specific zone or network segment
	- Common placement
		- Network borders
		- Datacenter borders
		- Between network segments
		- VLAN
		- Protect specific infrastructure

- **Security zones**
	- Network segments
	- Physical or virtual network segments
- Created on trust or data sensitivity boundaries
- Common example
	- Segregated guest networks
	- Internet-facing network to host webservers and other Internet accessible services
	- Management VLAN
		- Switches, access points, router, and similar 

- **Connectivity** considerations
	- How organization connects to the internet
	- Redundant connections
	- How fast the connections are
	- What security controls the upstream connectivity provider can make available
	- What type of connectivity is in use
		- Fiber optic, copper, wireless, or other
	- If the connection paths are physically separated
	- Using different providers 

- **Failure modes** and how the organization wants to address them
	- When a security device fails
		- Should it fail so that no traffic passes it or should it fail so that all traffic passes it?
			- Fail-close and fail-open

- **Network taps**, devices used to monitor or access traffic
	- May be active or passive
		- Powered or not powered
		- Passive can't lose power, potential failure mode is removed
	- They can also be in line, with all traffic flowing through them
	- Or can be set up as taps or monitors
		- **Copy traffic** instead of interacting with the original network traffic 

## Network Design Concepts

### Physical Isolation

- Separating devices so that there is no connection between them
- **Air-gapped** design

### High Availability

- HA
- Upgrades, patching, system or service failure, changes in load, and other events without interruption of services 
- Design
	- Cluster, load balancing, and proxies 
- Elimination of single point of failure

### Implementing Secure Protocols 

- HTTPS (TLS) instead of unencrypted HTTP
- SSH instead Telnet
- Wrapping other services using TLS
- **Protocol selection**
	- Will default using the secure protocol if it exist and is supported
- **Transport method**

## Security Through Obscurity and Port Selection

- Some organizations choose to run services on alternate ports to decrease the amount of scanning traffic that reaches the system
	- Is the right answer? In some cases
- Not a typical security control 

### Reputation Services

- **Services and data feeds that track** 
	- IP addresses, domain, and host that engage in malicious activity
- Monitor or block potentially malicious actors and systems
- Combined with *threat feeds* and *log monitoring *

### Software-Defined Networking

- **SDN**  
	- *Software-based network* configuration to control networks
- Rely on controllers that manage network devices and configurations
- Centrally managing 
- Allow networks to be dynamically tuned based on performance metrics and other configuration settings
- Flexible

### SD-WAN

- **Software-Defined Wide Area Network**
	- *Virtual Wide Area Network* design 
		- Combine multiple connectivity services
- Commonly used with
	- Multiprotocol Label Switching (MPLS)
	- 4G and 5G
	- Broadband networks
- *High Availability* and *Route traffic* based on application requirements
- Controlling costs
	- Using less expensive connection methods when possible

- MPLS
	- Uses **Data Label** 
		- Called a *Forwarding Equivalence Class (FEC)* 
			- Rather than network addresses (IP)

### Secure Access Service Edge (SASE)
- *pron. "sassy"*

- Provide secure access for devices
	- Combines
		- VPNs
		- SD-WAN
		- Cloud-based security tools
			- Firewalls
			- Cloud access security brokers (CASB)
			- Zero-trust networks
- Deployed to ensure
	- Endpoints are secure
	- Data is secure in transit
	- Policy

- CASB
	- **Policy enforcement** for cloud resources
		- Between *service providers* and *service customers*
	- Deployed
		- On-promises
		- Cloud

## Network Segmentation

- Logical or Physical
- VLAN
	- Data Link layer
	- Switches or other devices
	- Different broadcast domain

- Broadcast domain
	- Segment of a network
	- All the devices or system can reach one another
		- Via packets sent as a broadcast at the Data Link layer
	- Networks less noisy

- Network segmentation
	- **Screened subnets** (DMZ, Demilitarized zones)
		- Contain systems that are **exposed to less trusted areas**
		- Commonly used
			- Web servers or other Internet-facing devices
		- Also describe internal purposes where trust levels are different
	- **Intranets**
		- Internal network 
		- Provide information to employees
		- Typically protected from external access
	- **Extranets**
		- Set up for external access
		- Typically by partners or customers 

- Zero Trust network
	- Nobody is trusted
		- Internal or external
		- Person or system
	- Should include security 
		- Between systems
		- At security boundaries 

## They left on a Packet Traveling East

- *"East-west"* traffic
	- Describe traffic flow in a datacenter

## Zero Trust

- No trust boundary and no network edge
- Each action is validated when requested
	- Continuous authentication process
- Access is only allowed 
	- After policies are checked
		- Including elements like
			- Identity
			- Permissions
			- System configuration
			- Security status
			- Threat intelligence data review
			- Security posture

- NIST ZTA (Zero Trust Architecture)
	- **Subject** use of a system that is untrusted 
	- Connects through a **Policy Enforcement Point**
		- Allowing trusted transactions to enterprise resources
	- **Policy engine** makes policy decisions based on rules
	- That are are then acted on by **Policy Administrators** 

- In the NIST model
	- **Subjects**
		- Users
		- Services
		- Systems
		- That request access or attempt to use rights
	- **Policy Engines**
		- Policy decision based on both rules and external systems
			- Threat intelligence, ID management, SIEM devices, and other
		- Use trust algorithm
			- To grant, deny, or revoke access to a given resource
			- Based on the factors used for input to the algorithm
		- Once decision is made
			- It is logged
			- And the *Policy Administrator*
				- Takes action based on the decision
	- **Policy Administrator**
		- Components that establish or remove the communication path between subjects and resources
		- Creating session-specific authentication token or credentials
		- Where access is denied
			- Tells the *Policy Enforcement Point* to end the session or connection
	- **Policy Enforcement Points**
		- Communicate with *Policy Administrator*
			- To forward requests from *Subjects*
			- And to receive instruction about connections to allow or end
		- Deployed
			- Local client or application
			- Gateway element 

- **Two major Zero Trust planes**
- **Control Plane** 
	- **Adaptive identity** (Adaptive authentication)
		- Context-based authentication
			- Where the user is logging from
			- What device 
			- Device meets security and configuration requirements
			- May request additional identity validation 
	- **Threat scope reduction**
		- Described as "limited blast radius"
		- Key component in Zero Trust design
		- Limiting the scope of what a subject can do
		- What access is permitted to a resource limits what can go wrong
		- Relies on 
			- Least Privilege
			- Identity-bases network segmentation
	- **Policy-driven access control
		- Core concept
		- Policy Engines rely on policies
		- Then enforced by
			- *Policy Administrator
			* *Policy Enforcement Points*
	* **Policy Administrator**
		* Executes decisions made by a *Policy Engine*
- **Data Plane**
	- **Implicit trust zones**
		- Allow use and movement
		- Once a *Subject* is authenticated by *Zero Trust Policy Engine*s
	- **Subjects and systems**
		- Devices and users
	- **Policy Enforcement Points**

>[!TIP] Exam outline emphasizes infrastructure considerations like device placement, attack surface, failure modes, connectivity, security zones, and device attributes. It also considers network design concepts like physical isolation and logical segmentation as well as high availability, secure protocols, the role of reputation devices, SDN, SDWAN, SASE, and Zero Trust. Make sure you understand each of these concepts.

## Network Access Control

- NAC
- Protecting network from unauthorized access 
- Determining whether a system or device should be allowed to connect to a network
- Software agent on computer to perform security checks
	- Greater ability to determine the security state by validating
		- Patch levels
		- Security settings
		- Antivirus version
		- And other settings and details 
- Or agentless and run from a browser or other means without installing software locally
- Can also track user behavior 

- Since NAC has the **ability to validate security status for systems**
	- Can be an effective **policy enforcement tool**
	- If system does not meet security objectives, or if it has an issue
		- The system can be place into **quarantine network**

- **NAC checks** can occur 
	- **Before** a device is allowed on the network (Preadmission)
		- Keep potentially dangerous systems off a network
	- **After** it has connected (Postadmission)
		- Can help with response
		- Prevent failed NAC access attempts from stopping business

- **Agent-based NAC** 
	- Requires installation
	- Adds complexity and maintenance
	- But it provides greater insight and control

- **Agentless**
	- Lightweight
	- Easier
	- May not centrally managed
	- Devices may not support the NAC Agent
	- Provide less detail

### NAC and 802.1X

- **802.1X**
	- Standard for authenticating devices
		- Connected to wired and wireless network
	- Centralized authentication using EAP (Extensible Authentication Protocol)
	- Port-based authentication or port security
	- Network access switch level to authorize ports or leave them as unauthorized
	- If device want to connect to a LAN
		- Need to have an 802.1X supplicant
		- And complete an authentication process

## Port Security and Port-Level Protections

- **Port security**
	- Limit number MAC address on a single port
		- Prevents problems
			- MAC address spoofing
			- Content-addressable memory (CAM) table overflows
			- Plugging in additional network devices to extend the network
			- And others
	- Settings
		- Maximum number of MAC addresses (Dynamically lock)
		- Allow only specific MAC addresses (Statically lock)
	- Spoofing MAC addresses is easy

- Protocol-level protections
	- **Loop prevention**
		- Detecting loops and then disabling ports
		- Spanning Tree Protocol (STP)
			- Use Bridge Protocol Data Units (BPDU)
				- Sends frames with a switch identifier that the switch then monitors to prevent loop
	- **Broadcast storm prevention**
		- Prevents broadcast packets from being amplified
	- **Bridge Protocol Data Unit (BPDU)** Guard
		- Protects STP
			- By preventing ports that should not send BPDU messages from sending them
		- Typically applied to switch ports where user devices and servers will be plugged in
		- Ports where switches will be connected will not have BPDU Guard turned on
			- Because they may need to send BPDU messages that provide information about
				- Ports, addresses, priorities, and costs as part of the underlying management and control of the network
	- **Dynamic Host Configuration Protocol (DHCP)** snooping
		- Prevent rogue DHCP servers from handing out IP addresses to clients in a managed network
		- Drops messages from any DHCP servers that is not on a list of trusted servers
		- Block DHCP messages where the source MAC and the hardware MAC of a network card do not match
		- Drop messages releasing or declining DHCP offer if the release or decline does not come from the same port that the request came from
			- Preventing attackers from causing a DHCP offer or renewal to fail

## Virtual Private Networks and Remote Access

- VPN
	- Virtual network link across a public network
	- Allow endpoints to act as though they are on the same network

- **IPSec VPN**
	- Layer 3
	- Require **client**
	- Can operate **tunnel or transport** mode
	- Tunnel mode
		- Entire packets of data sent are protected
	- Transport mode
		- IP header is not protected
		- IP payload is protected
	- Used for 
		- **Site-to-site VPN**
		- VPN that need transport more than just web and application traffic

- **SSL VPN (actually TLS VPN)**
	- **Portal-based** approach (typically HTML5)
		- Users access via a **web page** and then access services through that connection
	- Tunnel mode (like IPSec)
	- No client needed or specific configuration like IPSec
	- Ability to segment application access
		- More granular

>[!TIP] Exam outline list IPSec and TLS under tunneling instead of under VPN. The underlying technology for VPN and tunneling is the same, and many security analysts will encounter VPN choices between IPSec VPN and TLS VPN before they have to choose between other types of tunneling. Just remember for the purpose of the exam that you may encounter this in either place.

- VPN will be used for remote access or if it will be a site-to-site VPN

- **Remote-access VPN**
	- Used for travelling staff and other remote workers
	- As-needed mode
- **Site-to-site VPN**
	- Used to create secure network channel between two or more sites
	- Extend an organization's network
	- Always-on VPN

### Tunneling

- **Full-tunnel VPN**
	- Sends all network traffic through the VPN tunnel
	- Keeping it secure as it goes to the remote trusted network
	- Ensure that traffic sent through an untrusted network (coffe shop, hotel...) remain secure
- **Split-tunnel VPN**
	- Sends traffic intended for systems on the remote trusted network through the VPN tunnel
	- Less bandwidth for the hosting site
	- Network traffic that is not intended for that network will be sent out through whatever ISP the VPN user is connected to
		- Traffic is not protected by the VPN and cannot be monitored
	- May expose more information about your network traffic than you want it to

>[!TIP] NAC, 802.1X, port security, and VPN all have roles to play in how networks and network traffic are secured. For the exam, you'll need to be familiar with each of them and how they're used in secure networks.

## Network Appliances and Security Tools

- Special-purpose hardware devices
- VM 
- Cloud-based software appliances
- Hybrid models in both open source and proprietary 

### Jump Servers

- Administrators and other staff
	- Securely operate in security zones with different security levels
- Secured and monitored system
- Configured with tools required for administrative work
- Accessed with SSH, RDP, or other
- Configured to create and maintain a secure audit trail
	- Copies maintained in a separate environment 
		- Allow for incident and issue investigations

### Load Balancing

- Distribute traffic to multiple systems
- Provide redundancy
- Ease of upgrades and patching
- Commonly for web server 
- Present a virtual IP (VIP)
	- Which clients send service requests on a specific service port
- Modes of operation
	- **Active/active** 
		- Distribute the load among multiple systems that are online and in use at the same time
	- **Active/passive**
		- Bring backup or secondary system online when an active system is removed or fails
		- More likely to be found as **part of disaster recovery or business continuity** 
- Scheduling or load-balancing algorithms
	- Round-robin
		- Sends each request to servers by working through a list, with each server receiving traffic in turn
	- Least connection
		- Sends traffic to the servers with the fewest number of active connections
	- Agent-based
		- Adaptive balancing monitors the load and other factors that impact a server's ability to respond and updates the load balancer's traffic distribution based on the agent's reports
	- Source IP hashing
		- Uses a hash of the source IP to assign traffic to servers. This is essentially a randomization algorithm using client-driven input
- Weighted algorithms
	- Weighted least connection
		- Uses a least connection algorithm combined with a predetermined weight value for each server
	- Fixed weighted
		- Relies on a preassigned weight for each server, often based on capability or capacity
	- Weighted response time
		- Combines the server's current response time with a weight value to assign it traffic
- May need to establish persistent sessions

## Layer 4 vs. Layer 7

- Firewall
	- Layer 4 vs Layer 7 inspection

- Next-Generation Firewall (NGFW)
	- Interact both layer 4 and layer 7
- Application awareness
	- Allow them to stop application attacks 
	- Monitor for unexpected traffic that would normally pass through a firewall level 4
- Toll
	- More CPU and memory
	- More complex rules and algorithms

### Proxy Servers

- Accept and forward requests
- Centralizing the request 
- Allowing actions to be taken on the request and responses
- Filter or modify traffic
- Cache data
- Access restrictions
	- By IP address or similar

- **Forward proxies**
	- Placed between clients and servers
	- Accept request from clients and send them forward to servers
	- Conceal the original client
		- Anonymize traffic
		- Provide access resource blocked by IP or geo location
	- Allow access to resources such as those that libraries subscribe to

- **Reverse proxies**
	- Placed between servers and clients
	- Help with load balancing
	- Caching of content
	- Clients query a single system 
		- But have traffic load spread to multiple systems or sites

### Web Filters

- Centralized proxy devices or agent-based tools
- Allow or block traffic based on content rules
	- URL scanning
	- Blocking specific URL, domain or host
	- Pattern matching
	- IP reputation 
	- An others filtering rules
	- Allow or deny lists

- When deployed as hardware devices or VM
	- Centralized proxy
		- Traffic routed through the decice
- Agent-based deployment
	- Agent installed on devices
	- Proxy is decentralized 

- Content categorization
	- URL filtering
		- Common categories
		- Adult material
		- Business
		- Child-friendly
	- Block rules

### Data Protection 

- Data Loss Prevention (DLP)
	- Pair
		- Agent on systems
		- Filtering capabilities at the network border, email servers, and other likely exfiltration points
- Pattern-matching capabilities or rely on tagging
- Action taken
	- Blocking traffic
	- Send notification
	- Forcing identifies data to be encrypted
	- Data securely transferred rathen than being sent in an unencrypted or unsecure mode

### Intrusion Detection and Intrusion Prevention Systems

- Network-based IDS and IPS
	- Hardware appliances
	- Software-based
	- VM
	- Cloud instance
- Detect threats
	- IPS block them
- Detection methods
	- Signature-based
		- Hash or signature
			- Matching to detect a threat
	- Anomaly-based
		- Flags when out-of-the-ordinary behavior occurs

- IPS
	- Active mode
		- In line where it can interact with the flow of traffic to stop threats
	- Passive mode
		- Can detect but cannot take action (like IDS)

## Configuration Decisions: Inline vs. Tap, Active vs. Passive

- **Inline** network device
	- Traffic pass through them
	- Interact with traffic
		- Modifying or stopping
	- Potential point of failure
		- Device that stops working may cause an outage
		- But some can allow to fail-open
			- Not all failure scenarios will activate this feature

- **Taps or Monitors** network devices
	- Replicate traffic for inspection
	- Do not interact with traffic
	- Avoid problem potential failures causing outage
	- Monitoring, analysis, and security purposes
- **Active Taps**
	- Require power
	- Network ports are physically separate without a direct connection between them
	- Power outage or software failures
		- **Can interrupt traffic**
- **Passive Taps**
	- Direct path between network
	- Optical taps
		- Split the light passing through them to create copies
	- Copper networks
		- Require power
		- Direct path
	- **Not interrupt traffic**

- **SPAN port or Mirror port**
	- Build into routers and switch
	- Allow selected traffic to be copied to a designated port
	- Less secure

### Firewalls

- Network appliances or individual devices

- **Stateless Firewalls** *(Packet filters)*
	- Filter every packet
		- Based on
			- Source
			- Destination IP
			- Port
			- Protocol
			- Other header information

- **Stateful Firewalls** *(Dynamic packet filters)*
	- Pay attention to the state of the traffic
	- Can make decision about a conversation
		- Allow it to continue once it has been approved
		- Rather than reviewing every packet
	- Track information in *state table*
		- Allow them to *see entire traffic flow instead of each packet*
		- Providing more context 

- Next-generation Firewall (NGFW)
	- All-in-one network security devices
	- Capabilities
		- Deep packet inspection
		- IDS/IPS functionality
		- Antivirus and antimalware 
		- And other
	- More configuration and expertise to deploy

- Unified threat management (UTM)
	- Include
		- Firewall
		- IDS/IPS
		- Antimalware
		- URL and email filtering and security
		- DLP
		- VPN
		- Security monitoring
		- Analytics capabilities
	- Out-of-box
		- Quickly deployed and used
	- Management capability
		- Can handle multiple UTM device at once
			- Allowing managing and monitoring them centrally

- **Web Application Firewalls (WAF)**
	- Intercept, analyze, and apply rules
		- Looking for attacks and attack patterns
		- Block or modify traffic sent to web server
	- To
		- Web traffic
		- Database queries
		- APIs
		- Web application tools
			- Login forms, search fields...

- Firewall **rules**
	- What traffic allow and what traffic is stopped
	- Source
		- IP addresses
		- Hostnames
		- Domains
		- **Ports**
		- **Protocol**
	- Destination
		- IP addresses
		- Host or hosts
		- Domain
		- Ports
		- Protocols

- Specific use of Firewall
	- **Screened subnets**
		- Three interfaces on a Firewall
			- One connect to the *Internet or an untrusted network*
			- One to create *secured area*
			- One to create a *public area (DMZ)*

### Access Control Lists

- ACL
- Rules 
	- Allow or deny
		- Actions
		- Traffic
		- Access
	- For network device, similar to firewall
		- Group
		- Tag
	- Simple or complex
- Cloud services also provide network ACL

## Deception and Disruption Technology

- **Honeypots**
	- Appear to be legitimate
	- Systems intentionally configured to be vulnerable
	- But heavily instrumented and monitored
	- Used for **adversarial research** 
- **Honeynets**
	- Network of honeypots
- **Honeyfiles**
	- Used for **intrusion detection**
	- Intentionally attractive file
	- If discovered outside of the network
		- The systems was breached
- **Honeytokens**
	- Allow security professional to **track data**
	- IDS, IPS, DLP and other systems
		- Configured to watch for *honeytokens* 
			- That should be *sent out or accessed*

>[!TIP] Appliances and tools like jump servers, load balancers, and load balancing techniques, proxy servers, web filters, DLP, IDS, IPS, firewalls and the type fo firewalls commonly encountered as well as ACLs are all included in the exam outline. Make sure you know what each is used for and how it could be used to secure an organization's infrastructure. Finally, make sure you're aware of the various deception and disruption technologies like honeyfiles, honeytokens, honeynets, and honeypots.

## Network Security, Services, and Management

- Prioritizing traffic via Quality of Service (QoS)
- Providing route security
- Implementing secure protocols on top of existing network fabric

### Out-Of-Band Management

- A separate means of accessing the administrative interface
- Network-based for administrator
	- VLAN
	- Separate physically
- Physical access
	- But reserved for emergencies
	- Travelling to is time consuming and far less useful

### DNS

- Domain Name System
- Unsecure protocol
	- Unencrypted
	- Unprotected
	- Not have authentication

- **Domain Name System Security Extensions (DNSSEC)**
	- Authentication
	- DNS query need to be validated
	- Unencrypted

- Properly configuring
	- Preventing zone transfers
	- DNS logging is turned on
	- DNS request to malicious domains blocked

- DNS filtering
	- Block malicious domain
	- Can prevent phishing
		- Redirect users who click on links in the phishing mail to a trusted warning site

### Email Security

- DomainKeys Identified Mail (DKIM)
- Sender Policy Framework (SPF)
- Domain-based Message Authentication Reporting and Conformance (DMARC)

- DKIM
	- Allow to add content the messages to identify them as being from their domain
	- Signs
		- Body of the message
		- Elements of the header
	- Help ensure non-repudiation between organizations
	- Adds DKIM-Signature header
		- Checked against the public key
			- Stored in public DNS entries for DKIM-enabled organizations

- SPF
	- Email authentication
	- Publish a list of **authorized email servers**
	- SPF records
		- Added to the DNS information for your domain
		- Specify which systems are allowed to send email from that domain
	- System not listed in SPF will be rejected

- DMARC
	- DKIM and SPF
		- Determine email is authentic 
	- Records are published in DNS
	- Can be used to determine
		- Whether you should accept a message 
			- (Unlike DKIM and SPF)
	- Can choose to reject or quarantine messages
		- That are not sent by a DMARC-supporting sender

- **Email security devices**
	- Email security gateways
		- Filter inbound and outbound email
		- Phishing protection
		- Email encryption
		- Attachment sandboxing
		- Ransomeware protection
		- URL analysis
		- Threat feed
		- Support for
			- DKIM, SPF, and DMARC checking

### Secure Sockets Layer/Transport Layer Security

- Encrypt data in-transfer
- HTTPS
	- HTTP with TLS

- TLS
	- To wrap protocols 

- **Ephemeral keys** for TLS
	- Perfect forward secrecy
		- Even if the secrets used for key exchange are compromised
			- Communication itself will not be
- Ephemeral Diffie-Hellman key exchange
	- Each connection receives a unique temporary key

## What about IPv6?

- Additional complexity to security practices and technology
- *NAT* no longer needed (lot of address space)
	- Protection that NAT provides no longer exist
- Complexity
	- Automatic tunneling
	- Automatic configuration
	- Use of dual network stacks (IPv4 and IPv6)
	- Sheer number of addresses 

### SNMP

- Simple Network Management Protocol
	- Protocol to **monitor and manage network devices**
- SNMP objects
	- Switches
	- Routers
	- Other devices listed in *Management Information Base (MIB)*
- Are queried for SNMP information

- When device configured to use SNMP encounter an error
	- It sends a message known as a **SNMP trap**
		- Include information about what occurred
- Unlike other SNMP traffic
	- SNMP trap are sent to a *SNMP manager* from *SNMP agents* on devices

- Base set of **SNMP traps**
	- coldStart
	- warmStart
	- linkDown
	- linkUP
	- authenticationFailure
	- egpNeighborLoss
	- Additional custom traps can be configured

### Monitoring Services and Systems

- Ensuring services are online and accessible
	- Requires monitoring and reporting capabilities
- Check service is responding is simple
- Validating service is functioning as expected can be more complex

- Organizations use multiple tiers of **service monitoring**
	- First
		- Validates a service port is open and responding
			- Help identify significant issues
				- Service failing to load
				- Crashing
				- Blocked by firewall rule
	- Next level
		- Interaction with the service and understanding of what a valide response should look like
		- Use metrics that validate performance and response times
	- Final
		- Indicators of likely failure
		- Uses a broad range of data to identify pending problems

- Service monitoring tools
	- Operations monitoring tools
	- SIEM devices
	- Other management platforms

- Configuring service-level monitoring
	- Insight into ongoing issues for security administrators
		- Services failures 
		- Issues can be an indicator of an incident

### File Integrity Monitors

- Attackers
	- May change configuration files
	- Install their own services
	- Modify systems 
- Detecting those changes 
- Reporting 
- Restoring
- Tools
	- Tripwire
- Create a signature or fingerprint for a file
	- Then monitoring the file and filesystem for changes to monitored files
- Allow normal behaviors like patching or user interaction
	- Focus on unexpected and unintended changes

### Hardening Network Devices

- Center for Internet Security (CIS) as well as manufacturers
	- Provide lockdown and hardening guidelines
- Protect management console
	- VLAN
	- Jump server
	- VPN
	- Physical 

>[!TIP] Need to know about quality of service, DNS, and email security, the use of encryption via TLS to encapsulate other protocols for secure transport, SNMP and monitoring services and systems, file integrity to track changes and how network devices are hardened and their management interfaces are protected.

# Secure Protocols

## Using Secure Protocols

- Voice and video
	- Often rely on **HTTPS**
	- Session Initiation Protocol (SIP)
		- **SIPS**
	- Real-time Transport Protocol (RTP)
		- **SRPT**

- Network Time Protocol (NTP)
	- **NTS**
		- Relies on *TLS*
		- Not protect the time data
		- Focuses on authentication
			- Trusted server
			- No changed in transit

- Email and web traffic
	- **HTTPS**
	- **IMAPS**
	- **POPS**
	- Security protocols
		- **FMARC**
		- **DKIM**
		- **SPF**

- File Transfer Protocol (FTP)
	- Combination of
		- **HTTPS**
		- **SFTP**
		- **FTPS**

- Directory services
	- LDAP
		- **LDAPS**

- Remote access
	- **SSH**
	- **RDP**
	- **HTTPS**

- Domain name resolution
	- **DNSSEC**
	- **DNS reputation list**

- Routing and switching
	- Border Gateway Protocol (BGP)
		- Lacking built-in security
		- BGP hijacking
	- Cannot rely on secure protocol
		- Design around this lack

- Network address allocation
	- DHCP
		- Not offer secure protocol
		- Relies on detection and response

- Subscription services 
	- Cloud and similar 
		- HTTPS
		- Other for specific use cases

- Lack of secure protocols 
	- DHCP
	- NTP
	- BGP

## Secure Protocols

- Many protocols rely on *TLS* to protect traffic
- Others implement *AES encryption* 
- Or other techniques 

| **Unsecure protocol** | **Original port** | Secure protocol | **Secure port**                                             | **Notes** |
| --------------------- | ----------------- | --------------- | ----------------------------------------------------------- | --------- |
| DNS                   | UDP/TCP 53        | DNSSEC          | UDP/TCP 53                                                  |           |
| FTP                   | TCP 21 (and 20)   | FTPS            | TCP 21 in explicit mode <br>and 990 in implicit mode (FTPS) | Using TLS |
| FTP                   | TCP 21 (and 20)   | SFTP            | TCP 22 (SSH)                                                | Using SSH |
| HTTP                  | TCP 80            | HTTPS           | TCP 443                                                     | Using TLS |
| IMAP                  | TCP 143           | IMAPS           | TCP 993                                                     | Using TLS |
| LDAP                  | UDP/TCP 389       | LDAPS           | TCP 636                                                     | Using TLS |
| POP3                  | TCP 110           | POP3            | TCP 995 - Secure POP3                                       | Using TLS |
| RTP                   | UDP 16384 - 32767 | SRTP            | UDP 5004                                                    |           |
| SNMP                  | UDP 161/162       | SNMPv3          | UDP 161/162                                                 |           |
| Telnet                | TCP 23            | SSH             | TCP 22                                                      |           |

- Domain Name System Security Extensions (DNSSEC)
	- DNS information is not modified or malicious
	- Not provide confidentiality
	- Digital signatures
		- Matches the DNS record
	- Chain of trusts
		- IPSec keys
		- SSH fingerprints
		- And similar records

- Simple Network Management Protocol version 3 (SNMPv3)
	- Authentication of message sources
	- Message integrity validation
	- Confidentiality via encryption
	- Support multiple security levels
		- Only authPriv level uses encryption
			- *Insecure implementation SNMPv3 are still possible*

- Secure Shell (SSH)
	- Remote access to devices
	- Also often used as a **tunneling protocol** to support
		- SFPT
	- Authentication
		- SSH keys

- Hypertext Transfer Protocol over SSL/TLS (HTTPS)
	- Relies on TLS (old SSL)

- Secure Real-Time Protocol (SRTP)
	- Provide audio and video
	- Encryption
	- Authentication
	- RTP used paired protocols
		- RTP
		- RTCP
			- Monitor the Quality of Service (QoS)
			- Synchronization of streams
			- Secure equivalent **SRTP**

- Secure Lightweight Directory Access Protocol (LDAPS)
	- TLS protected version of LDAP
	- Confidentiality
	- Integrity 

### Email-Related Protocols

- Web-based email
	- Access via HTTPS
- Mail clients
	- Post Office Protocol (POP)
		- with TLS
			- **POPS**
	- Internet Message Access Protocol (IMAP)
		- with TLS
			- **IMAPS**

- **Secure/Multipurpose Internet Mail Extensions (S/MIME)**
	- *Standard* for email, provide not only plain text
	- Encrypt body and attachments
	- Sign
	- Authentication
	- Integrity
	- Nonrepudiation
	- Confidentiality
	- Requires a **certificate**
		- Locally generated 
		- Public Certificate Authority (CA)
	- Broad support

- **Simple Mail Transfer Protocol (SMTP)**
	- Not secure option
		- Use with S/MIME
			- For encrypt and secure messages
	- SMTPS
		- No broad usage
- **DKIM, DMARC and SPF**
	- Efforts ti make email more secure
	- Less spam

### File Transfer Protocols

- FTP
- **FTPS**
	- With **TLS**
- **SFTP**
	- With **SSH**
	- Easier 
	- SSH port (22)

### IPSec

- Suite of protocols
	- Encrypt
	- Authenticate IP traffic

- **Authentication Header (AH)**
	- Hashing
	- Shared secret key
	- Ensure integrity 
	- Validates senders
	- IP payload and headers are protected

- **Encapsulating Security Payload (ESP)**
	- Transport mode
		- Integrity
		- Authentication
		- Entire packet
	- Tunnel mode
		- Protects payload 
		- If used with authentication header
			- Can cause issues for networks that need to change IP or port information

- IPSec
	- VPN
		- Tunnel mode

# Network Attacks

## On-Path Attacks

- Man-in-the-Middle (MitM)

- Attack
	- SSL stripping
		- Removes TLS/SSL encryption
		- Force users use HTTP instead HTTPS
	- Phases
		- **User sends HTTP request** for a web page
		- **Attacker intercepts the server's HTTPS redirect** and removes/modifies it
			- **Keeping the connection on HTTP**
		- User continues on HTTP
			- Thinking the connection is secure
			- While attacker reads/modifies the traffic
	- Common implementations
		- Open wireless network
			- Where attacker can control the wireless infrastructure
				- Modify traffic

## Stopping SSL Stripping and HTTPS On-Path Attacks

- Protect SSL stripping attacks
	- Configuring systems to expect certificate for sites
		- Issued by a **known certificate authority**
			- Preventing certificates for alternate sites or self-signed 
	- Redirects to secure websites are target for attackers
		- Since unencrypted requests for the HTTP version of a site
			- Could be redirected to a site of the attacker's choosing
	- **HTTP Strict Transport Security (HSTS)** security policy
		- Prevent attack like these
			- That rely on *protocol downgrades and cookie jacking*
				- **Forcing browsers to connect only via HTTPS using TLS**
		- Work only after a user has visited the site al least once

- **Man-in-the-Browser (MitB) or (MiB)**
	- **Trojan** inserted into a user's browser
		- Able to *access and modify information sent and received* by the browser
		- **Browser plug-in or proxy**
	- Browser receives and decrypts information
		- **Bypass TLS** encryption
		- **Access sites with open sessions**
			- Or that **the browser is authenticated** to
	- Defences
		- Antimalware 
		- System configuration management
		- Monitoring 

- On-patch attack indicators
	- Changed network gateway or routes
	- Compromise network switches or routers

## Domain Name System Attacks

- **Domain hijacking**
	- Changes the registration of a domain
		- Technical means
			- Vulnerability with domain registrar
			- Control of a system belonging to an authorized user
		- Non technical
			- Social engineering
	- Domain's settings and configuration can be changed by attacker
		- Intercept traffic
		- Send and receive email
		- Appearing to be the legitimate domain holder
	- Detecting
		- User
			- Difficult
		- Owners
			- Security tools and features provided by domain registrar

- **DNS poisoning**
	- On-path attack
		- Attacker provides DNS response
			- While pretending to be an authoritative DNS server
	- Vulnerabilities in DNS protocols or implementations
		- Also permit DNS poisoning
			- Rarer
	- Poisoning the DNS cache on systems
		- Once a malicious DNS entry is in a system's cache
			- It will continue to use that information until the cache is purged or updated
		- Can be detected 
			- IDS or IPS, but difficult 
	- DNSSEC
		- Help prevent DNS poisoning and other DNS attacks
			- By validating both 
				- Origin of DNS information
				- Ensuring that the DNS responses have not been modified

- **URL redirection**
	- Can take many forms
	- One of the most common
		- Insert **alternate IP addresses into a system's hosts file** (etc/host)
			- Modified hosts files
				- Can be manually checked
				- Monitored by system security antimalware

- **Domain reputation**
	- DNS-related information
	- Provide information about whether a domain is a **trusted email sender**
		- Or sends a lot of spam email
	- In addition, organizations
		- May assign domain reputation score
			- Using their own email security and antispam tools

- DNS attack indicators
	- Changes in DNS resolution
	- Domain hijacking 
	- More

## Credential Replay Attacks

- **Credential Replay** attacks 
	- Network attack
	- Attacker be able to **capture valid network data**
		- And re-send it or delay it
			- So that the attacker's own use of the data is successful
		- **Re-send authentication hashes**
			- Modern implementations of authentication systems use 
				- **Sessions ID and encryption** to prevent 

- Common indicators
	- Modified gateways or routes 

## Malicious Code

- Worms
- Backdoors via networks
- Viruses
- Trojans
- Ransomware 

- Common indicators
	- Signatures
		- IDS and IPS can identify
	- Scanning and probing on ports and protocols associated with worms

## Distributed Denial-of-Service-Attacks

- Conducted from multiple locations, networks, or systems
	- Difficult to stop and hard to detect 
- Bring significant resources to bear on a targeted system or network
	- Potentially overwhelming the target

### Network DDoS

- Large-scale botnets 
- ISP
	- May provide a DDoS prevention service
		- If not
			- Ensure that your network border security devices have DDoS prevention capabilities

- **Volume-based**
	- Sheer amount of traffic
	- Amplification techniques 
		- Flaws or features in protocols and services
			- To create significantly more traffic
- **UDP floods**
	- Take advantage of the fact that UDP doesn't use three-way handshake like TCP 
	- Simply by sending massive amounts of traffic 
	- UDP is **not rate limited** or otherwise protected
	- Minimal resources on the attacking systems 
	- Detect
		- IDS, IPS and other network defences
		- Manually, packet analyzer 
- **ICMP floods**
	- **Rate limited** in modern OS 
	- Also called PING floods
	- Send massive numbers of ICMP packets
		- Each requesting a response 
	- Require **more aggregate bandwidth from attacker** than the defender has
	- Prevent
		- **Rate-limit or block ping** at network ingress points 
		- Rate-limit between security zones
	- Detect
		- Rules on network security devices
		- Manual 
	- Defence 
		- Relatively easy
			- ICMP traffic may be lost if the rate limit is hit 

- **Protocol-based**
	- **SYN floods**
		- Send the first step in three-way handshake 
			- And not response to the SYN-ACK
				- Thus consuming TCP stack resources
	- Modern attack
- Older attack
	- Ping of Death
		- Sent a ping packet too large for many to handle
	- Smurf attacks
		- Leveraged ICMP broadcast messages
			- With spoofed sender address
				- Causing systems throughout the broadcast domain
					- To send traffic to the purported sender 
						- Overhelming it
	- Fragmented packets
	- Packets with all TCP flags on (Xmas attacks)

- Identify a SYN DDoS 
	- Reviewing traffic aimed at a target host 
	- And noticing that there are massive numbers of SYN packets sent
		- Without the rest of the handshake being completed

- **Amplified Denial-of-Service attacks**
	- Volume-based
	- Protocols that allow a **small query to return large result like a DNS query**
	- Spoofing a system's IP address as a part of a query
		- Can result in a DNS server **sending much more traffic to the spoofed IP address**
			- Than was sent to the DNS server originally
				- **Amplifying a small amount of traffic into a large response**
	- Also take advantage of other type of DoS attack
		- **Reflected Denial-of-Service** attacks
			- The spoofed IP address causes a legitimate server to conduct the attack
			- Harder to know who the attacker is
	- Powerful combination 

>[!TIP] The final elements you'll need to know to be ready for the exam include secure protocols, including being familiar with them and being able to suggest replacement for insecure options. You'll also want to be familiar with common network attacks and how you might counter them with the tools and techniques you've reviewed in this chapter. Consider on-path, DNS, replay attacks, malicious code, and denial-of-service attacks and how you'd identify, prevent, and respond to each.

# Exam Essentials

- **The foundation of network security is a secure design.**
	- Attack surface of the network
	- Attached devices
	- Which drive placement and segmentation 
		- Into different security zones based on risk or security requirements
	- Understanding what will happen when failures occur
		- Dealing with those failures
		- Influences design and choices around HA
	- NAC and 802.1X 
		- Protect networks from untrusted devices being connected
	- Port security and port-level protections
		- Loop prevention
		- Broadcast storm protection
	- Network taps and monitoring ports
		- Allow packet capture by creating copy of traffic
	- VPN
		- Tunnel network traffic to another location
		- Encrypted or simply tunneled
	- Key concepts
		- Physical isolation
		- Logical segmentation
		- Use of secure protocols
		- Use of reputation services
		- Tools like software-defined networking
		- Zero trust
		- SD-WAN
		- SASE

- **Network appliances are used to provide security services to networks and systems.**
	- Jump servers
		- Provide a secure way to access systems in another security zone
	- Load balancers
		- Spread load among systems
		- Can use different scheduling options
		- Operational modes
			- Active/active or active/passive designs
	- Proxy servers
		- Centralize connection from a group of clients out to a server
			- Or from a group of server out to clients
			- Load-balancing strategy
	- Web filters
		- Filter content and URLs
		- Limit what information can enter and exit
		- Network based on rules
	- Data Loss Prevention
		- Monitor to ensure that data that shouldn't leave systems or network
			- Is identified and flagged, sent securely, or stopped
	- IDS and IPS
		- Identify and take action
		- Based on
			- Malicious behavior
			- Signatures
			- Anomalies in traffic
	- Data collection devices like sensors and collectors
		- Help with data gathering
	- Firewalls
		- Including 
			- Next-Generation Firewalls (NGFW)
			- Web Application Firewalls (WAF)
			- Unified Threat management (UTM)
				- Combine many of these security features and capabilities into a single appliance or system
		- Used to build security zones
		- Placed at trust boundaries
	- Access Control List (ACL)
		- Used by many devices
			- Including switch and routers
		- To determine what traffic can flow through them based on rules

- **Network security services and management techniques help make sure that a network stays secure.**
	- Out-of-band management
		- Puts management interfaces
			- On a separate VLAN, physical network or requires direct connection
	- DNS security
		- DNSSEC
			- Helps validate DNS servers and responses
		- DNS server
			- Must be properly configured
				- To prevent zone transfers and other DNS attacks
	- Email security 
		- DMARC, DKIM and SPF
			- To validate senders and domain
	- TLS
		- Broadly used to protect network traffic
		- Acting as a wrapper for many other protocols
	- Monitoring services and systems
		- Help ensure that they remain online and accessible
		- Require care due to the amount of information that can be generated
		- False positives are possible 
			- If the validation and monitoring does not fully validate service responses
	- File integrity monitors
		- Check to see if files have been changed
		- Can alert on change
		- Restore existing files to a pre-change or pre-deletion state
	- Honeypots, honeynets and honeytokens
		- Used to identify potential breaches and attackers
	- Network devices are hardened
		- Based on standards and benchmarks

- **Secure protocols provide way to send and receive information securely.**
	- Many original Internet protocols are not secure
		- Do not provide encryption or authentication
		- Can be captured and analyzed or modified
		- Key protocols
			- Voice and video
				- SRTP
			- Email
				- IMAPS 
				- POPS
				- Security protocols
					- DMARC
					- DKIM
					- SPF
			- File transfer
				- SFTP (SSH)
				- FTPS (TLS)
			- Directory services
				- LDAPS
			- Some protocols do not have a complete secure options
				- DNS
				- Routing
				- DHCP
				- All have limited options for secure communication 

- **Network attacks drive network security decisions and design.**
	- On-path attacks
		- Redirect traffic through a system that an attacker controls
		- Allow them to observe and potentially modify traffic
	- DNS attacks
		- Domain hijacking
		- DNS poisoning 
		- URL redirection
		- Partially countered through the use of DNSSEC
	- Credential replay attacks
		- Take advantage of poorly designed or insecure protocols
		- To send valid authentication hashes or other artifacts pretending to be a legitimate user
	- Malicious code
		- Worms
		- Denial-of-Service tool
	- Denial-of-Service attacks
		- Or DDoS
		- Consume resources or target services
		- Reflected-DoS
			- Use spoofed source addresses to cause traffic to be sent to targets
		- Amplified-DoS
			- Use small queries to get large results, amplifying their impact

#cybersecurity 
