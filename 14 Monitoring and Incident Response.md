# Chapter 14 - Monitoring and Incident Response

---

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.4. Given a scenario, analyze indicators of malicious activity.**

- Indicators (Account lockout, Concurrent session usage, Blocked content, Impossible travel, Resource consumption, Resource inaccessibility, Out-of-cycle logging, Published/documented, Missing logs)

**2.5. Explain the purpose of mitigation techniques used to secure the enterprise.**

- Application allow list
- Isolation
- Monitoring

## Domain 4.0 Security Operations

**4.4. Explain security alerting and monitoring concepts and tools.**

- Monitoring computing resources (Systems, Applications, Infrastructure)
- Activities (Log aggregation, Alerting, Scanning, Reporting, Archiving, Alert response and remediation/validation (Quarantine, Alert tuning))
- Tools (Benchmarks, Agents/agentless, Security information and event management (SIEM), NetFlow)

**4.8. Explain appropriate incident response activities.**

- Process (Preparation, Detection, Analysis, Containment, Eradication, Recovery, Lessons learned)
- Training
- Testing (Tabletop exercise, Simulation)
- Root cause analysis
- Threat hunting

**4.9. Given a scenario, use data sources to support an investigation.**

- Log data (Firewall logs, Application logs, Endpoint logs, OS-specific security logs, IPS/IDS logs, Network logs, Metadata)
- Data sources (Vulnerability scans, Automated reports, Dashboards, Packet captures)

---

# Incident Response

- Incident
	- Violation of the organization's policies and procedures or security practices
- Events
	- Observable occurrence, few of which are likely to be incidents

## The Incident Response Process

- **Preparation**
	- Build the tools, processes, and procedures to respond to an incident
- **Detection**
	- Reviewing events to identify incidents
- **Analysis**
	- Once an event has been identified as potentially being part of an incident, it needs to be analyzed 
- **Containment**
	- Contain incident to prevent further issues or damage
- **Eradication**
	- Removing the artifacts associated with the incident
- **Recovery**
	- Restoration to normal 

- **Lessons learned** session
	- Ensure that organizations improve and do not make the same mistakes again

### Preparing for incident Response

### Incident Response Team

- Member of management or organizational leadership
	- Responsable for making decisions
- Information security staff members
	- Specialized IR and analysis skills
		- Firewalls, IPS, and other security tools
- Technical experts
	- Systems administrators, developers, or others from disciplines throughout the organization
	- Depending on the nature of the incident
- Communications and public relations staff
	- Internal and external communications are handled well
- Legal and HR staff
	- Legal counsel can advise on legal issues, contracts, and similar matters
	- HR may be needed if staff were involved
- Law enforcement
	- Only in specific issues or attacks 

### Exercises

- **Tabletop exercises**
	- Talk through processes
- **Simulations**
	- Include variety of types of events
	- Simulate individual functions or elements of the plan, or only specific parts of an organization
	- Also be done at full scale, involving the entire organization in the exercise

### Building Incident Response Plans

- IR plans can include several subplans
	- May choose to combine them all into a single larger document 
	- Or may break them out to allow the response team to select the components that they need
- Individual plans may also be managed or run by different teams

- **Subplans**
	- Communication plans are critical to incident response processes.
	- Stakeholder management plans
		- Related to communication plans
	- Business Continuity (BC) plans
		- Focus on keeping an organization functional
	- Disaster Recovery (DR) 
		- Define the processes and procedures that an organization will take

### Policies

- Explain why an organization wishes to operate in a certain way
	- Define things like the purpose or objective of an activity or program
- Part of building an IR capability

- Identify the team and the authority that the team operates under
- Creation and maintenance of incident handling
- Response procedures and practices
- Define the overall IR process 
- Communication or compliance requirements that are included in the overall policy

- High-level statement of management intent that is used to convey the organization's expectations and direction for a topic.
- Standards
	- Specific guidance about what should be done
- Procedures
	- Used to implement standards
	- Guide how a task is done

- Organizations have many IT policies that can impact response 

## Training 

- Appropriate and regular training is required for incident responders
- Organizations like the Cybersecurity & infrastructure Security Agency (CISA)
	- Offer training for incident response 

## Threat Hunting

- Detection and analysis phases 
- Indicators of Compromise (IoC)

- **Account lockout**
	- Brute-force login attempts
	- Incorrect passwords used 
- **Concurrent session usage**
	- When users aren't likely to use concurrent sessions
	- Second device is in an unexpected or uncommon location
		- Or the application is one that isn't typically used on multiple devices at once
