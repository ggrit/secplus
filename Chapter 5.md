# Chapter 5 - Security Assessment and Testing

---
## Domain 4.0: Security Operations

**4.3. Explain various activities associated with vulnerability management.**

- Identification methods (Vulnerability scan, Penetration testing, Responsible disclosure program, Bug bounty program, System/process audit)
- Analysis (Confirmation, Prioritize, Common Vulnerability Scoring System (CVSS), Common Vulnerabilities and Exposures (CVE), Vulnerability classification, Exposure factor, Environmental variables, Industry/organizational impact, Risk tolerance)
- Vulnerability response and remediation (Patching, Insurance, Segmentation, Compensating controls, Exceptions and exemptions)
- Validation of remediation (Rescanning, Audit, Verification)
- Reporting

**4.4. Explain security alerting and monitoring concepts and tools.**

- Tools (Security Content Automation Protocol (SCAP), Vulnerability scanners)

**4.8. Explain appropriate incident response activities.**

- Threat hunting
## Domain 5.0: Security Program Management and Oversight

**5.3. Explain processes associated with third-party risk assessment and management.**

- Rules of engagement  

**5.5. Explain types and purposes of audits and assessments.**

- Attestation
- Internal (Compliance, Audit committee, Self- assessments)
- External (Regulatory, Examinations, Assessment, Independent third-party audit)
- Penetration testing (Physical, Offensive, Defensive, Integrated, Known environment, Partially known environment, Unknown environment, Reconnaissance, Passive, Active)

---

# Vulnerability Management

- Identifying
- Prioritizing
- Remediating

- Use Vulnerability scanning to detect and then implement remediation workflow

## Identifying Scan Targets

- Asset inventory
- Asset criticality information (witch systems are critical and witch are noncritical)
- Types of scans
- Frequency of scans
- Priority on remediating 

## Determining Scan Frequency

- Organization's risk appetite
- Regulatory requirements (PCI DSS, FISMA, or corporate policies...)
- Technical constraints (may limit the frequency of scanning)
- Business constraints (may limit scans during periods of high business acticity)
- Licensing limitations (limit on bandwidth or number of scans)

## Configuring Vulnerability Scans

- Configure many different parameter related to scans

### Scan Sensitivity Levels

- Settings determine the types of checks
- Customized to ensure scan meets its objectives

### Supplementing Network Scans

- Basic vulnerability scans run over a network (simulating what an attacker might see)
- Firewall, IPS and other security controls may affects the scan result 
- Modern vulnerability management can supplement these remote scan with trusted information
	- Provide scanner with credentials (with read-only account for least privilege)

>[!TIP] Credentialed scanning: improving the scan's accuracy, scanner can retrieve configuration information with access operating systems, databases, and applications, among other sources.

- Traditional server-based scanning
- Agent-based scanning:
	- Install small software agents on each target server
	- Conduct scans of the server configuration
	- Inside-out scan

### Scan Perspective
- Scan from a different location on the network, providing different view into vulnerabilities
	- External scan: from the Internet
	- Internal scan: scanner on the general corporate network
- Internal scanner and agents located on the servers offer the most accurate view
- External scan might be affected by security controls like:
	- Firewall
	- Network segmentation
	- IDS & IPS

## Scanner Maintenance

- Ensure that scanning software and _vulnerability feeds_ remain up-to-date

### Scanner software

- Scanning systems aren't immune from vulnerabilities

### Vulnerability Plug-in Feeds

- Configure scanners to retrieve plug-ins on regular basis, preferably daily

## Security Content Automation Protocol (SCAP)

- **CCE:** Common Configuration Enumeration
- **CPE:** Common Platform Enumeration
- **CVE:** Common Vulnerabilities and Exposures
- **CVSS:** Common Vulnerability Scoring System
- **XCCDF:** Extensible Configuration Checklist Description
- **OVAL:** Open Vulnerability and Assessment Language

## Vulnerability Scanning Tools

- Network Vulnerability Scanner
- Application Scanner
- Web Application Scanner

### Infrastructure Vulnerability Scanning

- Tenable Nessus
- Qualys
- Rapid7 Nexpose
- OpenVAS (GreenBone)

