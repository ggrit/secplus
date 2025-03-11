# Chapter 8 - Identity and Access Management

---
## Domain 1.0: General Security Concepts

**1.2. Summarize fundamental security concepts.**

- Authentication, Authorization, and Accounting (AAA) (Authenticating people, Authenticating systems, Authorization models)

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.5. Explain the purpose of mitigation techniques used to secure the enterprise.** 

- Access control (Access control list (ACL), Permissions)

## Domain 4.0 Security Operations

**4.6. Given a scenario, implement and maintain identity and access management.**

- Provisioning/de-provisioning user accounts
- Permission assignments and implications
- Identity proofing
- Federation
- Single sign-on (SSO) (Lightweight Directory Access Protocol (LDAP)), Open authorization (OAuth), Security Assertions Markup Language (SAML)
- Interoperability
- Attestation
- Access controls (Mandatory, Discretionary, Role-based,Rule-based, Attribute-based, Time-of-day restrictions, Least privilege)
- Multifactor authentication (Implementations (Biometrics, Hard/soft authentication tokens, Security keys), Factors (Something you know, Something you have, Something you are, Somewhere you are))
- Password concepts (Password best practices (length, complexity, reuse, expiration, age), Password managers, Passwordless)
- Privileged access management tools (Just-in-time permissions, password vaulting, ephemeral credentials)

---

# Identity

- Set of claims made about a subject
- Common ways to assert or claim an identity
	- Usernames
	- Certificates
	- Tokens
	- SSH keys
	- Smartcard

## Lost Key Pairs

- Ensuring proper handling and management practices 

# Authentication and Authorization

- Authentication
	- Ensure that the subject is who they claim that they are
- Authorization
	- Verifies what you have access to

## Authentication and Authorization Technologies

>[!TIP] Focuses on SSO-related technologies -LDAP, OAuth, and SAML- as well as 802.1x and EAP, which will be covered in Chapter 12.

- Extensible Authentication Protocol (EAP)
	- Wireless network 
	- EAP-TLS, LEAP, and EAP-TTLS
- Challenge Handshake Authentication Protocol (CHAP)
	- Encrypted challenge and three-way handshake
- **802.1X**
	- IEEE standard for Network Access Control (NAC)
	- Authentication for devices on a network
- Remote Authentication Dial-In User Service (RADIUS)
	- Authentication, Authorization, and Accounting (AAA)
	- For network devices, wireless networks, and other services
	- TCP or UDP
	- Password obfuscated by shared secret and MD5 hash
- Terminal Access Controller Access Control System Plus (TACACS+)
	- Cisco-designed extension to TACACS
	- TCP to provide Authentication, Authorization, and Accounting services
	- Full-packet encryption as well as granular command controls
- Kerberos
	- Authenticating between trusted hosts across an untrusted network (like Internet)
	- Username, instance, and realms
	- Kerberos key distribution centers (KDCs)

## Single Sign-On

- Allow a user to log in with a single identity and then use multiple systems or services
- Lightweight Directory Access Protocol (LDAP)
	- Directory services
	- Commonly deployed as part of an identity management infrastructure and offer hierarchically organized information
- Technologies to accomplish authentication and authorization
	- Security Assertion Markup Language (SAML)
		- XML-based open standard for exchanging authentication and authorization information
	- OpenID
		- Decentralized authentication
		- Google, Amazon, Microsoft are OpenID identity providers (IdPs)
	- OAuth
		- Open standard for authorization used by many website

### Federation

- Identity information is handled by an Identity provider (IdP)
	- Manage life cycle of digital identities
	- Often part of federated identity deployments, where they are paired with relying parties
- Commonly used for many web services
- Terms
	- The principal, typically a user
	- Identity providers (IdPs)
		- Via an **Attestation (formal verification)**
	- Service providers (SPs)
	- Relying party (RP)
- Interoperability is a key concern when connecting different organizations together

# Authentication Methods

## Passwords

- NIST recommendations
	- Show password to prevent typos
	- Password managerd
	- Salting and hashing
	- Locks after multiple attempts
	- Multifactor authentication
	- Reducing password complexity and instead emphasizing length
	- Not requiring special characters
	- Allowing ASCII and Unicode
	- Allowing pasting into password fields to allow password managers to work
	- Monitoring new passwords to ensure that easily compromised password are not used
	- Eliminating password hints
- Common password settings
	- Length
	- Complexity
	- Reuse limitation
	- Expiration dates
	- Age settings 

## Password Managers 

- Create, store and manage password

## Passwordless

- Something you have
	- Security tokens, OTP application, certificates
- Something you are
	- Biometric factors
- Hardware device
	- Security key
		- Support OTP, Public key, FIDO, U2F

## Multifactor Authentication

