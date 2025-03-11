# Chapter 6 - Application Security

---
## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.3. Explain various types of vulnerabilities.**

- Application (Memory injection, Buffer overflow, Race conditions (Time-of-check (TOC), Target of evaluation (TOE), Time-of-use (TOU)), Malicious update)
- Web-based (Structured Query Language injection (SQLi), Cross-site scripting (XSS))

**2.4. Given a scenario, analyze indicators of malicious activity.**

- Application attacks (Injection, Buffer overflow, Replay, Privilege escalation, Forgery, Directory traversal)

## Domain 4.0: Security Operations

**4.1. Given a scenario, apply common security techniques to computing resources.**

- Application security (Input validation, Secure cookies, Static code analysis, Code signing)
- Sandboxing

**4.3. Explain various activities associated with vulnerability management.**

- Identification methods (Application security, Static analysis, Dynamic analysis, Package monitoring)

**4.7. Explain the importance of automation and orchestration related to secure operations.**

- Use cases of automation and scripting (User provisioning, Resource provisioning, Guard rails, Security groups, Ticket creation, Escalation, Enabling/disabling services and access, Continuous integration and testing, Integrations and Application programming interfaces (APIs))
- Benefits (Efficiency/time saving, Enforcing baselines, Standard infrastructure configurations, Scaling in a secure manner, Employee retention, Reaction time, Workforce multiplier)
- Other considerations (Complexity, Cost, Single point of failure, Technical debt, Ongoing supportability)

## Domain 5.0: Security Program Management and Oversight

**5.1. Summarize elements of effective security governance.**

- Policies (Software development lifecycle (SDLC))

---

# Software Assurance Best Practices

## The Software Development Life Cycle

- **SDLC**
	- Planning
	- Requirements definition
	- Design
	- Coding
	- Testing
		- User acceptance testing (UAT)
	- Training and transition
	- Operations and maintenance - Ongoing
	- Decommissioning - End of life

## Code Deployment Environments

- **Development** environment
- **Test** environment
	- Quality Assurance (QA)
- **Staging** environment
	- Waiting to be deployed
- **Production** environment
	- Live system

>[!TIP] Software Development Life Cycle (SDLC) describe the steps for software development. It maps software creation from an idea to requirements gathering and analysis to design, coding, testing, and rollout. Secure SDCL practices aim to integrate security into the development process.

## DevSecOps and DevOps

- **DevOps**
	- Software development and IT Operations with the goal of optimizing SDLC
	- Done by collections of tool called toolchain
- **DevSecOps**
	- Integrating Security

### Continuous Integration and Continuous Deployment

- **Continuous Integration (CI)**
	- Checks code into a shared repository
	- Automation and scripting
	- Continuous delivery of code
- **Continuous Deployment (CD)**
	- Rolls out tested changes into production automatically

- CI/CD pipeline
	- Developer commits change
	- Build process is triggered
	- Build report delivered
	- Tests run against build
	- Tests report delivered
	- If successful, code is deployed

 - CI/CD requires Continuous Validation and automated security testing
 - Logging, reporting and Continuous Monitoring must fit CI/CD process

# Designing and Coding for Security

- Security professional helps software security
	- Requirements gathering
	- Design phases
- During development process
	- Secure coding techniques
	- Code review
	- Testing
- During testing phase
	- Tools
		- Web application security scanner
	- Penetration testing
- Also ongoing security operations
	- Future security scans
	- Regression testing during patching and updates

## Secure Coding Practices

- Open Worldwide Application Security Project (OWASP)
	- Community-developed standards, guide, and best practice.
	- Open Source tools
	- How web application security threats change
- OWASP's top proactive controls
	- Define Security Requirements
	- Leverage Security Frameworks and Libraries
	- Secure Database Access
	- Encode and Escape Data
	- Validate All Inputs
	- Implement Digital Identity
	- Enforce Access Controls
	- Protect Data Everywhere
	- Implement Security Logging and Monitoring
	- Handle All Errors and Exceptions

## API Security

- **Application Programming Interface**
	- Interface between
		- Client - Server
		- Application - Operating System
