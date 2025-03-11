# 16 Security Governance and Compliance

---

## Domain 1.0: General Security Concepts

**1.3. Explain the importance of change management processes and the impact to security.**

- Business processes impacting security operation (Approval process, Ownership, Stakeholders, Impact analysis, Test results, Backout plan, Maintenance window, Standard operating procedure)
- Technical implications (Allow lists/deny lists, Restricted activities, Downtime, Service restart, Application restart, Legacy applications, Dependencies)
- Documentation (Updating diagrams, Updating policies/procedures)
- Version control

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.5. Explain the purpose of mitigation techniques used to secure the enterprise.**

- Least privilege

## Domain 5.0: Security Program Management and Oversight

**5.1. Summarize elements of effective security governance.**

- Guidelines
- Policies (Acceptable use policy (AUP), Information security policies, Business continuity, Disaster recovery, Incident response, Software development lifecycle (SDLC), Change management)
- Standards (Password, Access control, Physical security, Encryption)
- Procedures (Change management, Onboarding/offboarding, Playbooks)
- External considerations (Regulatory, Legal, Industry, Local/regional, National, Global)
- Monitoring and revision
- Types of governance structures (Boards, Committees, Government entities, Centralized/decentralized)

**5.3. Explain the processes associated with third-party risk assessment and management.**

- Vendor assessment (Penetration testing, Right-to-audit clause, Evidence of internal audits, Independent assessments, Supply chain analysis)
- Vendor selection (Due diligence, Conflict of interest)
- Agreement types (Service-level agreement (SLA), Memorandum of agreement (MOA), Memorandum of understanding (MOU), Master service agreement (MSA), Work order (WO)/Statement of Work (SOW), Non-disclosure agreement (NDA), Business partners agreement (BPA))
- Vendor monitoring
- Questionnaires
- Rules of engagement

**5.4. Summarize elements of effective security compliance.**

- Compliance reporting (Internal, External)
- Consequences of non-compliance (Fines, Sanctions, Reputational damage, Loss of license, Contractual impacts)
- Compliance monitoring (Due diligence/care, Attestation and acknowledgement, Internal and external, Automation)

**5.6. Given a scenario, implement security awareness practices.**

- Phishing (Campaigns, Recognizing a phishing attempt, Responding to reported suspicious messages)
- Anomalous behavior recognition (Risky, Unexpected, Unintentional)
- User guidance and training (Policy/handbooks, Situational awareness, Insider threat, Password management, Removable media and cables, Social engineering, Operational security, Hybrid/remote work environments)
- Reporting and monitoring (Initial, Recurring)
- Development
- Execution

---

# Security Governance

- Governance
	- Set of procedures and controls
	- Coordinate the development and execution of strategic plans

## Corporate Governance

- Corporate governance programs
	- Organization sets an appropriate strategic direction
	- Develops a plan to implement that strategy
	- Executes its strategic plan
- Hierarchical model (common for publicly traded corporations)
	- Shareholders
	- Board of Directors
	- Chief Executive Officer
	- Management Team
- Best practice
	- Majority of the members of the board to be *independent directors* 

- Hired by the board
	- Chief Executive Officer (CEO)
	- Hire
		- Team of executives
		- Hire
			- Managers
			- Hire
				- Individual contributors

- Nonprofit organizations follow a similar model
	- Major difference
		- Board members
			- Elected by the membership
			- Elected in a "self-perpetuating" model
				- Current board vote to elect new board members
- Privately owned organizations
	- May follow many different governance models
		- For example
			- The sole owner of a corporation may also serve as the CEO or carry out the functions of a board on their own
			- Multiple owners may each appoint a number of board members proportional to their ownership stake
- Many possibile variations
	- The key point is that 
		- The owners control the organization
			- Either directly or through a board that they control

## Governance, Risk, and Compliance Programs

- GRC programs integrate three related tasks
	- Governance of the organization
	- Risk management
	- Compliance