- **Blocked content**
	- Content that the organization has blocked
	- Via a DNS filter or other tool that prohibits
		- Domains, IP, or types of content from being viewed or accessed
- **Impossible travel**
	- User connecting from two locations that are far enough 
- **Resource consumption**
	- Filling up a disk or using more bandwidth than usual for uploads or downloads
- **Resource inaccessibility**
	- Can indicate that something unexpected is happening
- **Out-of-cycle logging**
	- Occurs when an event that happens at the same time or on a set cycle occurs at an unusual time
- **Missing logs**
	- May indicate that an attacker has wiped the logs to attempt to hide their actions

>[!TIP] Exam outline includes one other indicator type: published/documented. That type describes indicators that have been discovered and published or documented. Descriptions of IoCs are commonly distributed via threat feeds as well as through information sharing organizations. Should also make sure you know the incident response process as well as the list of common indicators. Be ready to analyze an indicator through a log entry or a scenario to determine what may have happened and if an incident should be declared.

## Understanding Attacks and Incidents

- Attack frameworks are used to understand adversaries, document techniques, and categorize tactics

### MITRE ATT&CK

- MITRE provides the ATT&CK
	- Or Adversarial Tactics, Techniques, and Common Knowledge
- Detailed descriptions, definitions, and example for the complete threat life cycle
	- From reconnaissance through execution, persistence, privilege escalation, and impact
- Lists techniques and components
	- Allowing threat assessment 

- Most comprehensive freely available database
	- Adversary techniques, tactics, and related information

# Incident Response Data and Tools

## Monitoring Computing Resources

- **System monitoring**
	- System logs
	- Central management tools
		- Including cloud services
	- System health and performance

- **Application monitoring**
	- Application logs
	- Application management interfaces
	- Performance monitoring tools

- **Infrastructure devices**
	- SNMP
	- syslog
	- Hardware vendors
		- Sell management tools and systems
			- Monitor and control infrastructure systems and devices 

## Security Information and Event Management Systems

- Central security monitoring tool
	- **SIEM**
- Collect and aggregate log data from a variety of sources
	- Systems, network security devices, network infrastructure, and many other
- Compare data, apply rules, analytical techniques, and ML or AI to the data.
- Review and alert 
	- User behavior
	- Sentiment analysis

- Packet capture
	- Capture and analyze raw packet data
		- Network traffic or other data sources
	- Incident analysis
	- Correlating with IDS or IPS events, firewall and WAF logs, and other security events

- Alerting, reporting and response capabilities
	- When an issue needs to be addressed
	- Track response to that issue through its life cycle
	- Forensic capabilities
	- Ticketing and workflow process to handle issues and events

### SIEM Dashboards

- Can be configured to show the information considered most useful and critical
- Multiple dashboards can be configured to show specific views and information
- High-level, visual representation of the information they contain
- Quickly identify likely problems, abnormal patterns, and new trends that may be of interest or concern

- Components that provide elements
	- Sensors
	- Trending and alerting capabilities
	- Correlation engines and rules
	- Methods to set sensitivity and levels

### Sensors

- Deployed to gather additional data
- Software agents, VM or dedicated device
- Often placed in environments like
	- Cloud, remote datacenter, or other locations
- May forward it in its original form or do some preprocessing
- Choosing where to deploy sensors is part of network and security architecture and design effort
- Must be secured and protected

### Sensitivity and Thresholds

- Control and limit the alerts that a SIEM can generate
- Set thresholds, filter rules, and use other methods of managing the sensitivity of the SIEM 
- Alerts
	- May be set to activate only when an event has happened a certain number of times
	- Or when it impacts specific high-value systems
	- Set to activate once instead of hundreds or thousands of times
- Help avoid alert fatigue and false positives

### Trends

- Can point to a new problem that is starting to crop up
- An exploit that is occurring and taking over
- Which malware is most prevalent in your organization

## Alerts and Alarms

- Categorized by their time and severity
	- Then provide detailed information
- Malware beaconing and infection
	- Automatically categorized, prioritized, marked by source and destination, and matched to an investigation by an analyst as appropriate
- Which sensor is reporting the issue

- **Alert tuning**
	- Modifying alerts to only alarm on important events
	- Setting thresholds, removing noise by identifying false alarms and normal behaviors
	- Ensuring tuning is not overly broad so that is ignores actual issues and malicious activity

- Alert fatigue
	- Alerts are sent so often, for so many events, that analysts stop responding to them
	- Creating noise
		- Aren't critical, high urgency, or high impact 
	- High proportion of false positives

## Log Aggregation, Correlation, and Analysis

