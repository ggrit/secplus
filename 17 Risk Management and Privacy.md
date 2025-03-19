# 17 Risk Management and Privacy

---

## Domain 3.0: Security Architecture

**3.3. Compare and contrast concepts and strategies to protect data.**

- Data types (Regulated, Trade secret, Intellectual property, Legal information, Financial information, Human- and non-human-readable)
- Data classifications (Sensitive, Confidential, Public, Restricted, Private, Critical)

## Domain 5.0: Security Program Management and Oversight

**5.1. Summarize elements of effective security governance.**

- Roles and responsibilities for systems and data (Owners, Controllers, Processors, Custodians/stewards)

**5.2. Explain elements of the risk management process.**

- Risk identification
- Risk assessment (Ad hoc, Recurring, One-time, Continuous)
- Risk analysis (Qualitative, Quantitative, Single loss expectancy (SLE), Annualized loss expectancy (ALE), Annualized rate of occurrence (ARO), Probability, Likelihood, Exposure factor, Impact)
- Risk Register (Key risk indicators, Risk owners, Risk threshold)
- Risk tolerance
- Risk appetite (Expansionary, Conservative, Neutral)
- Risk management strategies (Transfer, Accept, (Exemption, Exception), Avoid, Mitigate)
- Risk reporting
- Business impact analysis (Recovery time objective (RTO), Recovery point objective (RPO), Mean time to repair (MTTR), Mean time between failures (MTBF))

**5.4. Summarize elements of effective security compliance.**

- Privacy (Legal implications, (Local/regional, National, Global), Data subject, Controller vs. processor, Ownership, Data inventory and retention, Right to be forgotten)

---

# Analyzing Risk

- Enterprise Risk Management (ERM) program 
	- Take a formal approach to risk analysis
		- Identifying risks
		- Determining the severity of each risk
		- Adopting one or more **risk management** strategies to address each risk

- Few important terms
	- **Threats**
		- Any possible events that might have an adverse impact on the CIA of our information or information system
	- **Vulnerabilities**
		- Weaknesses in our systems or controls that could be exploited by a threat
	- **Risks**
		- Intersection of a vulnerability and a threat that might exploit that vulnerability
		- A threat without a corresponding vulnerability does not pose a risk, nor does a vulnerability without a corresponding threat

## Risk Identification

- Risk identification process
	- Identifying threats and vulnerabilities
	- From hacker to hurricanes 

- Some examples
	- **External risks**
		- Originate from a source outside the organization
		- Extremely broad category of risk
			- Cybersecurity adversaries, malicious code, and natural disaster, among many others 
	- **Internal risks**
		- Originate within the organization 
		- Include malicious insider, mistakes made by authorized users, equipment failures, and similar
	- **Multiparty risks**
		- Those that impact more than one organization
		- For example, a power outage or the compromise of an SaaS provider's database
	- **Legacy systems**
		- Outdated systems often do not receive security updates
		- Must take extraordinary measures to protect them against unpatchable vulnerabilities
	- **Intellectual Property (IP) theft**
		- Trade secrets or other proprietary information that, if disclosed, could compromise the organization's business advantage
	- **Software compliance/licensing risks**
		- When an organization licenses software from a vendor and intentionally or accidentally runs afoul of usage limitation that expose the customer to financial and legal risk

## Risk Assessment

- When assess any risk, use two factors
	- **Likelihood of occurrence**, or **probability** 
		- The percent of chance that a threat will exploit a vulnerability over a specified period of time
	- Magnitude of the **Impact**
		- The financial cost that we will incur as the result of a risk

- We can assign each risk a conceptual score by combining the probability and the magnitude
	- **Risk Severity = Likelihood x Impact**
		- This equation does not always have to be interpreted literally

- Laws and regulations facing an industry may play a significant role in determining the impact of a risk