- Define **how client ask information from the server** and **how server will respond**

- API Security relies
	- Authentication
	- Authorization
	- Data scoping
	- Rate limiting
	- Input filtering
	- Monitoring
	- Logging

# Software Security Testing

- Manual and automatic testing tools and methods

## Analyzing and Testing Code

- Static or dynamic code analysis
- Fuzzing

### Static Code Analysis

- Source Code Analysis
	- **Reviewing** the code
- Known-environment test
	- Full visibility to the testers
- Automated tools or manually
- Understanding how the program is written
- What the code is intended to do
- **No execution of the code**

### Dynamic Code Analysis

- **Execution of the code**
- Input to test the software
- Automated tools or manually

>[!TIP] Static testing analyzes code without executing it. Points directly at vulnerabilities and provides specific remediation suggestion. <br> Dynamic testing execute code, running all interfaces exposed to the user with a variety of inputs.

### Fuzzing

- Sending invalid or random data to test ability to handle unexpected data
- Monitored to determine
	- Crashes
	- Fails
	- Responds in an incorrect manner
- Detect input validation and logic issues

# Injection Vulnerabilities

- Type code as input and trick the web server
	- Executing that code
	- Supplying it to another server to execute

## SQL Injection Attacks

- Sends a threat query to the web server
- Visible or Blind output
- Blind SQL Injection
	- Content-based
	- Timing-based

### Blind Content-Based SQL Injection

- Sends input to test whether the application interprets injected code
- observes behavior based on differences in the server response
	- Visible or not visible
- If the **behavior changes between true and false conditions**, maybe vulnerable

### Blind Time-Based SQL Injection

- Use amount of time required to process a query as a channel for retrieving information from a database
- Depend on delay mechanism
- If the application **return the result after a specified delay**, it is likely vulnerable

>[!TIP] In a SQL Injection attack, malicious code is inserted into strings of code that are later passed to a SQL database server.

## Code Injection Attacks

- Insert attacker-written code into legitimate code
	- LDAP injection attack
	- XML injection attack
	- DDL injection attack
	- Cross-Site Scripting (XSS)
		- Inject HTML code

## Command Injection Attacks

- Application code may **reach back to the OS** the execute a command

# Exploiting Authentication Vulnerabilities

- Gain illegitimate access

## Password Authentication

- Knowledge-based auth
- Social engineering attacks
- Eavesdropping on unencrypted network traffic
- Password dump and reuse (users reuse their password)
- Brute-force
- Default administrator accounts

## Sessions Attacks

- Sessions Hijacking
	- Steal an existing authenticated session
- Don't required gain access to the authentication mechanism
- User sessions cookies as a part of the HTTP header
	- Cookies stored in the browser
	- Cookies contain authentication string for later access

### Cookie Stealing and Manipulation

- Cookie are digital version of badge
- Attacker obtain cookie
	- Eavesdropping on unencrypted network and stealing a copy
	- Malware on user's browser
	- On-path attack
		- Fake authentication form
- Session replay attack
- Web devs protect by marking cookies with *secure* attribute
	- *Secure* cookies rely only on HTTPS
- NTML pass-the-hash
	- Gain access to Windows system
	- Harvest stored NTML password hashes
	- Use these hashes to gain access
		- To that system or other in same AD domain

### Unvalidated Redirects

- Unvalidated redirect
	- Redirect the user to a malicious site
		- Credential theft or session stealing
- Application should perform **Validated redirects**
	- Against on approved list

# Exploiting Authorization Vulnerabilities

- Allow to exceed the level of access

## Insecure Direct Object References (IDOR)

- Change a parameter in the URL the access unauthorized data or documents
- To ensure, application should perform authorization checks

## Directory Traversal

- Navigate the directory structure
- Work when
	- Servers allow the inclusion of operator that navigate directory paths  
	- Filesystems access controls don't properly restrict access
- In Linux, the "`..`" operator refers to the directory one level higher

## File Inclusion

- Execute the code contained within a file
	- Web server executing arbitrary code
- **Local File Inclusion**
	- Execute code stored on the web server
	- Similar to Directory Traversal 