- Matching data points to other data points is a key part
- Correlation requires 
	- Time that an event occurred 
	- What system or systems
	- What accounts were involved
	- And other
- SIEM allow search and filter data
- Automated correlation and analysis
	- Designed to match known events and IoC
		- To build a complete dataset for an incident or event that can then reviewed and analyzed
- Add tags and investigations to data

- Centralized logging tools
	- syslog-ng, rsylog, and similar tools
- Gather and analyze logs
	- SIEM, SOAR, and other 

## Rules

- The heart of alarms, alerts and correlation engines
- Rule conditions
	- Logic to determine if and when a rule will be actived
	- Then actions can trigger based on the rule
	- Results
		- Simple as an alert
		- Complex as a programmatic action that changes infrastructure
			- Enables or disables firewall rules
			- Trigger other defence

- Poorly constructed rule logic
	- May miss events
	- Cause false positive
	- Overly broad detections
- If the rule has an active response component
	- Mis-triggered rule can cause an outage or other infrastructure issue

- Rules need to be
	- Carefully build, tested, and reviewed on regular basis

- SIEM devices
	- Also follow the entire life cycle for data
		- Set retention and data lifespan for each type of data
	- Support for compliance requirements
		- Prebuilt rules or modules designed to meet specific compliance
	- Built-in integrations for cloud services
		- Like Google, ServiceNow, Office 365, Okta, Sophos and others
			- Can import data directly from those services 

### Log Files

- Provides incident responder with information about what has occurred
- Target for attackers
	- Make sure that the logs have not been tampered and time stamp and other data that is correct
- Windows Event Viewer
	- View logs for a single Windows system
- In enterprise environments
	- Specific logs or critical log entries will be sent to a secure logging infrastructure
		- To ensure a trustworthy replica of the logs 
	- Security practitioners will still review local logs
		- Because a complete copies of all logs for every system are not typically maintained

- Common logs
	- **Firewall logs**
		- Blocked and allowed traffic
		- NGFW or UTM provide Application-layer details
		- IDS/IPS related log information
	- **Application logs**
		- For Windows include
			- Installer information for application
			- Errors generated by applications
			- License check 
			- And others
		- Web servers and other devices
			- Logs from Apache and IIS
			- Track requests and related events
			- What was accessed, when, what IP sent the request
			- Can identify attacks
				- Like SQLi and others 
	- **Endpoint logs**
		- Application installation logs
		- System and service logs
		- Other logs
	- **OS-specific security logs**
		- For Windows
			- Failed and successful logins
			- Other authentication log information
		- For Linux
			- Stored in /var/log/auth.log and /var/log/secure
	- **IDS/IPS logs**
		- Insight into attack traffic that was detected
		- In case IPS, blocked
	- **Network logs**
		- Logs for routers and switches
		- Configuration changes
		- Traffic information
		- Network flows
		- Data captured by **packet analyzers**
			- Wireshark

- Security practitioners
	- SIEM tools
	- Manual search
		- `grep`and `tail` to review logs

## Going With the Flow

- Tracking bandwidth utilization
	- Bandwidth monitor
		- Provide trend information 
			- Spot current problems and new behaviors
- Network flows
	- Cisco's proprieraty
		- NetFlow protocol
			- Software-driven
		- sFlow
			- Broadly implemented in devices from many vendors
	- IPFIX
		- Open standard based on NetFlow v9

- Network flows
	- What traffic was sent on your network
	- Where it went
	- Where it came from
	- Source and destination of traffic
	- How much traffic was sent
	- When the traffic occurred

- Flows may not show all the traffic
	- Consume a large amount of network device processing power and storage
	- Lose some resolution and detail

### Logging Protocols and Tools

- How logs are sent to remote systems
- What tools are used to collect and manage logs
- How they are acquired 

- Linux logs
	- Sent via 
		- **syslog**
			- Clients sending messages to servers that collect and store the logs
	- When **speed** is necessary
		- **rsyslog**
			- Extremely high message rates
			- Secure logging via TLS
			- TCP-based messages
			- Multiple backend database options
	- Another
		- **syslog-ng**
			- **Enhanced filtering**
			- Direct logging to databases
			- Support sending via TCP protected by TLS
	- Final option
		- **NXLog**
			- Open source and commercially supported
			- syslog centralization and aggregation tool
			- Parse and generate log files in many common formats
			- Sending log to analysis tools and SIEM solutions

- Decisions about retention
	- On both local systems and central logging and monitoring infrastructure
- Take into account operational needs
	- Likely scenarios where you may need the logs you collect
- Legal
	- Compliance, or other requirements 
- In many cases
	- 30, 45, 90, or 180 days