- Risk assessments may be performed in several ways
	- **One-time risk assessments**
		- Point-in-time view of its current risk state
		- May be done in response to a security incident, at the request of management, or when the organization wants a snapshot of its risk profile
	- **Ad hoc risk assessments**
		- Conducted in response to a specific event or situation 
			- New project, technology implementation, or significant change in the business environment
		- Often performed quickly to address a particular concern or set of circumstances
	- **Recurring risk assessments**
		- Performed at regular intervals
		- Meant to track the evolution of risks over time, monitor changes in the risk profile
		- Ensure that risk management practices are adapting to new threats and vulnerabilities
	- **Continuous risk assessments**
		- Ongoing monitoring and analysis of risks
		- Can include automated systems that constantly scan for new threats or changes in the risk environment, as well as regular reviews and updates to the risk management strategy
		- Enables organizations to respond more quickly and effectively to emerging risks

>[!TIP] You might notice some overlap in the terminology above. For example, an ad hoc risk assessment is a type of one-time risk assessment and continuous risk assessments are closely related to recurring risk assessments. These four terms are the types that exam specifically mentions, so be sure you can explain any one of them when you take the exam.

## Risk Analysis

- Risk analysis is a formalized approach to risk prioritization
- Risk assessments follow two different analysis methodologies
	- **Quantitative risk analysis**
		- Uses numeric data in the analysis
		- Assessments that allow the very straightforward prioritization of risks
	- **Qualitative risk analysis**
		- Substitutes subjective judgments and categories for strict numerical analysis
		- Allowing the assessment of risks that are difficult to quantify

- Provide clear communication of risk factors to stakeholders, they often combine elements of quantitative and qualitative risk assessments

### Quantitative risk Analysis

1. **Determine the asset value (AV) of the asset affected by the risk**
	- This *asset value* is expressed in money, and may be determined using the cost to acquire the asset, the cost to replace the asset, or the depreciated cost of the asset, depending on the organization's preferences 
2. **Determine the likelihood that the risk will occur**
	- Risk analysts consult subject matter experts and determine the likelihood (also kwon as the probability) that a risk will occur in a given year
	- Expressed as the number of times the risk is expected each year and is described as the **Annualized Rate of Occurrence (ARO)**
		- A risk that is expected to occur twice a year has an ARO of 2.0, whereas a risk is expected once every one hundred years has an ARO of 0.01
3. **Determine the amount of damage that will occur to the asset if the risk materializes**
	- This is known as the **Exposure Factor (EF)** and is expressed as the percentage of the asset expected to be damaged
	- The exposure factor of a risk that would completely destroy an asset is 100%, whereas a risk that would damage half of an asset has an EF of 50%
4. **Calculate the single loss expectancy**
	- The **Single Loss Expectancy (SLE)** is the amount of financial damage expected each time a risk materialized
	- Calculated by multiplying the AV by the EF
5. **Calculate the annualized loss expectancy**
	- The **Annualized Loss Expectancy (ALE)** is the amount of damage expected from a risk each year
	- Calculated by multiplying the SLE and the ARO 


- Repeat this process for each threat/vulnerability combination

>[!TIP] Be prepared ti explain the terminology of quantitative risk analysis and perform these calculations when you take the exam. When you encounter these questions, watch out for scenarios that provide you with more information than you may need to answer the question. Question writers sometimes provide extra facts to lead you astray. 

- Organizations can use the **ALE** to prioritize their remediation activities and determine the appropriate level of investment in controls that mitigate risks

### Qualitative Risk Analysis

- Describe reputational damage, public health and safety, or employee morale 
- Substituting subjective judgment for objective data 
- Use the same probability and magnitude factors to evaluate the severity of a risk but do so using subjective categories

- Simple qualitative risk analysis that evaluates the probability and magnitude of risks on a subjective Low/Medium/High scale

- Not possible to directly calculate the financial impact of risks
- This scale make possible to prioritize risks 

#### Note

- Many organizations combine quantitative and qualitative techniques to get a well-rounded picture of both the tangible and intangible risks that they face

## Supply Chain Assessment

- You rely on many different vendors to protect the CIA of your data
- Performing vendor *due diligence* is a crucial security responsibility
- Performing hardware source authenticity assessments validates that the hardware you received was not tampered with after leaving the vendor 

# Managing Risk

- Risk management
	- Process of systematically addressing the risks facing an organization

- *Risk assessment* serves two important roles
	- The *risk analysis* 
		- Provides guidance in prioritizing risks so that the risks with the highest probability and magnitude are addressed first
	- Quantitative risk analyses
		- Help to determine whether the potential impact of a risk justifies the costs incurred by adopting a risk management approach 