- **Remote File Inclusion** 
	- Execute code store on a remote server
	- Attacker can directly control code being executed
- Exploit it to upload a webshell
- Access to the server over HTTP and HTTPS ports

## Privilege Escalation

- Increase level of access
	- Via exploit vulnerabilities

>[!TIP] Privilege escalation focus on exploiting flaws to gain elevated permissions or access. Allow a normal or an untrusted user to use administrator or other privileged access.

# Exploiting Web Application Vulnerabilities

- Complex ecosystem of application code, web platforms, OS, databases, and interconnected APIs

## Cross-Site Scripting (XSS)

- HTML injection into a web page

### Reflected XSS

- Reflected input
- Embed scripts in web pages by using HTML tags `<SCRIPT>` and `</SCRIPT>`
- The key of this attack is that is possible to **embed form input in a link**
- **Input validation**
	- Never allow the `<SCRIPT>` tag
	- Determine the type of input that the application will allow

>[!TIP] In a Cross-Site Scripting (XSS) attack, an attacker embeds scripting commands on a website that will later be executed by an unsuspecting visitor accessing the site. The idea is to trick a user visiting trusted site into executing malicious code placed there by an untrusted third party.

### Stored/Persistent XSS

- Store hidden Cross-Site Scripting code on a remote web server
- Persistent because they remain on the server
- Used to
	- Redirect to phishing site
	- Request sensitive information
	- Perform another attack

## Request Forgery

- Exploit trust relationships and attempt to have users unwittingly execute commands against a remote server

### Cross-Site Request Forgery (CSRF/XSRF)

- XSS exploit the trust that a user has in a website to execute code on the user's computer
- XSRF exploit the **trust that remote sites have in a user's** system 
	- To execute commands on the user's behalf
- XSRF attack work in assumption the **users are logged into many different website at the same time**
- Attacker then embed code in one website that sends a command to a second website
	- If the user is logged into that second website the command may succeed
- Protect
	- Secure tokens
	- Check referring URL

### Server-Side Request Forgery (SSRF)

- **Trick a server into visiting a URL based on user-supplied input**
- Possible when a web application accepts URLs from a user as a input
- Then retrieves information from that URL
- If server has access to nonpublic URLs
	- SSRF attack can unintentionally disclose that information to an attacker

# Application Security Controls

## Input Validation

- Application that allow user input should perform validation of that input
- **Allow listing**
	- Describes the exact type of input that is expected
- **Deny listing**
	- Describes potentially malicious input
- Ensure that validation occurs **server-side**
	- Easy bypass browser-based input validation

>[!TIP] Input validation helps prevent a wide range od problems, from Cross-Site Scripting (XSS) to SQL injection attacks.

## Parameter Pollution

- Used to defeat input validation controls
- Sending a web application more than one value of the same input variable
	- Web platform might perform input validation on only the first argument

## Web Application Firewalls (WAFs)

- Works at the **Application Layer**
- Sit in front of a web server
- Scrutinizes the input headed to the application
	- Performing **input validation before passing the input to the web server**

## Parameterized Queries

- Protect application against injection attacks
- The client doesn't directly send SQL code to the database server
- The client sends arguments to the server
	- Which then insert those arguments into a precompiled query template
- *Stored procedures* are an example 

## Sandboxing

- Controlled or isolated environment
- Mitigating potential threats or vulnerabilities
- Application run with restricted permissions and access to system resources
- Testing new or untrusted software
- Easily contained and removed without impact the overall system

>[!TIP] Sandboxes are isolation tools used to contain attacker within an environment where they believe they are conducting an attack but, in reality, are operating in a benign environment.

## Code Security

- Steps to safeguard the creation, storage, and delivery of code

### Code Singing

- Confirm the authenticity of code
- **Cryptographic** function to digitally sign code with **Devs Private key**
	- Then browsers use the **Dev's public key** to verify that signature
- Protect agains **Malicious updates**
	- Attacker attempts to deploy a fake patch
- If system only accept digitally signed updates
	- A malicious update would fail that check and be rejected

### Code Reuse

- Not only internally
	- Third-party software libraries and Software Development Kits (SDKs)