- Hardware cost
- Potential legal challenges
	- If you retain logs that you may not wish to disclose in court.

## Digging Into systemd's Journal in Linux

- Most Linux distributions
	- Rely on **systemd**
		- To manage services and process
		- And the system itself 
- Systemd Journal 
	- Records what systemd is doing
- `journald`daemon 
	- Can be accomplished using **journalctl**

- **journalctl**
	- Review kernel
	- Services
	- `initrd` messages
	- And other that systemd generates

- Simply issuing the `journalctl`
	- Display all the journal entries

>[!TIP] Exam outline includes a large number of types of logging systems, logs, analysis tools, and other data sources. You should focus on thinking about why you might need each of them. Although you don't have master each of these log types, if one is completely unfamiliar to you, you may want to lear more about it so that you can read it and understand it if it shows up on the exam.

### Going Beyond Logs: Using Metadata

- **Matadata**
	- Generated as a normal part of system operations, communications and other activities
	- Can also used for incident response
	- Data about other data
	- In case of systems and services
		- Is created as part of files
		- Embedded in documents
		- Used to define structured data
		- Included in transactions
		- Network communication
		- Many other

- **Common example**
	- **Email metadata**
		- Headers and other information found in an email
			- Details about the sender, the recipient, the date and time the message was sent, attachment
			- Which systems the email traveled through, and other header markup
	- **Mobile metadata**
		- Collected by phones and other mobile devices
		- Call logs, SMS and other message data, data usage, GPS location tracking, cellular tower information, and other details found in call data records
		- Geospatial information
	- **Web metadata**
		- Embedded into websites as part of the code
		- Metatags, headers, cookies, and other information
		- Help with seach engine optimization, website functionality, advertising and tracking
	- **File metadata**
		- When a file was created, how it was created, if and when it was modified, who modified it, the GPS location of the device that created it, and many others

- Metadata is commonly used for forensic and other investigations

### Other Data Sources

- Can be acquired using **agents**
	- Special-purpose software deployed to systems and devices 
	- That send the logs to a log aggregator or management system
- Or **agentless**
	- Simply send the logs via standardized log interfaces like syslog 

- **Vulnerability scans**
	- Provide information about scanning activities
- **Packet captures**
	- Review the traffic network
		- As part of incident response or troubleshooting activities

- **Automated reports**
	- From various systems and service
- **Dashboards**
	- Available via management tools and administrative control panels

## Benchmarks and Logging

- **Benchmarks**
	- A key tool as part of alerting and monitoring
	- Often include log settings
- Well-constructed benchmark
	- Central logging
	- Configuring log and alerting levels
	- Endpoints or servers log critical and important events

- Ensuring that all is configured to log important information
- In useful ways to support security operations

## Reporting and Archiving

- **Reporting**
	- On log information is part of the overall log management process
	- Identifying trends
	- Providing visibility into changes in the logs 
		- That may indicate issues or require management oversight

- **Archiving logs**
	- When they must be retained but are not in active use
	- Helps to make sure space is available in SIEM and other devices
	- Keeps the logs to a manageable size for analysis
	- Time frame like 30, 60, 90, or 180 days for log retention
		- Before archiving or deletion

>[!TIP] As you consider monitoring, SIEM, log aggregation, and log and event analysis, make sure you understand why log aggregation is important, and how SIEM and NetFlow play into understanding what an organization is doing. Be prepared to explain alerts, reporting, archiving, and how logs and analysis are used throughout the entire incident response process. 

# Mitigation and Recovery

>[!TIP] Exam focuses on mitigation efforts and does not delve into recovery. As you read this section of the chapter, remember the incident response flow from the beginning of the chapter and think about how you would support recovery and incident response goals as you mitigate the incident. But remember that the focus of the exam will be on how to stop the incident and secure systems, not on how to bring them back to normal.

## Security Orchestration, Automation, and Response (SOAR)

- To determine security posture and status
	- Requires integrating different data sources
- Managing security operations
- Remediating issues identified 
- Mitigation and recovery tool
	- Assess the attack surface 
	- State of systems
	- Where issues may exist
	- Automation of remediation and restoration workflows

## Containment, Mitigation, and Recovery Techniques

- First mitigation techniques
	- Block the cause 

- **Application allow lists**
- **Application deny/block lists**
- **Isolation** or quarantine 
	- Help investigations
- **Monitoring**

>[!TIP] Pay particular attention to the concepts of segmentation, access control through ACLs and permissions, application allow lists, and isolation.

- **Configuration changes**
	- Carefully tracked and recorded
	- May have to be rolled back