## Information Security Governance

- CEO delegates information security responsibility to
	- Chief Information Security Officer (CISO) or other responsible executive

- CISO
	- Design and implement an *information security governance framework*
		- Guides the activity of the information security function
		- Ensures alignment with the organization's information security strategy
		- Mechanisms that the security team will use to enforce security requirements 

## Types of Governance Structures

- **Centralized governance**
	- Top-down approach
	- Central authority creates policies and standards, which are then enforced throughout the organization
- **Decentralized governance**
	- Bottom-up approach
	- Individual business units are delegated the authority to achieve cybersecurity objectives and then may do so in the manner they see fit

>[!TIP] Tell the difference between centralized and decentralized governance models.

- In addition to using a formal board of directors
	- May incorporate a variety of internal committees 
		- Consisting of subject matter experts (SMEs) and managers

- Government entities
	- Such as **regulatory agencies**
		- May also play a role in the governance of some organizations
- For example, banks may be regulated by the US Treasury Department

# Understanding Policy Documents

- Information Security policy framework
	- Policies
	- Standards
	- Procedures
	- Guidelines

- External consideration that may impact policies
	- Regulatory and legal requirement 
	- Industry-specific considerations
	- Jurisdiction-specific consideration

## Policies

- High-level statements of management intent
- Compliance with policies is mandatory
- Infosec policy contain broad statements about cybersecurity objectives
	- A statement of the importance of cybersecurity to the organization
	- Requirement that all staff and contractors take measures to protect the CIA of information and information systems
	- Statement on the ownership of information created and/or possessed by the organization
	- Designation of the CISO or other individual as the executive responsible for cysec issues
	- Delegation of authority granting the CISO the ability to create standards, procedures, and guidelines that implement the policy 
- Requires very high-level approval, often from the CEO

- Infosec policy library
	- **Information Security policy**
		- Provides high-level authority and guidance for the security program
	- **Incident Response policy**
		- Describes how the organization will respond to security incidents
	- **Acceptable Use Policy (UAP)**
		- Provides network and system user with clear direction on permissible uses of information resources
	- **Business continuity and Disaster recovery policies**
		- Outline the procedures and strategies to ensure that essential business functions continue to operate during and after a disaster, and that data and assets are recovered and protected
	- **Software Development Life Cycle (SDLC) policy**
		- Establishes the processes and standards for developing and maintaining software, ensuring that security is considered and integrated at every stage of development
	- **Change management and Change control policies**
		- Describe how the organization will review, approve, and implement proposed changes to information systems in a manner that manages both cybersecurity and operational risk

>[!TIP] The policies listed here are specifically mentioned in the exam objectives. Be sure that you're familiar with the nature and purpose of policies related to information security, incident response, acceptable use, business continuity, disaster recovery, SDLC, and change management as you prepare for the exam.

## Standards

- Mandatory requirements describing how an organization will carry out its information security policies
	- Configuration settings used for a common OS
	- Controls that must be put in place for highly sensitive information
	- Any other security objective 
- Approved at a lower organizational level than policies
- May change more regularly

- Types of standards
	- **Password standards**
		- Set forth requirements for password length, complexity, reuse, and similar issues
	- **Access Control standards**
		- Describe the account life cycle from provisioning through active use and decommissioning
		- Should include specific requirements for personnel who are employees of the organization as well as third-party contractors
		- Also include requirements for credentials used by devices, service accounts, and administrator/root accounts
	- **Physical Security standards**
		- Guidelines for securing the physical premises and assets of the organization
		- Includes security measures like access control systems, surveillance cameras, security personnel, and policies regarding visitor access, protection of sensitive areas, and handling of physical security breaches
	- **Encryption standards**
		- Specify the requirements for encrypting data both in transit and at rest
		- Selection of encryption algorithms, key management practices, and the conditions under which data must be encrypted to protect the confidentiality and integrity of information

>[!TIP] Be sure that you're familiar with the nature and purpose of standards related to passwords, access control, physical security, and encryption as you prepare for the exam.