- SDKs are
	- Collection of software libraries
	- Documentation
	- Example
	- Resources designed to help devs
	- Test code
- Ensure that outsourced code is subjected to the same level of testing as internally developed code

### Software Diversity

- Avoid single point of failure
- Identify and monitoring dependencies from
	- Single piece of source code
	- Binary executable files
	- Compilers
- Tracking them

### Code Repositories

- Centralized locations for secure storage and management
- **Version control**
	- Tracking of changes
	- Rollback
- Automated auditing
- Logging of changes
- Search existing code and reuse it
	- Don't start from ground zero
- Avoid the problem of **Dead code**
	- When nobody is responsible for the maintenance
	- Nobody know where the original source files reside

### Integrity Measurement

- Cryptographic hash functions hash to verify the code
	- Released matched the code previously approved

### Application Resilience

- **Scalability** 
	- Computing resources require may be incrementally added to support increasing demand
- **Elasticity** 
	- Provisioning resources automatically to scale when necessary and then automatically deprovision those resources to reduce capacity (and cost) when it is no longer needed

# Secure Coding Practices

- Best practices to help ensure software security

## Source Code Comments

- Placed strategically throughout code
	- Provide documentation of design choices
	- Explain workflow
	- Details to other devs
- Also provide attackers with a roadmap explaining how code works
	- Details that should remain secret
	- Web app that expose their code may allow remote users to view comments left
- **Remove comment** from production versions of the code **before deployment**

## Error Handling

- Write code so that it is **resilient** to unexpected situation
	- Write **Error handling** code
		- That steps in and handles these situation in a secure fashion
- Secondary control (first is *Input Validation*)
	- **Preventing** the malicious input from triggering a **dangerous error condition**
- **Overly verbose** error handling **may explain too much** about the inner workings of code

## Hard-Coded Credentials

- Devs may include usernames and passwords in the source code
- **Backdoor**
	- Devs create a hard-coded maintenance account
	- That allows to regain access even if the authentication system fails
- **Access credentials** for other services within their **source code**

## Package Monitoring

- Track all the third-party library or packages used
	- Being aware of any potential vulnerabilities
- Regular updating these dependencies
- Automated tool can help
	- Identifying outdated or insecure dependencies
- Understand the trustworthiness and reputation of these packages

## Memory Management

- Poor memory management practices can undermine the security of the entire system

### Resource Exhaustion

- Consume all of the memory, storage, processing time, or other resources available
- **Memory leaks**
	- The application fails to return some memory that it no longer needs
		- It can slowly consume all the memory available: crash

### Pointer Dereferencing

- **Memory pointers** are an area of memory that **stores an address** of another location in memory
- One particular issue that might arise is if the **pointer is empty**, containing a null value
	- Causes a *null pointer exception*
	- In best case, causes crash
	- In worst case, bypass security controls

### Buffer Overflow

- Placing **more data into an area of memory** than is allocated for that program's use
- **Overwrite** other information in **memory with instructions** that may be **executed** by different **process**
- **Memory injection**
	- Maliciously inserting information into memory
- Tends to persist for years
- **Integer overflow**
	- Variant where the result of an arithmetic operation attempts to store an integer that is too large to fit in the specified buffer
- Scan report will directly identify an available patch

## Race Conditions

- Occur when the **security of a code segment depends upon the sequence of events** occurring within the system
- **Time-Of-Check (TOC)**
	- Instance when a system verifies access permissions or other security controls
- **Time-Of-Use (TOU)**
	- Moment when the system access the resource or uses the permissions that was granted
- **Target-Of-Evaluation (TOE)**
	- Refers to the particular component, system, or mechanism being evaluated or tested for potential vulnerabilities, such as the system's method of managing and validating access permissions
- A **TOCTTOU** or **TOC/TOU** issue 
	- Is a type of race conditions that occurs when a **program checks access permissions too far ahead of a resource request**
- To prevent
	- Evaluate access permissions at the time of each request rather than caching a list of permissions