- **Firewall rule changes**
- **Mobile Device Management changes**
- **Data Loss Prevention (DLP) changes**
- **Content filter and URL filtering capabilities**
- **Updating or revoking certificates**
- Many others...

- **Broader action may also be necessary**
	- Removing systems, devices, or entire network segments or zones
- **Isolation**
	- Move system into a protected space or network
	- Removing system from the network or isolation VLAN
	- In case of VM or cloud infrastructure
		- Moving the system to an environment with security rules
			- Keep it isolated while allowing inspection and investigation
- **Containment**
	- Leaves the system in place 
	- But works to prevent further malicious action or attacks
	- Network-level containment
		- Firewall rules or similar
			- Limit the traffic that the system can send or receive
	- System and application-level
		- Can be more difficult without shutting down the system or interfering with the functionality and state of the system
			- Which can have an impact on forensic data
	- Decision about containment actions can have an impact on future investigative work
	- Incident responder may have different goals than forensic analyst and organizations may have to make quick choices about whether rapid response or forensic data is more important in some situations
- **Segmentation**
	- Employed before an incident occurs
	- Place systems with different functions or data security level 
		- In different zones or segments of a network
	- Can be done in virtual and cloud environments
	- Using security, network, or physical machine boundaries to build separation 
		- Between environments, systems, networks, or other components
	- Segment infected systems
		- Away from the rest of the network
	- Move crucial systems to a more protected segment

## Root Cause Analysis

- Once mitigated issues and are on the path to recovery
	- Perform a **Root Cause Analysis (RCA)**
	- Identifying the underlying cause for an issue or compromise
	- Identifying how to fix the problems that allowed the vent or incident
	- Ensuring that any systemic issues that led to the problem are also addressed

- Common techniques used in RCA
	- Five whys
		- Ask why multiple times to get to the underlying reason for an event or issue
	- Event analysis
		- Determines if it's the root cause or occurred because of the root cause
	- Diagramming cause and effect
		- Help determine whether each event was a cause or an effect
		- Fishbone diagrams are often used

- Feed the preparation phase of the cycle to avoid future issues of the same type

>[!TIP] Mitigation and recovery processes requires an understanding of allow and deny lists, isolation, quarantine, and, of course, ongoing monitoring to ensure that the remediation efforts were successful. Finally, be ready to explain what root cause analysis is and why it's important as part of the recovery and preparation process.

# Exam Essentials

- **The incident response cycle and incident response process outline how to respond to and incident.**
	- Incident response cycle
		- Preparation
		- Detection
		- Analysis
		- Containment
		- Eradication
		- Recovery
		- Lessons learned
	- May not be in a single phase at a time
	- Phases may move forward and backward
		- Depending on discoveries and further events
	- Organization train their staff and hold exercises
		- Tabletop exercises
		- Walk-throughs
		- Simulations

- **Threat hunting uses data to identify potential indicators of compromise.**
	- IoCs are a critical part of a modern threat hunter's toolkit
	- They include detecting things like
		- Account lockout
		- Concurrent session usage
		- Impossible travel
		- Attempted access to blocked content
		- Resource consumption
		- Resource inaccessibility
		- Out-of-cycle logging
		- Missing logs
		- Many others
	- IoCs are documented and published
		- Threat feeds and other services and sources

- **Data sources and data management or incident response provide insight into what occurred as well as investigative and detection tools.**
	- Security Information and Event Management (SIEM) tools
		- Gather and analyze data using dashboards
		- Automated analysis
		- Manual investigation capabilities
		- Information such as
			- Vulnerability scan output
			- System configuration data
			- System and device logs
			- And other data are *ingested* and *analyzed*
				- To provide broad insight into events and incidents
	- Network traffic information
		- Gathered using
			- NetFlow, sFlow, and packet analyzers, among other tools
		- Bandwidth usage
		- Which systems communicated
		- Ports and protocols in use
		- Time and date
		- Other high-level information
			- Useful for incident analysis
	- In addition to log and event information
		- Matadata from files and other locations
			- Used for incident investigation and incident response

- **Mitigation techniques ensure that the impact of incidents are limited.**
	- Incident responders use a variety of techniques to mitigate and contain and recover from incidents
	- Common task
		- Change configuration
			- Allow lists or block/deny lists
			- Quarantining files or devices
			- Making firewall changes
			- MDM or DLP tools
			- Adding content or URL filtering rules
			- Revoking or updating certificates
	- At network and infrastructure level
		- Isolation
		- Containment
		- Segmentation
	- Root cause analysis
		- Determine why an incident was able to happen
		- Why it happen
		- Guide preparation work to avoid future incidents

#cybersecurity 