## Procedures

- Detailed, step-by-step processes that individuals and organizations must follow in specific circumstances
	- Ensure a consistent process for achieving security objective
- Compliance with procedures is mandatory

- Common procedures
	- **Change management procedures**
		- Describe how the organization will perform change management activities that comply with the organization's change management policy, including the possible use of version control and other tools
	- **Onboarding and Offboarding procedures**
		- Describe how the organization will add new user accounts as employees join the organization and how those accounts will be removed when no longer needed
	- **Playbooks**
		- Describe the actions that the organization's *incident response team* will take when specific types of incidents occur

>[!TIP] Be sure you're familiar with the nature and purpose of procedures related to change management, onboarding, offboarding, and playbooks as you prepare for the exam.

## Guidelines

- Best practices and recommendations related to a given concept, technology, or task
- Compliance with guidelines is not mandatory
	- Providing helpful advice

## Exceptions and Compensating Controls

- Unforeseen circumstances will arise that require a deviation from the requirements
- Exception processes require the use of **compensating controls**
	- To mitigate the risk associated with exceptions to security standards

## Monitoring and Revision

- Policy monitoring is an ongoing process
- Regularly evaluating the implementation and efficacy of infosec policies
- Tools
	- Security Information and Event Management (SIEM)
- Periodic audits and assessments
- Feedback from staff

- Inconsistencies or areas for improvement are identified
	- Policy revision becomes necessary

- Updating policies
	- Address any shortcoming
	- Adapting to new challenges or requirements
	- Important that revised policies are promptly communicated

# Change Management

- Helps reduce unanticipated outages caused by unauthorized changes
- Appropriate personnel review and approve changes before implementation
- Organizations constantly seek the best balance between security and usability
- Check work in controlled environments before implementing changes in production
- Some changes can weaken or reduce security

## Change Management Processes and Controls

- A change management process ensures that personnel can perform a security **impact analysis**
	- Experts evaluate changes to identify any security impact
- Provide a process to control, document, track and audit all system changes

### Standard Operating Procedures for Changes

1. **Request the change**
2. **Review the change**
3. **Approve/reject the change**
4. **Test the change**
5. **Schedule and implement the change**
	- Important to have *backout plan* 
6. **Document the change**

>[!TIP] Changes should be performed at a scheduled and coordinated time to avoid undesirable or unexpected impacts on operations. Many organizations use scheduled *maintenance windows* to coordinate changes to information systems. These windows are preplanned and announced times when all non-emergency changes will take place and often occur on evenings and weekends.

- Documenting emergency change 

## Technical Impact of Changes

- Important to involve a diverse set of technical stakeholders
- Organizations have a complex technical environment that no single person understands completely

- Some issue to consider
	- Whether the change will require any modifications to security controls, such as firewall rules, allow lists, or deny lists
	- Whether any other business or technical activities need to be restricted during or after the change
	- Whether the change will cause downtime for critical systems
	- Whether the change will require restarting any services or applications
	- Whether the change involves any legacy applications that lack vendor support
	- Whether all possibile dependencies have been identified and documented

## Version Control

- Ensures that developers and users have access to the latest versions of software
- Changes are carefully managed throughout the release process 

## Documentation

- Identifies the current configuration of systems
	- Who is responsible for the system
	- Its purpose
	- Lists all changes applied to the baseline
- Store this information
	- Configuration management system
- Keeping this documentation current is crucial step when completing a change
- Before closing out a change management taks
	- Be sure that any related documentation, diagrams, policies, and procedure are updated to reflect the impact of the change

# Personnel Management

- Employees require access to information and systems
	- Source of a cybersecurity incident

## Least Privilege

- Individuals should be granted only the minimum set of permissions necessary

- Privilege creep
	- When an employee moves from jib to job, accumulating new privileges, but never has the privileges associated with past duties revoked

## Separation of Duties