### Application Testing

- **Static testing** analyzes code without executing it
- **Dynamic testing** execute code as part of the test, running all the interfaces that the code expose to the user with a variety of inputs, searching for vulnerabilities
- **Interactive testing** combine static and dynamic

### Web Application Scanning

- Web specific vulnerabilities
	- SQL injection
	- Cross-site scripting **XSS**
	- Cross-site request forgery **CSRF**
- Tools
	- Nikto
	- Arachni
	- Acunetix

## Review and Interpreting Scan Reports

- Name of the vulnerability
- Overall severity (Low, Medium, High, Critical)
- Detailed description of the vulnerability
- Solution
- _"See Also"_ provides references for more details
- Output (verbatim)
- Ports/hosts
- Vulnerability information (some miscellaneous information)
- Risk information (assessing the severity, CVSS)
- Plug-in Details (version)

### Understanding CVSS

- **Common Vulnerability Scoring System**

>[!TIP] Component of **SCAP**. Framework that provides a score from 0 to 10. Often refer to **CVE** list of publicity know vulnerabilities that contain ID number, description, and reference.

- 8 different measures
	- First 4 evaluate **exploitability**
	- Last 3 evaluate the **impact**
	- Eight evaluate the **scope**

- Attack Vector metric (AV)
- Attack Complexity metric (AC)
- Privileges Required metric (PR)
- User Interaction metric (UI)
- Scope metric (S)
- Confidentiality metric (C)
- Integrity metric (I)
- Availability metric (A)

## Interpreting the CVSS Vector

###### Example: **CVSS:3.0/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N**

- CVSS Version: 3.0
- **Attack Vector**: Network, Adjacent, Local, Physical
- **Attack Complexity**: Low, High
- **Privilege Required**: None, Low, High
- **User Interaction**: None, Required, 
- **Scope**: Unchanged, Changed
- **Confidentiality**: None, Low, High
- **Integrity**: None, Low, High
- **Availability**: None, Low, High

### Summarizing CVSS Scores

- CVSS *base score* is a single number representing the overall risk

### Categorizing CVSS Base Score

| **CVSS Score** | **Rating** |
| -------------- | ---------- |
| 0.0            | None       |
| 0.1 - 3.9      | Low        |
| 4.0 - 6.9      | Medium     |
| 7.0 - 8.9      | High       |
| 9.0 - 10       | Critical   |

>[!TIP] CVSS severity rating scale are a common topic for exam questions!

## Confirmation of Scan Results

- Investigation to confirm the presence and severity of vulnerabilities.

### False Positives

- Scanner report a vulnerability that does not exist, is false positive

- Scanner report a vulnerability: positive report
	- Report accurate: True positive report
	- Report inaccurate: False positive report
- Scanner not report a vulnerability: negative report
	- Report accurate: True negative report
	- Report inaccurate: False negative report

>[!TIP] Focus on false positives and false negatives. Must understand the types of errors that might occur in vulnerability reports and be prepared to identify them in scenarios on the exam.

### Reconciling Scan Results with Other Data Sources

- **Log reviews** from servers, applications, network devices and other sources
- **Security information and event management (SIEM)**
	- Correlate log entries from multiple sources and provide actionable intelligence
- **Configuration management systems**
	- Provide information on OS and applications installed on a system

# Vulnerability Classification

- Thousand of possible vulnerabilities

## Patch Management

- Security patches to systems should be routine task

## Legacy Platforms

- Vendor discontinue support
- If an organization must continue using an unsupported OS best practice dictates isolating the system and applying compensating security measures

>[!TIP] Good vulnerability response and remediation practices include:
>- Patching
>- Insurance
>- Segmentation
>- Compensating controls
>- Exceptions
>- Exemptions

## Weak Configurations

- Default setting (administrator set up pages...)
- Default credentials or unsecured accounts
- Open service ports (that are not necessary)
- Open permissions (violate the principle of least privilege)

## Error Messages

- **Debug modes:** Give error information for troubleshoot
	- Useful for developers, can assist an attacker
- Disable debug modes on systems with public exposure
	- Developers should conduct their testing only on systems dedicated to that purpose

## Insecure Protocols