- Risk managers have four strategies to choose from
	- Risk mitigation
	- Risk avoidance
	- Risk transference
	- Risk acceptance

## Risk Mitigation

- The process of applying security controls to **reduce the probability and/or magnitude of a risk**
- Most common risk management strategy 
- Through the design, implementation, and management of security controls
- Trade-offs between functionality, performance, and security 

## Risk Avoidance

- **Change** our business practices **to completely eliminate the potential** that a risk will materialize 
- Typically have a serious detrimental impact on the business 

## Risk Transference

- **Shifts some of the impact of a risk** from the organization experiencing the risk to another entity
- Most common
	- Purchasing an insurance policy that cover a risk
- Example, insurance cover DDoS attack
	- *Cybersecurity insurance*

## Risk Acceptance

- Take no other risk management strategy and to **simply continue operations as normal**
- If the cost of mitigating a risk is greater than the impact of the risk itself
- In certain cases, mechanism such as *exemptions and exceptions* can be employed
	- **Exemptions** are similar to exceptions but are generally more formal
		- May require a higher level of approval and are often documented
		- Might also have an expiration date and need to be reviewed periodically

- Risk acceptance is a deliberate decision that comes as the result of a thoughtful analysis
- It should not be undertaken as a default strategy
- Simply stating that "we accept this risk" without analysis is not an example of an accepted risk
	- It is an example of an unmanaged risk

>[!TIP] Understand the four risk management strategies: risk mitigation, risk avoidance, risk acceptance, and risk transference when you take the exam. Also remember that in the case of risk acceptance, you have the options of providing an exemption or an exception. Be prepared to provide examples of these strategies and to identify which strategy is being used in a given scenario.

# Risk Tracking

- Few key terms to describe different states of risk
	- **Inherent Risk**
		- Original level of risk that exists before implementing any controls
	- **Residual risk**
		- Risk that remains after an organization implements controls 
			- Designed to mitigate, avoid, and/or transfer the inherent risk
	- **Risk appetite**
		- Level of risk that it is willing to accept as a cost of doing business
		- This is a broad term describing overall risk
	- **Risk threshold**
		- Related to its risk appetite, but its more specific term
		- Is the specific at which a risk becomes unacceptable 
		- Boundary that, when crossed, will trigger some action or decision
		- Usually more quantitative, defining clear points or values
	- **Risk tolerance**
		- Ability to withstand risks and continue operations without any significant impact
	- **Key Risk Indicators (KRI)**
		- Metric used to measure and provide early warning signals for increasing levels of risk
		- These indicators help in tracking the effectiveness of risk mitigation efforts
		- Make sure that the residual risk stays within the risk appetite
	- **Risk owner**
		- An individual or entity responsible for managing and monitoring risks
		- Including implementing necessary controls and actions to mitigate them

- Begins with **Inherent risk**
- Implement **Risk management strategies** to reduce that level of risk
- Continue doing so until the **Residual risk** 
- Is below the organization's **Risk appetite**

## Risk appetite

- Three specific types that may be suitable for different types of organizations
	- **Expansionary risk appetites**
		- Willing to take on higher levels of risk in the pursuit of potential higher rewards
		- Suitable for organizations that are looking to aggressively grow, innovate, or capture market share
		- Often engage in new ventures, investments, or technologies
	- **Neutral risk appetites**
		- Balanced approach
		- Take on moderate levels of risk to achieve steady growth and returns
		- Usually opting for more secure investments and projects
	- **Conservative risk appetites**
		- Tend to avoid high risks and focus on maintaining stability and protecting existing assets
		- Generally risk-averse 
		- Prioritize security and preservation over high growth
		- Common in highly regulated industries or where the consequences of risks are severe 

## Risk Register

- Primary tool that risk management professionals use to track risk facing the organization

- Often provides far too much detail for business leaders
- When communicating risk management concepts to senior leaders
	- Risk professionals often use a **Risk matrix**, or heat map
		- Quickly summarized risks 

- Risk register common data elements 
	- Risk owner
	- Risk threshold information
	- Key Risk Indicators (KRI)

>[!TIP] These three risk register elements: risk owner, risk threshold, and KRI are specifically mentioned in the exam objective.