- For extremely sensitive job functions
- Takes two different tasks that, when combined, have great sensitivity
	- Create rule that no single person may have the privileges required to perform both tasks

- Common in the world of accounting
	- Ability to create a new vendor and issue a check is sensitive when used in combination

- *Two-person control* is similar to separation of duties but with an important difference
	- Requires the **participation of two people to perform a single sensitive action**

## Job Rotation and Mandatory Vacations

- Uncovering fraudulent action after they occur by exposing them to other employees

- **Job rotation**
	- Employees with sensitive roles and move them periodically to other position

- **Mandatory vacations**
	- Serve a similar purpose
	- Revoking their access privileges during that vacation period

## Clean Desk Space

- To protect the confidentiality of sensitive information
	- Limiting the amount of paper left exposed
- All papers and other materials be secured before an employee leaves their desk

## Onboarding and Offboarding

- Organizations should have standardized process for onboarding and offboarding
- Ensure retains control of its assets and handles the granting and revocation of credentials and privileges 

- New hire processes
	- Should include *background checks* designed to uncover any criminal activity or other past behavior

## Nondisclosure Agreements

- Nondisclosure agreements (NDA)
	- Require that employees protect any confidential information that they gain access
- Organizations normally ask new employees to sign and NDA upon hire and periodically remind
- Offboarding process often involve exit interviews that include a final reminder of the employee's responsibility 

## Social Media

- Organization may choose to adopt social media policies that constrain the behavior of employees on social medial
- Social media analysis may include assessments of both personal and professional acounts
	- That activity may reflect positively or negatively upon the organization
- Should make their expectations and practices clear in a social media policy

# Third-Party Risk Management

- Risks come from third-party organizations

## Vendor Selection

- Take special care to evaluate the vendor thoroughly during the selection process

- **Due diligence**
	- Thoroughly vetting potential vendors to ensure that they meet the organization's standards and requirements
		- Vendor's financial stability
		- Business reputation
		- Quality of products or services
		- Compliance with relevant regulations
		- Security practices
		- Data handling procedures

- **Conflicts of interest**
	- Competing interest that could influence behavior
	- Adding clauses in the contract that limit the vendor's engagement with competitors 

## Vendor Assessment

- Continuously assess the chosen vendors to ensure they maintain the expected quality, security and performance levels

- On method to evaluate a vendor's security is through
	- **Penetration testing**
- Vendor agreements should include
	- **Right-to-audit clause**
- Request evidence of internal audits conducted by the vendor
	- Insight into internal controls, compliance, and risk management practices

- Independent assessments
	- Third-party experts to objectively evaluate the vendor's practices and systems
		- Such as ISO 27001 or SOC reports

- **Supply chain analysis**
	- Risks associated with the vendor's supply chain
	- Assessing the vendor's suppliers 
		- Understanding the interdependencies and risks 
			- Could impact the vendor's ability to deliver products or services

- **Questionnaires**
	- Collect information regarding the vendor's practices and performance regularly 
	- Can be tailored to focus on specific areas of concern
		- Such as security policies, data handling procedures, and business continuity planning

## Vendor Agreements

- Commonly used agreements

- **Master service agreements (MSA)**
	- Provide an umbrella contract for the work that a vendor does with an organization over an extended period of type
	- Typically includes detailed security and privacy requirements
	- **Work Order (WO)** or **Statement Of Work (SOW)**
		- Contains project-specific details and references the MSA

- **Service Level Agreements (SLA)**
	- Contracts that specify the conditions of services
		- That will be provided by the vendor and remedies available to the customer if the vendor fails to meet the SLA
	- Commonly cover issues 
		- System availability
		- Data durability
		- Response time

- **Memorandum Of Understanding (MOU)**
	- Document aspects of the relationship
	- Informal mechanism that allows the parties to document their relationship to avoid future misunderstanding 
	- Commonly used in cases where an internal service provider is offering a service to a customer that is in a different business unit of the same company