- Solution simply switch to a more secure protocol

## Weak Encryption

- Encryption protect stored data and data in transit over networks
- Should update to a more secure cipher, such Advanced Encryption Standard (**AES**)

# Penetration Testing

- Use technicals tools to test an organization security 

## Adopting the Hacker Mindset

- Find vulnerability that might exploit 
- Conduct reconnaissance
- Gather information about security controls

## Reasons for Penetration Testing

- Provides visibility into the organization's security posture that simply isn't available by other means 

## Benefits of Penetration Testing

- Knowledge that we can't obtain elsewhere
- Provides us with important blueprint for remediation
- Provide actionable insight that can prevent a vulnerability from initial exposure

## Threat Hunting

- Search for the artifacts/evidence of a successful attack
- Ask yourself what a hackers might do and what type of evidence they might leave behind
- Conduct post-mortem analysis of the factor that contributed to the compromise

## Penetration Test Types

- **Physical Penetration** testing 
	- Breaking into buildings, compromising surveillance systems
- **Offensive Penetration** testing
	- Identify and exploit vulnerabilities in network, systems, and application
- **Defensive Penetration** testing 
	- Assessing the effectiveness of security policies, procedures, and technologies in detecting and mitigating threats
- **Integrated Penetration** Testing
	- Offensive and Defensive

### Typical environment classifications

- **Know environment**
	- Fully knowledge of the underlying technology
	- Credentials
	- Often more complete test
	- Not provide what an attacker see
	- Controls may by bypassed
- **Unknown environment**
	- Replicate what an attacker encounter
	- Must gather information
	- Discover vulnerabilities like an attacker
	- Skill of pentester is very important
- **Partially know environment**
	- Some information
	- Can help focus pentest time and effort
	- More accurate view than what an attacker sees

>[!TIP] Differentiate and explain 4 major categories and 3 classification types of penetration testing

## Rules of Engagement

- **Timeline** (when conduct test)
- What **locations, systems, applications** or other potential target (like **third-party service**)
- **Data handling** requirements (confidentiality requirements, encrypting sensitive data during and after test)
- What **behaviors** to expect from the target (defenses may limit penetration testing)
- What **resources** are committed
- **Legal concerns**
- When and how **communications** will occur

## Permission

- Before penetration test, should have appropriate permission

## Reconnaissance

- **Passive reconnaissance** techniques seek to gather information without directly engaging with the target
	- OSINT
	- Lookups of domain
		- DNS and WHOIS queries
	- Web search, review public website
- **Active reconnaissance**
	- Scanning ports
	- Footprinting (identify OS and Applications in use)
	- Vulnerability scanning

>[!TIP] Know difference between passive and active reconnaissance techniques. Passive not directly engage the target and Active directly engage the target.

- War driving
- War flying

## Running the Test

- Initial access
- Privilege escalation
- Pivoting or lateral movement
- Persistence

## Cleaning Up

- Remove any tools installed on systems
- Remove any persistence mechanism
- Close-out report with details on the vulnerabilities and advice on improving

# Audit and Assessments

- Security Tests
- Security Assessments
- Security Audits

## Security Tests

- Verify that a control is functioning properly
	- Automated scans
	- Tool-assisted penetration tests
	- Manual attempts to undermine security
	- Key security controls
- Security teams design and validate a comprehensive assessment and testing strategy
	- Automated tests and manual tests
- Risk-prioritized approach
- Review the results

## Responsible Disclosure Programs

- Allow security researchers to securely share information about vulnerabilities in a product with the vendor.
- Bug Bounty

## Security Assessments

- Comprehensive review of the security of a system, application, or other tested environment
- Risk assessment that identifies vulnerabilities
- Use security testing tools
- Thoughtful review of the threat environment
	- Current and future risk
	- Value of targeted environment
- Assessment report addressed to management
	- Specific recommendations for improving security
- Conducted by internal team or third-party

## Security Audits

- Same techniques of security assessments but performed by independent auditors
- Unbiased view
- Impartial
- Report similar to security assessments but different audience
	- Organization's board of directors, government regulator, third-party
- Outcome of an audit is an attestation

### Internal Audits

