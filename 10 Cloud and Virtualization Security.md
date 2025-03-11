# Chapter 10 - Cloud and Virtualization Security

---

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.3. Explain various types of vulnerabilities.**

- Virtualization (Virtual machine (VM) escape, Resource reuse)
- Cloud-specific

## Domain 3.0 Security Architecture

**3.1. Compare and contrast security implications of different architecture models.**

- Architecture and infrastructure concepts (Cloud, (Responsibility matrix, Hybrid considerations, Third- party vendors), Infrastructure as code (IaC), Serverless, Microservices, On-premises, Centralized vs. decentralized, Containerization, Virtualization)

**3.3. Compare and contrast concepts and strategies to protect data.**

- General data considerations (Data sovereignty)

## Domain 4.0 Security Operations

**4.1. Given a scenario, apply common security techniques to computing resources.**

- Hardening targets (Cloud infrastructure)

---

# Exploring the Cloud

- Computing services over the Internet
- Oversubscription
	- Shared pool of resources used by different users
- Multitenancy
	- Different users share resources

## Benefits of the Cloud

- On-demand self-service computing
- Scalability
	- Vertical scaling
		- Increase the capacity of existing servers
	- Horizontal scaling
		- Adds more servers to a pool of clustered servers
- Elasticity
	- Expand and contract as needs change to optimize costs
- Measured service
	- You pay for exactly what you use
- Agility and flexibility
	- Speed to provision and the ability to use for short periods

## Cloud Roles

- Cloud service providers (CSP)
- Cloud consumers
- Cloud partners (or cloud broker)
	- Products or services that support or integrate with the offerings of a cloud service provider
- Cloud auditors
	- Third-party assessments
- Cloud carriers
	- Intermediaries that provide the connectivity
- Same organization may take on multiple roles

## Cloud Service Models

- Anything as a Service
	- XaaS

### Infrastructure as a Service

- **IaaS**
	- Interact with basic building blocks
		- Computing, storage, and networks
	- Customize components to meet their needs
	- Provider implement security controls

### Software as a Service

- **SaaS**
	- Fully managed application 
	- Web-based email to Enterprise Resource Planning (ERP) and Customer Relationship Management (CRM)
	- Access through browser 
	- Client device, such Google Chromebook

### Platform as a Service

- **PaaS**
	- Middle ground between SaaS and IaaS
	- Application developed by customers

- Function as a Service
	- FaaS
	- Example of PaaS computing
	- Customers upload their own code functions
	- Run in scheduled basis
	- *Serverless* computing
		- Costumers don't exposed to server instances

## Managed Services

- Managed service provider (MSP)
	- Working across a customer's total environment
		- Cloud and on-premises deployments 
- Managed secure service provider (MSSP)
	- Security monitoring
	- Vulnerability management
	- Incident response
	- Firewall management

## Cloud Deployment Models

### Public Cloud

- Multitenant model
- Workloads for different customers simultaneously
- All cloud service models
	- IaaS, PaaS, SaaS, and FaaS
- Not dedicated to a sigle but available to general

### Private Cloud

- One customer uses the environment
- Not cost-efficient as public cloud

### Community Cloud

- Share characteristics of public and private models
- Multitenant
- Limited to members of community

### Hybrid Cloud

- Public, private, and/or community cloud services
- Cloud bursting
	- Operate private cloud and leverage public cloud when demand exceeds
- Decentralized approach
	- Reduces single point of failure
	- Spreading technology components across multiple providers

## Shared Responsibility Model

- Responsibility matrix
- Cloud providers
	- Responsible for security **hardware and physical datacenter environment**
- IaaS
	- Customer 
		- Data, Application, OS
- PaaS
	- Customer
		- Data
	- Shared
		- Application
- SaaS
	- Shared
		- Data

| Responsibility       | IaaS     | PaaS     | SaaS   |
| -------------------- | -------- | -------- | ------ |
| **Data**             | Customer | Customer | Shared |
| **Application**      | Customer | Shared   | Vendor |
| **Operating System** | Customer | Vendor   | Vendor |
| **Hardware**         | Vendor   | Vendor   | Vendor |
| **Datacenter**       | Vendor   | Vendor   | Vendor |

- Pay attention with requiring compliance with external regulation
	- Payment Card Industry Data Security Standard (PCI DSS)

## Cloud Standards and Guidelines

- Cloud Reference Architecture
	- NIST (National Institute for Standards and Technology)
		- SP 500-292
			- High-level taxonomy for cloud services
- Cloud Security Alliance (CSA)
	- Developing and promoting best practices in cloud security
	- Cloud Control Matrix (CCM)
		- Reference document designed to help organizations **understand the appropriate use of cloud security controls and map those controls** to various regulatory standards

## Edge Computing

- IoT
- Edge computing
	- Allow preprocess data before shipping to cloud
- Fog computing
	- Sensors send data to their local gateway
	- Then sends to cloud

# Virtualization

- Allow multiple guest systems to share the same underlying hardware

## Hypervisors

- Enforcing isolation between VM
	- Illusion of completely separate physical environment
- Type I 
	- Bare-metal hypervisors
- Type II 
	- On top of an existing OS 

# Cloud Infrastructure Components

- IaaS

## Cloud Compute Resources

- Dynamic resource allocation
- Add or remove resources as needs change

### Virtualization

- VM are the basic building block
- Provision servers running most common OS
- Connection SSH, RDP

### Containerization

- Application-level virtualization
- Portable across OS and hardware platforms
- Containerization platform
	- Docker
- Secure containers
	- Container-specific host OS, reduced features to reduce attack surface
	- Segmenting containers by risk profile and purpose
	- Container-specific vulnerability management security tools