- **Memorandum Of Agreement (MOA)**
	- Formal document that outlines the terms and details of an agreement between parties
		- Establishing a mutual understanding of the roles and responsibilities in fulfilling specific objectives
	- Generally more detailed than MOU 
		- May include clauses regarding resource allocation, risk management, and performance metrics

- **Business Partners Agreements (BPA)**
	- Exist when two organizations agree to do business with each other in a partnership
	- Might specify each partner's responsibilities and the division of profits 

>[!TIP] Be sure you know the differences between the various agreement types, including SLA, MOA, MOU, MSA, NSA, WO/SOW, and BPA

## Vendor Monitoring 

- Continuous observation and analysis of a vendor's performance and compliance

- Establishing **Rules Of Engagement**
	- How vendor should operate
	- Setting clear communication protocols
	- Defining responsibilities
	- Establishing processes for issue resolution

- **Performance monitoring**
	- **Key Performance Indicators (KPI)**
	- Regularly monitoring these metrics to ensure that vendors are meeting the agreed-upon standards

- Ensure the vendor maintains adequate security practices
	- Vendor's security posture
	- Checking for any data breaches or security incidents
	- Compliance with relevant security standards and regulations

- Compliance monitoring
	- Particularly for vendors handling sensitive data or operating in highly regulated industries
	- Compliance with legal and regulatory requirements
	- That they have the necessary certifications and accreditations

- Financial monitoring
	- Vendor's financial health to ensure they remain a viable partner

- In case where issues are identifies
	- Process for addressing these issues with the vendor
		- Formal meetings
		- Corrective action plans
		- In extreme cases, termination of the contract

## Winding Down Vendor Relationships

- Organization should take steps to ensure that they have an orderly transition when a vendor relationship ends or the vendor is discontinuing a product or service

- Product's End Of Life (EOL)
- End Of Service Life (SEOL)

>[!TIP] We discussed nondisclosure agreements (NDA) earlier in this chapter in the context of employee relationships, but employees are not the only individuals with access to sensitive information about your organization. Vendor agreements should also include NDA terms, and organizations should ensure that vendors ask their own employees to sign NDAs if they will have access to your sensitive information.

# Complying with Laws and Regulations

- Legislators and regulators around the world 

## Common Compliance Requirements

- **Health Insurance Portability and Accountability Act (HIPAA)**
	- Includes security and privacy rules 
	- Affect health-care providers, health insurers, and health information clearinghouses
- **Payment Card Industry Data Security Standard (PCI DSS)**
	- Rules about the storage, processing, and transmission of credit and debit card information
	- Not law but rather a contractual obligation that applies to credit card merchants and service providers
- **Gramm-Leach-Bliley Act (GLBA)**
	- Covers US financial institutions
	- Requires that those institutions have a formal security program
		- And designate an individual as having overall responsibility for that program 
- **Sarbanes-Oxley Act (SOX)**
	- Applies to the financial records of US publicly traded companies
	- Requires that those companies have a strong degree of assurance for the IT systems
		- That store and process those records
- **General Data Protection Regulation (GRPD)**
	- Implements security and privacy requirements for the personal information of EU residents worldwide
- **Family Educational Rights and Privacy Act (FERPA)**
	- Requires that US educational institutions implement security and privacy controls for student educational records
- Various **Data breach notification laws**
	- Requirements that individual state place on organizations that suffer data breaches
		- Regarding notification of individuals affected by the breach

## Compliance Reporting

- Internal and external **compliance reporting** 
	- Regulatory requirements and maintain transparency 

- Internal compliance reporting
	- Maintaining security posture
	- Adherence to various laws and regulations
	- Involves regular reports
	- Highlighting the state of compliance
	- Identifying gaps
	- Recommendations for improvement
- Helps to understand the compliance landscape

- External compliance reporting
	- Mandates by regulatory bodies or as a part of contractual obligations
	- Providing necessary documentation and evidence to external entities
		- To demonstrate compliance with relevant laws and regulations