>[!TIP] Buffer Overflow: Attempt to use more space than is allocated for a purpose and allow the attacker to perform memory injection, inserting their own content into sensitive memory location. <br> Race Conditions: Occur when the security of a code segment depends on the sequence of events occurring within the system.


## Unprotected APIs

- **Application Programming Interface**
- Unprotected APIs may lead to the unauthorized use of functions
- API that are not intended for public use
	- Should be secured with an authentication mechanism
		- API key
		- Accessed only over encrypted channels

# Automation and Orchestration

- Standardizing tasks also helps you identify opportunity for automation
- Security orchestration, automation, and response (SOAR)
	- Automate security tasks that cross between multiple systems
	- Combine multiple threat feed
- Scripting responses
	- Log analysis
	- Network scanning
	- Alert

## Use Cases of Automation and Scripting

- **User provisioning**
	- Scripts can handle the process of adding, modifying, or removing user access to systems and networks
- **Resource provisioning**
	- Scripts can automate the allocation and deallocation of systems resources
- **Guard rails**
	- Automation to enforce policy controls and prevent violation of security protocols
- **Security groups**
	- Manage security groups memberships, ensuring users have appropriate permissions
- **Ticket creation**
	- Enabling immediate creation and routing of issues to the right teams
- **Escalation**
	- Automate the escalation process, alerting key personnel quickly
- **Enabling/disabling services and access**
	- Turn services or access on or off based on certain triggers or conditions
- **Continuous integration and testing**
	- Build and test process, faster and more reliable software delivery
- **Integrations and APIs**
	- Handle data exchange between different software applications through APIs

## Benefits of Automation and Scripting

- **Achieving efficiency and time savings**
	- Reduces manual tasks
- **Enforcing baselines**
	- Ensures consistent application of security baselines across systems and networks
- **Standardizing infrastructure configurations**
	- Automate the process of configuring systems
- **Scaling in a secure manner**
	- Rapid scaling of infrastructure
- **Retaining employees**
	- Increase job satisfaction
- **Reducing reaction time**
	- Alerts and responses
- **Serving as a workforce multiplier**
	- Handling repetitive tasks

## Other Considerations

- **Complexity**
	- The development and management can be complex and require a high level of technical skill
- **Cost**
	- Upfront costs
- **Single point of failure**
	- Over-reliance could impact a part of operations
- **Technical debt**
	- Systems evolve and change, script became outdated or inefficient
- **Ongoing supportability**
	- Maintaining and updating scripts

>[!TIP] These bullet list are good material to memorize

# Exam Essentials

- **Understand secure software development concepts.**
	- Standardized **Software Development Life Cycle (SDLC)**
		- Development
		- Test
		- Staging
		- Production environment
	- Issue with code reuse and software diversity
	- Web applications industry-standard principles
		- Open Worldwide Application Security Project (OWASP)

- **Know how to analyze the indicators associated with application attacks.**
	- Software applications suffer vulnerabilities
		- Be familiar with these attack
			- Memory injection
			- Buffer overflow
			- Race conditions
		- Web-specific attacks
			- SQL injection (SQLi)
			- Cross-site scripting (XSS)
	- Understanding methods behind these attacks

- **Know how to implement application security controls.**
	- Forefront of security operation principles
	- Protecting code through Input validation
	- Web applications cookies should secure through transport encryption
	- Code review
		- Static and dynamic testing
	- Code signing
		- Code from trusted source
	- Sandboxing
		- Testing in an isolated environment

- **Explain the common benefits and drawbacks of automation and scripting related to secure operations.**
	- Automation and scripting
		- Efficiency and saving time
		- Enforcing baseline
		- Standardizing infrastructure configurations
		- Retaining employees
		- Lowering reaction times
		- Serving as a workforce multiplier
	- Main drawbacks
		- Complexity
		- Cost
		- Single point of failure
		- Technical debt
		- Ongoing supportability

- **Explain common use cases of automation and scripting for cybersecurity.**
	- User and resource provisioning
	- Guard rails
	- Managing security groups
	- Creating and escalating tickets
	- Enabling and disabling services and access
	- Performing continuous integration and testing
	- Use Application Programming Interfaces (APIs)

#cybersecurity 