- Internal audit staff
- Chief Audit Executive (CAE) report directly CEO, or similar role
- Compliance obligation
- Self-assessments

### External Audits

- Independent third-party
- Big 4 Audit firms
	- Ernst & Young
	- Deloitte
	- PricewaterhouseCoopers (PwC)
	- KPMG

### Independent Third-Party Audits

- Request comes from a regulator, customer, or outside entity
- SSAE18 Common standard

>[!TIP] Only difference between external and third-party audits is who is requesting the audit. 

### Auditing Standards

- **COBIT** common framework, maintained by:
	- ISACA
	- CISA
	- CISM
- **ISO 27001**
- **ISO 27002** more detail on specific of information security control

# Vulnerability Life Cycle

- Identification
- Analysis
- Response and Remediation
- Validation of Remediation
- Reporting

## Vulnerability Identification

- Vulnerability scans
- Penetration tests
- Reports from responsible disclosure or bug bounty programs
- System and process audits

## Vulnerability Analysis

- Confirm vulnerability exist and is not false positive
- Prioritizing and categorizing (CVSS and CVE)
- Organization specific details
	- Exposure factor
	- Environment variables
	- Industry and organizational impact
	- Risk tolerance

## Vulnerability Response and Remediation

- Patch or other corrective measure
- Network segmentation to isolate
- Implement complementing controls (like firewall, IPS)
- Purchase insurance
- Formal risk acceptance strategy

## Validation of Remediation

- Rescanning affected system and verifying that the vulnerability no longer appears

## Reporting

- Communicating the finding, actions taken and lesson learned
- Report may include:
	- Summarizing the vulnerabilities identified, analyzed, and remediated, along with their initial severity and impact on the organization
	- Proving details on the remediation 
		- Actions taken
		- Patches applied
		- Compensating controls implemented
		- Risk acceptance decisions made
	- Highlighting any trends, patterns, or areas requiring further attention
	- Recommendation for improvements
		- Vulnerability management process
		- Security policies
		- Employee training programs

# Exam Essentials

**Many vulnerabilities exist in modern computing environments.**
- On-premises and Cloud
- Improper or weak patch management
- Weak configuration settings
	- Open permissions
	- Unsecured root accounts
	- Weak encryption
	- Insecure protocol
	- Default settings
	- Open ports and services
- Scan detect a vulnerability does not exist: false positive
- Scan don't detect a vulnerability does exist: false negative

**Threat hunting discovers existing compromises.**
- Presume that organization is already compromised and search indicator of those compromises
- Use of advisories, bulletins, and threat intelligence feeds in an intelligence fusion program
- Search signs that attackers gained initial access

**Vulnerability scans probe systems, applications, and devices for known security issues.**
- Scan application, network and web application
- Credentialed (more accuracy) or non credentialed
- Intrusive or non intrusive
- Review logs and configuration for additional context
- Described using CVE and CVSS (SCAP components)

**Penetration testing place security professionals in the role of attackers.**
- Known environment
- Unknown environment
- Partially known
- RoE: Rules of Engagement
- Begin with reconnaissance
	- Passive information gathering
	- Active information gathering
- War driving
- War flying
- Footprinting
- OSINT
- Use this information for:
	- Gain initial access
	- Privilege escalation
	- Lateral movement/pivoting
	- Persistence
- Cleanup activities

**Bug bounty programs incentivize vulnerability reporting.**
- Allow external security professionals to probe the security of an organization's public-facing systems

**Recognize the purpose and types of security audits.**
- Internal
- External
- Third-party
- At conclusion makes an attestation

**Understand the stages of a vulnerability life cycle.**
- Identification
	- Scans
	- Penetration test
	- Responsible disclosure
	- Bug bounty
	- Audit
- Analysis
	- Confirm vulnerability
	- Prioritizing with CVE, CVSS and organization specific factor
- Response and remediation
	- Apply patches
	- Isolating affected systems
	- Implement compensating controls (firewall, IPS)
	- Insurance
	- Formally accepting the risk
- Validation of remediation
	- Rescanning for ensures the vulnerability is no longer present
- Reporting
	- Inform stakeholders
	- Findings
	- Actions 
	- Trends
	- Recommendation for improvement

#cybersecurity 