- Handling credit card data 
	- Submit compliance reports to the PCI SSC
- Maintaining good standing with regulatory authorities
- Avoiding penalties
- Building trust with customers and parters 
	- By demonstrating a commitment to security and privacy

## Consequences of Noncompliance

- From financial penalties to reputational damage and loss of business 
- Most immediate impact is the imposition of fines and sanctions

- Nonfinancial sanctions
	- May include restrictions on business operations
- Regulatory authorities
	- Suspend or revoke licenses

- Reputational damage
	- Especially involving data breaches or privacy violations

- Loss of business and contractual impacts

- Lead to legal action
	- May sue for damages 

- Essential for organizations to invest in compliance management 
- Ensure that they are aware of and adhere to all relevant laws and regulations
- Regular audits, training, and effective communication channels 

## Compliance Monitoring

- **Due diligence**
	- Process of continuously researching and understanding the legal and regulatory requirements that pertain to the organization
	- Stay abreast of evolving laws and ensure that the organization has the necessary policies and controls in place
- **Due care**
	- Ensure that the implemented policies and controls are effective and continuously maintained
	- Regularly reviewing and updating policies
	- Proactive steps to ensure compliance
	- Attestation and acknowledgment
		- Attestation
			- They are aware of these requirements but have also confirmed that their practices adhere to these policies
		- Acknowledgment
			- Ensuring that employees and business parters state that they are aware of the compliance requirements 

- Internal and external monitoring mechanism
	- Internal monitoring
		- Internal audits, reviews, and checks to its policies and legal requirements
	- External monitoring
		- Third-party audits and assessments
			- Unbiased view

- Automation is an invaluable tool in compliance monitoring
	- Not only saves times and resources
	- Also reduces risk of human error
	- Helps generating detailed reports

>[!TIP] Be ready to summarize the elements of effective security compliance, including compliance reporting, the consequences of noncompliance, and compliance monitoring.

# Adopting Standard Frameworks

- Standardized approach to developing cybersecurity programs

## NIST Cybersecurity Framework

- National Institute of Standards and Technology (NIST)
	- Develop cybersecurity standards

- **Cybersecurity Framework (CSF)** assist organizations to meet 
	- Describe their current cybersecurity posture
	- Describe their target state for cybersecurity
	- Identify and prioritize opportunities for improvement within the context of a continuous and repeatable process
	- Assess progress toward the target state
	- Communicate among internal and external stakeholders about cybersecurity risk

- NIST Framework includes three components
	- **Framework Core**
		- Set of five security functions
			- Identify, protect, detect, respond, and recover
		- The framework then divides these functions into categories, subcategories, and informative references
	- **Framework Implementation Tiers**
		- Assess *how an organization is positioned* to meet cybersecurity objectives
		- **Maturity model**
			- Describes the current and desired positioning of an organization along a continuum of progress
	- **Framework Profile**
		- Describes how a specific organization might approach the security functions covered by the Framework core
		- Use a framework profile to *describe its current state* 
			- Then a separate *profile to describe its desired future state* 

- NIST Cybersecurity Framework
	- Developing and evaluating the state of cybersecurity programs

## NIST Risk Management Framework

- Risk Management Framework (RMF)
- Mandatory standard for federal agencies
- Provides a formalized process that federal agencies must follow
	- To select, implement, and assess risk-based security and privacy controls

### Note

- RMF is a formal process for implementing security controls and authorizing system use
- CSF provides a broad structure for cybersecurity controls
- CSF and RMF are mandatory for government agencies
- CSF commonly used in private industry

## ISO Standards

- International Organization for Standardization (ISO)
	- ISO 27001
	- ISO 27002
	- ISO 27701
	- ISO 31000

### ISO 27001