## Risk Reporting

- Involves communicating the status and evolution of risks to stakeholders within the organization
- Ensures that decision-makers are aware of the current risk landscape
	- Can make informed choices regarding risk mitigation strategies, allocation of resources, and setting priorities

- Some forms of risk reporting
	- **Regular Updates**
		- Routine reports
		- Provide stakeholders with the status of risks, the effectiveness of controls, and any recent changes or developments
	- **Dashboard Reporting**
		- Visual aids like graphs and charts to summarize risk data
			- Usually in real time
		- Quick understanding and monitoring of Key Risk Indicators (KRI)
	- **Ad Hoc Reports**
		- Produced as needed, typically in response to specific events or situation 
			- That require immediate attention or in-depth analysis
	- **Risk Trend Analysis**
		- Analyzing historical data to identify patterns or trends in the risk faced by the organization
		- Helps predicting possible future risks or understanding the evolution o current risks
	- **Risk Event Reports**
		- Focused on documenting specific risk events
			- Such as security breaches or incidents, their impacts, and the responses taken

- Be sure to tailor the information and format to the audience 
	- Top-level management
		- Summarized dashboards or high-level reports
	- Risk management team
		- Detailed data for analysis

- Reports should be clear, concise, and focused, providing essential information that supports decision-making
- Not only highlight the current status but also provide context
	- Changes since the last report and how the information relates to the risk appetite and thresholds

# Disaster Recovery Planning

- **DRP** developing plans to recover operations as quickly as possible in the face of a disaster

## Disaster Types

- Disaster any event that has the potential to disrupt an organization's business
	- Occurrence of a disaster triggers the activation of the organization's DRP

- As part of DRP process
	- Organizations should conduct site risk assessments for each of their facilities
		- These risk assessments should seek to identify and prioritize the risks posed to the to the facility by a disaster
			- Both internal and external risks from both environmental and human-made disasters

## Business Impact Analysis

- **BIA** is a formal process designed to identify the mission-essential functions within an organization
	- And facilitate the identification of the critical systems that support those functions

- Four key metrics used in the BIA process
	- **Mean Time Between Failures (MTBF)** 
		- Measure of the reliability of a system
		- Expected amount of time that will elapse between system failures 
	- **Mean Time To Repair (MTTR)**
		- Average amount of time to restore a system to its normal operating state after a failure
	- **Recovery Time Objective (RTO)**
		- Amount of time that the organization can tolerate a system being down before it is repaired
		- Service team is meeting expectations when the time to repair is less than the RTO
	- **Recovery Point Objective (RPO)** 
		- Amount of data that the organization can tolerate losing during an outage

- Each of these metrics allow the organization to evaluate the impact of different risks on tis operations
	- And the acceptability of the state of its disaster recovery controls 

- Particular attention to **Single Point of Failure**

# Privacy

- Personally Identifiable Information (PII)
	- If disclosed would jeopardize the privacy of one or more individuals

- Consequences may include reputational damage, fines, and the loss of important Intellectual Property (IP) 

- Evaluating privacy risks
	- Legal implications that may exist based on the jurisdiction where your business operates
		- Should be familiar with local, regional, national, and global privacy requirements

- **Privacy notice**
	- Outlines privacy commitments 
	- Laws or regulations may require that
- In some cases, organizations may include privacy statements in their *terms of agreement*
	- With customers and other stakeholders

## Data Inventory

- Many different types of sensitive and personal information

- Data types
	- **Personally Identifiable Information (PII)**
		- Information that uniquely identifies an individual person
			- Including customers, employees, and third parties
	- **Protected Health Information (PHI)**
		- Medical records maintained by health-care providers 
		- And other organizations that are subject to the Health Insurance Portability and Accountability Act (HIPAA)
	- **Financial information**
		- Any personal financial records maintained by the organization
		- Some of these records may be subject to the provisions of the Gramm-Leach-Bliley Act (GLBA) and/or the Payment Card Industry Data Security Standard (PCI DSS)
	- **Intellectual property** includes **trade secrets**
		- Encompass proprietary business information that provides a company with a competitive edge
			- Such as formulas, manufacturing processes, strategies, or any other confidential information
	- **Legal information**
		- Includes documents, communications, and records that are related to legal proceedings, contracts, or corporate governance
		- Might include attorney-client privileged communications, contracts, legal opinions, court records, and regulatory filings
	- **Regulated information**
		- Any data that is governed by laws or regulations
		- Includes the regulations discussed earlier (HIPAA, GLNA, and PCI DSS), as well as any other rules governing different categories of information 