>[!TIP] Containers provide application-level virtualization but must be protected like VMs. Enforced isolation between containers to prevent operational and security issues is recommended.

## Cloud Storage Resources

- Block storage
	- Large volumes of storages for use by virtual server instances
	- Formatted as virtual disks by OS
	- Preallocated
- Object storage
	- Place files in buckets and treat file as an independent entity
	- Accessed over the web or API
	- Hides the storage details from end user
	- Not preallocated

- Security considerations
	- **Set permissions properly**
	- **Consider High-Availability and durability options**
	- **Use encryption to protect sensitive data**

## Cloud Networking

- Software-defined networking (SDN)
	- Interact and modify cloud resources through their API
- Software-defined Visibility (SDV)
	- Insight into the traffic on their virtual network

### Security Groups

- Define permissible network traffic
	- Same as a firewall ruleset
	- Network level
- Because cannot provide customer with direct access to firewall

### Virtual Private Cloud (VPC)

- Segmentation
- Group systems into subnet
	- Public or private
- VPC endpoints
	- Allow the connection of VPCs to each other
- Cloud Transit Gateway
	- Allowing direct interconnection of cloud VPC with on-premises VLANs for hybrid cloud operations

### DevOps and Cloud Automation

- DevOps
	- Development and operations teams in a unified process
	- Software testing and release process becomes highly automated

- Infrastructure as a Code (IaC)
	- Automating provisioning, management. and deprovisioning of infrastructure services
	- One of key features of IaaS
	- Depends on the API offered by cloud providers 
	- API integration helpful with microservices
		- Function-as-a-service

# Cloud Security Issues

## Availability

- Backup data across different geographic regions
- High availability mode

>[!TIP] High availability is not always guaranteed with base-level cloud services. You often need to purchase and/or configure HA services in order to maximise your uptime.

## Data Sovereignty

- Data is subject to the legal restrictions of **any jurisdiction** where it is collected, stored, or processed

## Virtualization Security

- **VM escape vulnerabilities**
	- Attacker as access to a single virtual host and then manages to leverage that access to intrude upon the resources assigned to a different VM
	- Hypervisor is supposed to prevent this type of access
		- By restricting a VM's access to only those resources assigned to that machine

- Virtual machine sprawl
	- IaaS users create virtual service instances and then forget or abandon them
	- Accrue cost and accumulate security issue

- Resource reuse
	- Cloud provider assign resource to new customer but **data not removed**
	- New customer may inadvertently gain access to data of old customer

>[!TIP] VM escape and resource reuse. Be sure you are familiar with and can explain these virtualization vulnerabilities.

## Application Security

- Cloud applications depend on the use of APIs
	- API inspection 
		- Scrutinizes API request 

- Secure web gateways (SWGs)
	- Provide a layer of application security
	- Monitor web request made by internal users
	- Block access to potentially malicious content
	- Enforce content filtering

## Governance and Auditing of Third-Party Vendors

- Cloud Governance Efforts
	- Evaluate vendors for potential cloud partnerships
	- Monitor vendor performance and detect early signs of instability
	- Supervise the organization’s cloud activities

- Auditability
	- Contracts should include
		- Right to Audit Customers must be able to audit providers directly or via third parties
	- Purpose of Auditing
		- Ensure secure operations by the provider
		- Verify compliance with contractual data protection obligations

# Hardening Cloud Infrastructure

- Cloud-native controls
	- Cost-effective and user-friendly
- Third-party solutions
	- Costly
	- Integrating with a variety of cloud providers

## Cloud Access Security Brokers

- Cloud access security brokers (CASB)
	- Tools serve as intermediaries between users and provider
	- Inline CASB
		- Physically or logically reside in the connection path
		- Allowing to block requests that violates policy
	- API-based CASB
		- Not interact directly with user but rather interact directly with the cloud provider
		- Through provider's API
		- Limited to monitoring user activity and reporting on
		- Correcting policy violations after the facts

## Resource Policies

- Cloud providers limit the actions that users may take
- Limit damage caused by
	- Accidental command
	- Compromised account
	- Malicious insider

## Secrets Management

- Hardware security modules (HSM)
	- Manage encryption key 
	- Perform cryptographic operations 
	- Expensive
	- Create and manage encryption key without exposing to human
	- Cloud service provider use HSM internally
		- Also provide HSM services to their customers

# Exam Essential

- **Explain the three major cloud service models.**
	- Infrastructure as a service (IaaS)
		- Purchase and interact with the basic building blocks of a technology infrastructure
	- Software as a Service (SaaS)
		- Access to a fully managed application 
	- Platform as a Service (PaaS)
		- Run applications developed themselves

- **Describe the four major cloud deployment models.**
	- Public cloud
		- Accessible to any customers
		- Multitenant
	- Private cloud
		- Provisioned for use by a single customer
	- Community cloud
		- Share characteristic public and private models
		- Multitenant but the tenants are limited to members
	- Hybrid cloud
		- Public, private, and/or community cloud services together 

- **Understand the shared responsibility model of cloud security.**
	- IaaS environment
		- Cloud provider takes on the most responsibility
		- Security for everything below OS layer
	- PaaS
		- Provider added responsibility of OS itself
	- SaaS
		- Provider is responsible for entire environment
		- Except for configuration of access controls and the choice of data to store

- **Implement appropriate security controls in a cloud environment.**
	- Controls offered
		- By providers
		- Third-parties
	- Maintaining resources policies
	- Design resilient cloud implementations 
	- HA across multiple zones
	- Storage
		- Permissions
		- Encryption
		- Replication
		- HA
	- Network
		- Design of virtual network
		- Public and private subnets to segmentation
	- Compute
		- Design security groups
			- Restrict network traffic to instances

#cybersecurity 