- Titled "Information security management systems"
- Covering 14 categories
	- Information security policies
	- Organization of information security
	- Human resource security
	- Asset management
	- Cryptography
	- Physical and environmental security
	- Operations security
	- Communications security
	- System acquisition, development, and maintenance
	- Supplier relationships
	- Information security incident management
	- Information security aspects of business continuity management
	- Compliance with internal requirements, such as policies, and with external requirements, such as laws

- Was once the most commonly used information security standard

### ISO 27002

- Goes beyond control objectives and *describes the actual controls that an organization may implement* to meet cybersecurity objectives
- ISO designed this supplementary document for organizations that wish to
	- Select information security controls
	- Implement information security controls
	- Develop information security management guidelines

### ISO 27701

- Contains standard guidance for managing **privacy controls**
- Extension to ISO 27001 and ISO 27002 standards

#### Note

ISO 27001 covers cybersecurity
ISO 27701 covers privacy

### ISO 31000

- Provide guidelines for risk management programs
- Covers **risk management in a general way** so that it may be applied to any risk

## Benchmarks and Secure Configuration Guides

- NIST and ISO frameworks are high-level descriptions of cybersecurity and risk management best practices
	- Don't offer practical guidance on actually implementing security controls

- Benchmarks and secure configuration guide
	- Help on how securely operate commonly used platforms
		- OS, web servers, application servers, and network infrastructure devices
	- Get down into the nitty-gritty details of securely operating 

- **Center for Internet Security (CIS)**
	- Publishes benchmarks for commonly used platforms

# Security Awareness and Training

- The success of a security program depends on the behavior of many different people
- Information security managers are responsible 
	- Establishing, promoting, and maintaining an infosec training and awareness program 

## User Training

- Receive regular **security training** 
	- Computer-Based Training (CBT)

### Role-Based Training

- Not every user requires the same level of training
- Receive the appropriate level of training based on job responsibilities

### User Guidance and Training

- Phishing attacks often target users at all levels
	- **Phishing simulations**
		- Who click on the simulated phishing message are sent to a training program

- **Anomalous behavior recognition**
	- Recognize when risky, unexpected, and/or unintentional behavior takes place
		- Insider threat

- Other topics in end-user security training programs
	- **Security Policies and Handbooks**
		- Provide users with information about where they can find critical security documents
	- **Situational Awareness**
		- Update users on the security threats facing the organization and how they can recognize suspicious activity
	- **Insider Threats**
		- Remind users that employees, contractors, and other insiders may pose a security risk and that they should be alert for anomalous behavior
	- **Password Management**
		- Educate users about your organization's password standards and the importance of not reusing passwords across multiple sites
	- **Removable Media and Cables**
		- Risks associated with the use of USB drives, external hard drives, and other removable media, as well as unfamiliar cables. 
		- Educate them on the policies for using these devices and the importance of scanning for malware before accessing files
	- **Social Engineering**
		- Train users to recognize and respond to social engineering attacks.
		- Teach them to be skeptical of unsolicited communications, especially those that create a sense of urgency or require sensitive information
	- **Operational Security**
		- Educate user on the importance of protecting sensitive information during day-to-day operations
		- Includes understanding the importance of access controls, not discussing sensitive information in public or unsecured areas, and being vigilant about who has access to sensitive data
	- **Hybrid/Remote Work Environments**
		- Instruct users on best practices for securing data and maintaining privacy when working remotely or in hybrid environments. 
		- Includes the use of VPNs, secure Wi-Fi networks, ensuring physical security of devices, and understanding the specific policies and procedures that are in place for remote work

>[!TIP] The exam objectives call out specific security awareness practices for phishing, anomalous behavior recognition, user guidance and training, reporting and monitoring, development, and execution. Given a scenario, be ready to implement security awareness best practices.

### Training Frequency

- Balance the time required to conduct training with the benefit 
- One approach
	- Initial training whenever an employee joins the organization or assumes new job responsibilities
	- Then use annual refresher trainings to cover the same material and update users on new threats and controls

### Development and Execution

- Begins with a thorough assessment of the organization's security landscape
	- Identifying potential risks and threats