>[!TIP] It's very important to understand that this inventory should include all forms of information maintained by the organization. The exam objectives specifically mention that you should include both human-readable and non-human-readable information in you inventory. For example, binary format data files that contain PII are still PII whether they can be read by a human being or whether they require specialized software to read

## Information Classification

- Categories based on the sensitivity of the information
	- And impact on the organization should the information be inadvertently disclosed

- For example, US government uses the following
	- **Top Secret** information
		- Requires the highest degree of protection
		- Disclosure causes exceptionally grave damage to national security
	- **Secret** information
		- Requires substantial degree of protection
		- Disclosure causes serious damage to national security
	- **Confidential** information
		- Requires some protection
		- Disclosure causes identifiable damage to national security
	- **Unclassified** information
		- Does not meet the standards for classification under the other categories
		- Still not publicly releasable without authorization

- Business generally use more friendly terms
	- Highly sensitive, sensitive, internal, and public 

>[!TIP] Exam includes a listing of classification levels. As you prepare for the exam, become familiar with these example that are commonly used in business: Public, Private, Sensitive, Confidential, Critical, Restricted. It's important to understand that there are no "official" classification levels in business. Each of these terms may be used differently between organizations and it is likely that different firms may use these terms for different purposes. It's very important to review your organization's classification policy and understand the different levels in use and their meanings.

- Data classification allow organization to clearly specify the security controls required to protect information with different level of sensitivity

## Data Roles and Responsibilities

- **Data ownership** policies and procedures 
	- The organization designates specific senior executives as the data owners for different data types
		- For example, vice president of HR might be the data owner for employment and payroll data

- Data owners delegate some of their responsibilities to other in the organization
	- Also rely on advice from subject matter experts (SME)
		- Such as cybersecurity analyst and data protection specialists

- Other important data privacy roles
	- **Data subjects**
		- Individuals whose personal data is being processed
		- Can include customers, employees, and partners
		- Often have rights regarding their data 
			- Such as the right to access, correct, or request the deletion of their data
	- **Data controllers**
		- Entities who determine the reasons for processing personal information 
			- And direct the methods of processing that data
		- Term is used primarily in EU law
			- It serves as a substitute for the term data owner to avoid a presumption that anyone who collects data has an ownership interest in that data
	- **Data stewards**
		- Individuals who carry out the intent of the data controller 
			- And are delegated responsibility from the controller
	- **Data custodians**
		- Individuals or teams who do not have controller or stewardship responsibility
		- Responsible for the secure safekeeping of information
	- **Data processors**
		- Service providers that process personal information on behalf of a data controller

## Data Protection Officers

 - Who bears overall responsibility for carrying out the organization's data privacy efforts
 - Often given the title of Chief Privacy Officer
	 - Bears the ultimate responsibility for data privacy
	- Must coordinate across functional teams to achieve the organization's privacy objectives

- The EU General Data Protection Regulation (GDPR) formalizes this role
	- Every data controller designate a Data Protection Officer (DPO)
		- Grant that individual the autonomy to carry out their responsibilities without undue oversight

## Information Life Cycle

- Data protection should continue at all stages of the information life cycle

- At early stages of the data life cycle
	- Organization should practice **Data Minimization**
		- Collect the smallest possible amount of information necessary to meet their business requirements
		- Information not necessary should either be immediately discarded or, better yet, not collected in the first place

- Although information remains within the care of organization, the organization should practice **Purpose limitation**
	- Information should be used only for the purpose that it was originally collected and that was consented to by the data subjects 

- At the end of the life cycle
	- **Data retention** standards that guide the end of the data life cycle
	- Data should only be kept for as long as it remains necessary to fulfill the purpose
	- At the conclusion of its life cycle, data should be securely destroyed

## Right to Be Forgotten 

- Also known as the right to erasure
- Concept that has been implemented in various data protection laws
	- Notably the EU GDPR