- MFA
- Something **you know**
	- Passwords, PINs, answer to a security question
- Something **you have**
	- Smartcard, USB or Bluetooth token, or another object
- Something **you are**
	- Fingerprints, retina scans, voice prints, typing speed and patters
- **Somewhere you are**
	- GPS, network location, and other data

## One-Time Passwords

- Second factor
- Combat password theft and other password-based attacks
- **Time-based One-time password (TOTP)**
- **HMAC-based One-time password (HOTP)**
	- HMAC Hash-based message authentication codes
- Based on SMS 
- Phone call
- Static code
	- Pre-generated and often printed or stored

## Biometrics

- **Something you are**
- Fingerprints
- Retina scanner
- Iris recognition
- Facial recognition
- Voice recognition
- Vein recognition
- Gait analysis (how a person walk)

- Four major measures
	- Type I, or False Rejection Rate (FRR)
		- Legitimate biometric rejected
	- Type II, or False Acceptance Error
		- Measured as False Acceptance Rate (FAR)
			- False biometric accepted
	- Receiver Operating Characteristic (ROC)
		- Compares FRR and FAR
		- Important for accuracy and efficacy

# Accounts

## Account Types

- User Account
- Privileged or administrative accounts
- Shared and generic accounts or credentials
- Guest accounts
- Service accounts

## Provisioning and Deprovisioning Accounts

- Provisioned, or created
	- Involve Identity proofing (verify)
- Deprovisioned, or terminated
	- Disable or delete
- Add to groups to accomplish their role
- Least privilege
- Permission creep
	- Overly broad permissions

## Privileged Access Management

- PAM
- Tools to handle administrative and privileged account
- Ensuring concept of least privilege
- **Just-in-time (JIT)**
	- Granted and revoked only when needed
	- Prevent having ongoing access
- **Password vaulting**
	- Allow to access privileged accounts without know a password
	- Ensure password available for emergencies and outages
- **Ephemeral accounts**
	- Temporary account

# Access Control Schemes

- **Mandatory Access Control (MAC)**
	- Systems rely on OS to enforce control
	- Security policies set centrally
	- Government and military systems
- **Discretionary Access Control (DAC)**
	- Home PC
	- Owners of file or directory can set permission to that
- **Role-based Access Control (RBAC)**
	- Rely on roles
	- Popular for enterprise
	- Three primary rules
		- Role assignment
		- Role authorization
		- Permission authorization
	- Support multiple role for subject 
- **Rule-based Access Control (RBAC or RuBAC)**
	- Set of rules, or ACL
	- Common use is a firewall ruleset
- **Attribute-based Access Control (ABAC)**
	- Policies that are driven by attributes of the users
	- Allow complex rulesets based on combination of attributes
	- Flexible
	- Complex to manage
	- Useful for application security, databases, content management systems, microservices, and API
- **Time-of-day restrictions**
	- Limit when activities can occur
		- Work hours
- **Least privilege**
	- Minimum set of permissions and capabilities

## Filesystem Permissions

- Determine which accounts, users, groups, or services can read, write, and execute files

# Exam Essentials

- **Identities are the foundation of authentication and authorization.**
	- User claim an identity through an authentication process
	- In addition to usernames, identities are ofter claimed through
		- Certificates, tokens, SSH keys, or smartcard
	- Identities use attribute to describe the user
		- Like job, title, personal traits

- **Single sign-on and federation are core elements of many identity infrastructures.**
	- SSO allow user to log in one and use resources and services across an organization or federation
	- Technologies and implementations
		- LDAP, OAuth, and SAML

- **Passwords, passworldless authentication, and multifactor authentication all have roles to play in authentication systems.**
	- Password best practices
		- Length, complexity, reuse, expiration, and age
	- Password manager
		- Help limit password reuse and manage
	- Multifactor authentication
		- Additional factors beyond passwords
			- Biometrics
			- Hardware (and software) based tokens like security keys and authenticator applications
		- Require distinct factors
			- Something you know
			- Something you have
			- Something you are
			- Somewhere you are

- **Account types and account policies determine what users can do and privileged accounts must be managed and controlled.**
	- Users, guests, administrative (privileged), and service accounts
	- Provisioning and deprovisioning
		- Account life cycle ensuring appropriate rights and that they do not remain after they are no longer needed
	- Privileged Access Management (PAM)
		- Focus on privileged accounts and rights
		- Just-in-time
		- Ephemeral accounts

- **Access control schemes determine what rights accounts have.**
	- Attribute-based Access Control (ABAC)
	- Role-based Access Control (RBAC)
	- Rule-based Access Control (RBAC, RuBAC)
	- Mandatory Access Control (MAC)
	- Discretionary Access Control (DAC) 
	- Privilege Access Management (PAM)

#cybersecurity 