- Then the team can develop tailored content that address the unique challenges of the organization

- Helpful to incorporate real-world examples and interactive elements 

- The execution phase should include a variety of training methods
	- Workshops, e-learning modules, and simulations
- Make training accessible and regular for all employees
- Schedule that includes initial training for new employees
- Periodic refreshers to keep knowledge current

### Reporting and Monitoring

- Track participation in training programs 
- Assess user knowledge through quizzes and other means
- Collect feedback from employees

- Provide decision-makers with regular reports
	- Provide both detailed data for technical stakeholders and high-level trends for management
- Analysis of trends in knowledge levels and security incidents 
	- Essential for understanding the long-term impact of the training program

- Review material on a regular basis to ensure that the content remains relevant
	- Changes in the security landscape and the organization's business may require updating the material

## Ongoing Awareness Efforts

- **Security awareness** efforts
	- Less formal efforts that are designed to remind about the security lessons already learned
	- Use posters, videos, email messages, and similar techniques to **keep security top-of-mind**

# Exam Essentials

- **Security governance practices ensure that organizations achieve their strategic objectives.**
	- Governance programs
		- Sets of procedures and controls put in place to allow an organization to effectively direct its work
		- May involve the participation of a variety of boards, committees, and government regulators
	- Centralized governance models
		- Top-down approach 
		- Dictates how subordinate units meet security objectives
	- Decentralized governance models
		- Delegate the authority for meeting security objectives as the subordinate units see fit

- **Policy frameworks consist of policies, standards, procedures, and guidelines.**
	- Policies are high-level statements of management intent for the information security program
	- Standards describe the detailed implementation requirement for policy
	- Procedures offer step-by-step instructions for carrying out security activities
	- Compliance with policies, standards. and procedures is mandatory
	- Guidelines offer optional advice that complements other elements of the policy framework

- **Organizations often adopt a set of security policies covering different areas of their security programs.**
	- Common policies used in security programs include 
		- Information security policy
		- Acceptable use policy
		- Data ownership policy
		- Data retention policy
		- Account management policy
		- Password policy
	- The specific policies adopted will depend on that organization's culture and business needs

- **Policy documents should include exception processes.**
	- Exception processes should outline 
		- The information required to receive an exception to security policy
		- Approval authority for each exception
	- The process should also describe the requirements for compensating controls that mitigate risks associated with approved security policy exceptions

- **Change management is crucial to ensuring the availability of systems and applications.**
	- The primary goal of change management is to ensure that changes do not cause outages
	- Change management processes 
		- Ensure that appropriate personnel review and approve changes before implementation  
		- Ensure that personnel test and document the changes
	- Change review processes should carefully evaluate the potential impact of any change

- **Organizations face a variety of security compliance requirements.**
	- Merchants and credit card service providers 
		- Must comply with the Payment Card Industry Data Security Standard (PCI DSS)
	- Organizations handling the personal information of EU residents m
		- Must comply with the EU General Data Protection Regulation (GDPR)
	- All organizations should be familiar with the national, territory, and state laws that affect their operations

- **Standards frameworks provide an outline for structuring and evaluating cybersecurity programs.**
	- Organizations may choose their security programs on a framework standard
		- Such as the NIST Cybersecurity Framework (CSF) 
		- Or International Organization for Standardization (ISO)
	- US federal government agencies and contractors 
		- Should also be familiar with the NIST Risk Management Framework (RMF)
	- These framework sometimes include maturity models that allow an organization to asses its progress
	- Some frameworks also offer certification programs 
		- That provide independent assessment of an organization's progress toward adopting a framework

- **Security training and awareness ensures that individuals understand their responsibilities.**
	- Security training programs impart new knowledge on employees and other stakeholders
	- They should be tailored to meet the specific requirements of and individual's role in the organization
	- Security awareness programs seek to reming users of the information they have already learned, keeping their security responsibilities top-of-mind

#cybersecurity 