- Allow individuals to request the deletion of personal data about them under certain circumstances
- Under GDPR
	- The data is no longer needed for its original purpose
	- The individual withdraws consent
	- The individual objects and there is no overriding legitimate interest to continue processing
	- The data has been unlawfully processed
	- There is a legal obligation to erase the data

- The principle behind this right is that outdated or incorrect information
	- Can be harmful or misleading 
	- Individuals should have some degree of control over their personal information online

- Can be challenging from both technical and procedural standpoints

>[!TIP] Reducing the amount of data that you retain is a great way to minimize your security risk. Remember this as you answer exam questions that ask you to identify the best or most effective strategy for reducing risk.

## Privacy Enhancing Technologies

- If we can't completely remove data from a data set
	- We can often transform it into a format where the original sensitive information is anonymized
- True anonymization may be quite difficult to achieve
	- Often use pseudo-anonymization techniques
		- **Deidentification**
			- Process removes the ability to link data back to an individual, reducing its sensitivity

- An alternative is transforming it into a format where the original information can't be retrieved
	- **Data obfuscation**
		- Several tools to assist with it
			- **Hashing**
				- Hash function to transform a value in our dataset to a corresponding hash value
			- **Tokenization**
				- Replace sensitive value with a unique identifier using a lookup table
				- If you use this approach, you need to keep the lookup table secure
			- **Data masking**
				- Redacts sensitive information by replacing some or all sensitive fields with blank characters
				- With "x" or "\*"

- Isn't possible to retrieve the original value directly from the hashed value
	- But if someone has a list of possible value for a filed
		- They can conduct something called a **Rainbow Table attack**
			- Computes the hashes of those candidate values and then checks to see if those hashes exist in your data file

## Privacy and Data Breach Notification

- In the event of a data breach
	- Organization should immediately activate its cybersecurity incident response plan
		- Should include procedures for the notification of key personnel and escalation of serious incidents

- Responsibility under national and regional laws
	- To make public notification and disclosures in the wake of a data breach
		- May be limited to the individuals involved or may require notification of government regulators and/or the news media

- In US every state has a data breach notification law with different requirements for triggering notification
- US lacks a federal law requiring broad notification for all security breaches
	- But does have industry-specific laws and requirements that require notification in some circumstances
- EU GDPR also includes a breach notification requirement

- Breach notification requirements
	- Vary by industry and jurisdiction
	- An organization experiencing a breach may be required to untangle many overlapping requirements
		- For this reason, organization should consult with an attorney who is well versed in this field

# Exam Essentials

- **Risk identification and assessment helps organization prioritize cybersecurity efforts.**
	- Cybersecurity analyst seek to identify all of the risk facing their organization
		- Then conduct a business impact analysis to asses the potential degree of risk
			- Based on the probability that it will occur and the magnitude of the potential effect 
	- This work allow security professionals to prioritize risk
		- And communicate risk factors to others in the organization

- **Vendors are a source of external risk.**
	- Organization should conduct their own systems assessments as part of their risk management practices
		- But the should also conduct supply chain assessments as well
	- Performing vendor due diligence reduces the likelihood that a previously unidentified risk at a vendor will negatively impact the organization 
	- Hardware source authenticity techniques verify that hardware was not tampered with after leaving the vendor's premises 

- **Organizations may choose from a variety of risk management strategies.**
	- Risk avoidance strategies change business practices to make a risk irrelevant to the organization
	- Risk mitigation techniques seek to reduce the probability or magnitude of a risk
	- Risk transference approaches move some of the risk to a third party
	- Risk acceptance acknowledges the risk and continues normal business operations despite the presence of the risk

- **Disaster recovery planning builds resiliency.**
	- Disaster recovery plans activate when an organization experiences a natural or human-made disaster that disrupts its normal operations
	- The disaster recovery plan helps the organization quickly recover its information and systems and resume normal operations

- **Privacy controls protect personal information.**
	- Organization handling sensitive personal information should develop privacy program that protect that information from misuse and unauthorized disclosure
	- The plan should cover personally identifiable information (PII), protected health information (PHI), financial information, and other records maintained by the organization that might impact personal privacy

#cybersecurity 
