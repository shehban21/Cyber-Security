# 

# ![][image1]

# RANSOMWARE INCIDENT PLAYBOOK {#ransomware-incident-playbook}

# Table of Contents {#table-of-contents}

[**RANSOMWARE INCIDENT PLAYBOOK	1**](#ransomware-incident-playbook)

[**Table of Contents	2**](#table-of-contents)

[**Playbook Revision Log	3**](#playbook-revision-log)

[**Executive Summary	4**](#executive-summary)

[**Roles, Responsibilities and Contact Information	5**](#roles,-responsibilities-and-contact-information)

[Incident Response Team Responsibilities	5](#incident-response-team-responsibilities)

[Testing and Updates	12](#testing-and-updates)

[Incident Response Process Overview	13](#incident-response-process-overview)

[**Incident Response Checklist	14**](#incident-response-checklist)

[**Responsibilities at a Glance	19**](#responsibilities-at-a-glance)

[**Escalation Considerations	20**](#escalation-considerations)

[**Communications Considerations	21**](#communications-considerations)

[Stakeholder Communications	21](#stakeholder-communications)

[Information to Withhold	21](#information-to-withhold)

[APPENDIX A \- Threat Classification	22](#appendix-a---threat-classification)

[APPENDIX B \- Compliance and Legal Obligations	23](#appendix-b---compliance-and-legal-obligations)

[APPENDIX C \- Playbook Activation Flowchart	25](#appendix-c---playbook-activation-flowchart)

[**APPENDIX D \- Ransomware Flowchart	26**](#appendix-d---ransomware-flowchart)

[**APPENDIX E \- Citations	27**](#appendix-e---citations)

This playbook follows the template from Cynet which can be found at: [https://www.cynet.com/incident-response/incident-response-plan-template/](https://www.cynet.com/incident-response/incident-response-plan-template/)

# Playbook Revision Log {#playbook-revision-log}

| Document Name | BC-Ferries-Ransomware |
| :---- | :---- |
| Version | 1.0 |
| Plan Owner | IR Team Lead |
| Plan Approver | CEO |
| Date of Last Review | 10 Aug 2024 |

| Revision | Description of Change | Effective | Author | Approver | Signature |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1.0 | Playbook Creation | 10 Aug 2024 | IR Team Lead | CEO |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |

# 

# Executive Summary {#executive-summary}

This report serves as a playbook to use in case BC Ferries faces a ransomware attack. A ransomware is a type of malware, a type of software that is designed to be harmful to a device. A ransomware in particular is used by malicious agents to hold valuable information like company servers or Personal Identifiable Information (PII) of customers or employees as hostage to extort a ransom.

A playbook is a step by step guide to use in case of a particular type of Cyber Incident. This report provides different ways in which a ransomware scenario can go and what to do in those scenarios.

The report also provides a look at the roles and responsibilities all the employees in BC Ferries should follow. It also provides contact information for important Executives in case an escalation is required. The Incident Response Team and the steps they should take are also detailed in a checklist.

This playbook should be tested and updated annually taking into account organisational changes and new technology developments. 

# 

# Roles, Responsibilities and Contact Information {#roles,-responsibilities-and-contact-information}

The Security Incident response plan is to be followed by all personnel, including all employees, temporary staff, consultants, suppliers and third parties operating on behalf of **BC Ferries**. All personnel are referred to as staff within this plan.

Below are details about the roles and responsibilities of each member of BC Ferries to prevent and respond to a workplace incident. It is not an exhaustive list of duties but designed to give each employee a general understanding of their role and the roles of other employees in incident response and prevention.

## Incident Response Team Responsibilities {#incident-response-team-responsibilities}

The Incident Response Lead is tasked with:

* Ensuring that the Security Incident Response Plan, along with related response and escalation procedures, is clearly defined and documented to guarantee a prompt and effective approach to handling security incidents.  
* Keeping the Security Incident Response Plan up-to-date, with reviews and tests conducted at least annually.  
* Providing proper training to staff responsible for the Security Incident Response Plan at least once a year.  
* Taking charge of investigating suspected breaches or reported security incidents and activating the Security Incident Response Plan as necessary.  
* Coordinating with external entities, including relevant business partners, legal representatives, and law enforcement, when required.  
* Approving on-site investigations by appropriate law enforcement or third-party security/forensic professionals during any security incident. This includes authorising the access to or removal of evidence from the site.

The members of the Security Incident Response Team (SIRT) are responsible for:

* Making sure that all staff understand how to identify and report a suspected or actual security incident.  
* Advising the Incident Response Lead of an incident when they receive a security incident report from staff.  
* Investigating and documenting each reported incident.  
* Taking action to limit the exposure of sensitive data and to reduce the risks that may be associated with any incident.  
* Gathering, reviewing and analysing logs and related information from various central and local safeguards, security methods and controls.  
* Documenting and maintaining accurate and detailed records of the incident and all activities that were undertaken in response to an incident.  
* Assisting law enforcement during the investigation processes. This includes any forensic investigations and prosecutions.  
* Initiating follow-up actions to reduce the likelihood of recurrence as appropriate  
* Determining of policies, processes, technologies, security measures or controls need to be updated to avoid a similar incident in the future. They also need to consider whether additional safeguards are required in the environment where the incident occurred.

All staff members are responsible for:

* Making sure they understand how to identify and report a suspected or actual security incident.  
* Reporting a suspected or actual security incident to the Incident Response Lead (preferable) or to another member of the Security Incident Response Team (SIRT).  
* Reporting any security related issues or concerns to line managemen, or to a member of the SRT.  
* Complying with the security policies and procedures of **BC Ferries**.

| ROLE | RESPONSIBILITY | CONTACT DETAILS |
| ----- | ----- | ----- |
| **INFORMATION SECURITY** |  |  |
| **CIO / CISO** | Strategic lead. Develops technical, operational, and financial risk ranking criteria used to prioritise incident response plan. Authorises when and how incident details are reported. Main point of contact for the executive team and Board of Directors. | Name: James Tan\[1\] Phone: (555) 555-5555 Email: jtan@bcferries.com |
| **Incident Response Team Lead and Team Members** | Central team that authorises and coordinates incident response across multiple teams and functions through all stages of a cyber incident. Maintains incident response plan, documentation, and catalogue of incidents. Responsible for identifying, confirming, and evaluating the extent of incidents. Conducts random security checks to ensure readiness to respond to a cyberattack. | Name: Aiden Mercer Phone: (555) 555-5556 Email: amercer@bcferries.com |
| **Identity and Access Team Lead and Team Members** | Responsible for privilege management, enterprise password protection and role-based access control. Discovers, audits, and reports on all privilege usage. Conducts random checks to audit privileged accounts, validate whether they are required, and re-authenticate those that are. Monitors privileged account uses and proactively checks for indicators of compromise, such as excessive logins, or other unusual behaviour. Informs incident response team of potential attacks that compromise privileged accounts, validates and reports on the extent of attacks. Takes action to prevent the spread of a breach by updating privileges. | Name: Priya Singh Phone:(555) 555-5557 Email: psingh@bcferries.com |
| **IT Operations and Support (internal)** | Manages access to systems and applications for internal staff and partners. Centrally manages patches, hardware and software updates, and other system upgrades to prevent and contain a cyberattack. | Name: Ethan Collins Phone: (555) 555-5558 Email: ecollins@bcferries.com |
| **Technical Partners (ISP, MSP, Hosting, Testing Partners, etc.)** | Manages security controls to limit the progression of a cyberattack across third-party systems and organisations. | Name: Sofia Martinez Phone: (555) 555-5559 Email: smartinez@bcferries.com |
| **Third Party External Incident Response Teams** | Coordinates with the Internal Response Team to manage risks. Professional Incident response teams help ensure a solid Incident Response process is followed. It is highly recommended that the company identify and prepare an External Response Team that can be available in an emergency IR situation and provide any requested information prior to an emergency to help them become familiar with your environment. | Name: Caleb Foster Phone: (555) 555-5550 Email: cfoster@bcferries.com |

| ROLE | RESPONSIBILITY | CONTACT DETAILS |
| ----- | ----- | ----- |
| **COMPLIANCE** |  |  |
| **Legal Counsel** | Confirms requirements for informing employees, customers, and the public about cyber breaches. Responsible for checking in with local law enforcement. Ensures IT team has legal authority for privilege account monitoring. | Name: Maya Thomas Phone: (555) 555-5551 Email: mthomas@bcferries.com |
| **Audit & Compliance** | Communicates with regulatory bodies, following mandated reporting requirements. | Name: Liam O’Reilly Phone: (555) 555-5552 Email: loreilly@bcferries.com |
| **Human Resources** | Coordinates internal employee communications regarding breaches of personal information and responds to questions from employees. | Name: Zara Patel Phone: (555) 555-5553 Email: zpatel@bcferries.com |
| **Regulatory Contacts** | Receives information about a breach according to timeline and format mandated by regulatory requirements. | Name: Leila Khan Phone: (555) 555-5554 Email: lkhan@bcferries.com |

| ROLE | RESPONSIBILITY | CONTACT DETAILS |
| ----- | ----- | ----- |
| **COMMUNICATIONS** |  |  |
| **Marketing & Public Relations Lead** | Communicates externally with customers, partners, and the media. Coordinates all communications and requests for interviews with internal subject matter experts and security team. Maintains draft crisis communications plans and statements which can be customised and distributed quickly in case of a breach. | Name: Chloe Nguyen Phone: (555) 555-5560 Email: cnguyen@bcferries.com |
| **Web & Social Media Lead** | Posts information on the company website, email, and social media channels regarding the breach, including our response and recommendations for users. Sets up monitoring across social media channels to ensure we receive feedback or questions sent by customers through social media. | Name: Amara Johnson Phone: (555) 555-5561 Email: ajohnson@bcferries.com |
| **Technical Support Lead** (Internal) | Provides security bulletins and technical guidance to employees in case of a breach, including required software updates, password changes, or other system changes. | Name: Oliver Bennett Phone: (555) 555-5562 Email: obennett@bcferries.com |
| **Technical Support Lead** (External) | Provides security bulletins and technical guidance to external users in case of a breach. | Name: Noah Carter Phone: (555) 555-5566 Email: ncarter@bcferries.com |

## Testing and Updates {#testing-and-updates}

Annual testing of the Incident Response Plan using walkthroughs and practical simulations of potential incident scenarios is necessary to ensure the SIRT are aware of their obligations, unless real incidents occur which test the full functionality of the process.

1. The Incident Response Plan will be tested annually.   
2. The Incident Response Plan Testing will test BC Ferries’s response to potential incident scenarios to identify process gaps and improvement areas.  
3. The SIRT will record observations made during the testing, such as steps that were poorly executed or misunderstood by participants and those aspects that need improvement.  
4. The Incident Response Lead will ensure the Security Incident Response Plan is updated and distributed to SIRT members.

# Incident Response Process Overview {#incident-response-process-overview}

Below is the structured 7-step process followed in this document as defined by the NIST in their publication Computer Security Incident Handling Guide (NIST.SP.800-61r2)\[2\]. The seven steps outlined are:

1. Preparation(Preparation) — review and codify an organisational security policy, perform a risk assessment, identify sensitive assets, define which are critical security incidents the team should focus on, and build a Computer Security Incident Response Team (CSIRT).  
2. Identification(Detection and Analysis) — monitor IT systems and detect deviations from normal operations and see if they represent actual security incidents. When an incident is discovered, collect additional evidence, establish its type and severity, and document everything.   
3. Containment (Containment, Eradication and Recovery) — perform short-term containment, for example by isolating the network segment that is under attack. Then focus on long-term containment, which involves temporary fixes to allow systems to be used in production, while rebuilding clean systems.  
4. Eradication (Containment, Eradication and Recovery) — remove malware from all affected systems, identify the root cause of the attack, and take action to prevent similar attacks in the future.  
5. Recovery (Containment, Eradication and Recovery) — bring affected production systems back online carefully, to prevent additional attacks. Test, verify and monitor affected systems to ensure they are back to normal activity.  
6. Lessons learned (Post-Incident Activity) — no later than two weeks from the end of the incident, perform a retrospective of the incident. Prepare complete documentation of the incident, investigate the incident further, understand what was done to contain it and whether anything in the incident response process could be improved.   
7. Follow-up Report (Post-Incident Activity) \- A report covering the incident and the impact it had on the company should be followed up after the systems have fully recovered. It should include the number of incidents, the time spent on each incident and an objective and subjective assessment of the incident.

			Incident Response Life Cycle

# Incident Response Checklist {#incident-response-checklist}

To demonstrate and improve the effectiveness of BC Ferries incident response team and security tools, BC Ferries requires a record of all actions taken during each phase of an incident. Supporting documentation is required, including all forensic evidence collected such as activity logs, memory dumps, audits, network traffic, and disk images.

| PHASE OF CYBER INCIDENT | ACTION | TEAM MEMBER / SYSTEM | DAY / TIME ACTION TAKEN |
| ----- | ----- | ----- | ----- |
| **Incident Discovery and Confirmation** | Describe how the team first learned of the attack (security researcher, partner, employee, customer, auditor, internal security alert, etc.). |   |   |
|  | Analyse audit logs and security applications to identify unusual or suspicious account behaviour or activities that indicate a likely attack and confirm attack has occurred. |   |   |
|  | Describe potential attackers, including known or expected capabilities, behaviours, and motivations. |   |   |
|  | Identify access point and source of attack (endpoint, application, malware downloaded, etc.) and responsible party. |   |   |
|  | Prepare an incident timeline to keep an ongoing record of when the attack occurred and subsequent milestones in analysis and response. |   |   |
|  | Check applications for signatures, IP address ranges, files hashes, processes, executables names, URLs, and domain names of known malicious websites. |   |   |
| **Containment and Continuity** | Enable temporary privileged accounts to be used by the technical and security team to quickly access and monitor systems. |   |   |
|  | Protect evidence. Back up any compromised systems as soon as possible, prior to performing any actions that could affect data integrity on the original media. |   |   |
|  | Force multi-factor authentication or peer review to ensure privileges are being used appropriately. |   |   |
|  | Change passwords for all users, service, application, and network accounts. |   |   |
|  | Increase the sensitivity of application security controls (allowing, denying, and restricting) to prevent malicious malware from being distributed by the attacker. |   |   |
|  | Remove systems from production or take systems offline if needed. |   |   |
|  | Inform employees regarding breach containment. |   |   |
|  | Analyse, record, and confirm any instances of potential data exfiltration occurrences across the network. |   |   |
|  | Potentially share information externally regarding breach containment (website updates, emails, social media posts, tech support bulletins, etc.). |   |   |
| **Eradication** | Close firewall ports and network connections. |   |   |
|  | Test devices and applications to be sure any malicious code is removed. |   |   |
|  | Compare data before and after the incident to ensure systems are reset properly. |   |   |
|  | Inform employees regarding eradication. |   |   |
|  | Potentially share information externally regarding eradication (website updates, emails, social media posts, tech support bulletins, etc.). |   |   |
| **Recovery** | Download and apply security patches. |   |   |
|  | Close network access and reset passwords. |   |   |
|  | Conduct vulnerability analysis. |   |   |
|  | Return any systems that were taken offline to production. |   |   |
|  | Inform employees regarding recovery. |   |   |
|  | Share information externally regarding recovery (website updates, emails, social media posts, tech support bulletins, etc.). |   |   |
|  | Review forensic evidence collected. |   |   |
| **Lessons Learned** | Assess incident cost. |   |   |
|  | Write an Executive Summary of the incident. |   |   |
|  | Report to the executive team and auditors if necessary. |   |   |
|  | Implement additional training for everyone involved in incident response and all employees. |   |   |
|  | Update incident response plan. |   |   |
|  | Inform employees regarding lessons learned, additional training, etc. |   |   |
|  | Potentially share information externally (website updates, emails, social media posts, tech support bulletins, etc.). |   |   |

# Responsibilities at a Glance {#responsibilities-at-a-glance}

| Activity | Role |  |  |  |  |
| ----- | :---: | ----- | ----- | ----- | ----- |
|   | **CSIRT Incident Lead** | **IT Contact** | **Legal Representative** | **Communications Officer** | **Management** |
| Initial Assessment | Owner | Advises | None | None | None |
| Initial Response | Owner | Implements | Updates | Updates | Updates |
| Collects Forensic Evidence | Implements | Advises | Owner | None | None |
| Implements Temporary Fix | Owner | Implements | Updates | Updates | Advises |
| Sends Communication | Advises | Advises | Advises | Implements | Owner |
| Check with Local Law Enforcement | Updates | Updates | Implements | Updates | Owner |
| Implements Permanent Fix | Owner | Implements | Updates | Updates | Updates |
| Determines Financial Impact on Business | Updates | Updates | Advises | Updates | Owner |

# Escalation Considerations {#escalation-considerations}

All incidents can not be handled by the first responders or the Level 1 SOC Analysts assigned to monitor the systems. Sometimes, it is required to call higher management or third party consultants to investigate the incident and prevent damage. There are some considerations that are required to make that decision to escalate. They are:

1. **Systems Affected:** The number of systems affected by the ransomware attack can determine if the company can function normally or not. And it also matters what the affected system handles. A ransomware attack on the company server would be much more impactful than an attack on a random employee’s work laptop.  
   1. Escalate to CIO, Systems Admin  
2. **Ransom:** If a ransom demand is made for a device and there’s important data on it, the issue should be escalated to decision making people in the company.  
   1. Escalate to C-Suite  
3. **Unauthorised Encryption:** Some ransomware attacks lock the data they have accessed behind an encryption. Some encryption methods are impossible to break and even if the server is disconnected from the ransomware attackers, it might make the data unusable.  
   1. Escalate to C-Suite  
4. **Legal and Regulatory Issues:** There might be legal and regulatory problems due to the ransomware attackers accessing Personal Identifiable Information about customers, employees and more.   
   1. Escalate to CIO, Legal  
5. **External Communication:** The decision to notify the public and others outside the organisation needs to be made by the authority responsible for it. What to disclose and when are decisions that need to be made.  
   1. Escalate to Public Relations Lead, CIO

# Communications Considerations {#communications-considerations}

The last point in the previous section outlines how the issue of external communication should be escalated to an authority who can make a decision about it. This is essential as sensitive information regarding the incident cannot be released to parties who can take advantage of that information to use against BC Ferries. Some considerations for the communication are as follows:

## Stakeholder Communications {#stakeholder-communications}

* Anything that will affect end user accessing the service needs to be communicated  
* Any cancellations in ferry travels need to be reported well in advance to avoid bad experience to customers  
* If there is any data breach, all the affected parties must be notified as soon as possible so they can take necessary precautions to prevent damage  
* All the corporate suite needs to know the overall summary of it. A non technical version of the report should be presented to keep the management up to date on the issue and the consequences of the incident.  
* The legal and regulatory compliance officers need to know the parts of the issue that affect these areas of compliance.  
* Insurance agents need to know the extent of the issue to see if their coverage is applicable.  
* There should be a clear communication with the public about the issue and how long it would take to fix. Social media would be the best way to communicate the same.

## Information to Withhold {#information-to-withhold}

There is some information which should not be released to the public or to anyone outside the Incident Response Team. Some of this includes:

* Any information regarding the investigation into the incident  
* Proprietary Information  
* Unconfirmed speculation  
* Vulnerability that was exploited to carry out the attack  
* Any Personal Identifiable Information

# **APPENDIX A \- Threat Classification** {#appendix-a---threat-classification}

The CIA Triad (Confidentiality, Integrity, and Availability) is a framework for incident classification that helps to prioritise the level of incident response required for a cyberattack.

1\.	**Confidentiality** – Incidents involving unauthorized access to systems, including privileged account compromise. The more confidential the data or the more important the systems are to the business, the higher the potential impact.

2\.	**Integrity** – Incidents involving data poisoning, including leveraging a privileged account to corrupt or modify data. The more sensitive the data, the higher the potential impact.

3\.	**Availability** – Incidents that impact the availability or proper functioning of services, such as Distributed Denial of Service (DDoS) or ransomware, including use of privileged accounts to make unauthorized changes. The more critical the services to the business, the higher the potential impact.

When ranking the level of risk to the organisation and the type of incident response required, you must consider the extent to which privileged accounts are compromised, including those associated with business users, network administrators, and service or application accounts. When privileged accounts are involved in the breach, the level of risk increases exponentially as does the response required.

# **APPENDIX B \- Compliance and Legal Obligations** {#appendix-b---compliance-and-legal-obligations}

**HIPAA and HITECH**

Any organisation that creates, receives, maintains, or transmits electronic protected health information (ePHI) in the United States must meet HIPAA requirements for access control and data sharing.

·  	**Reporting requirements** – The HIPAA Breach Notification Rule, 45 CFR §§ 164.400-414, requires HIPAA covered entities and their business associates to provide notification following a breach of unsecured protected health information.

·  	Similar breach notification provisions implemented and enforced by the Federal Trade Commission (FTC) apply to vendors of personal health records and their third-party service providers, pursuant to section 13407 of the HITECH Act.

·  	**Learn more** – [https://www.hhs.gov/hipaa/for-professionals/breach-notification/index.html](https://www.hhs.gov/hipaa/for-professionals/breach-notification/index.html)

 

**PCI DSS**

PCI DSS provides organisations that accept, store, or transmit credit card data with guidelines for privilege management and a framework to protect cardholder data.

·   	**Reporting requirements** – PCI DSS requires entities to have an incident response plan and alert affected parties immediately. [PCI DSS 3.2.1](https://www.pcisecuritystandards.org/document_library/), released in May 2018, marks the latest version.

·   	You may want to set up an arrangement with an independent Payment Card Industry Forensic Investigator (PFI) to call if you need outside expertise.

·   	**Learn more** – [https://www.pcisecuritystandards.org/documents/PCI\_SSC\_PFI\_Guidance.pdf](https://www.pcisecuritystandards.org/documents/PCI_SSC_PFI_Guidance.pdf) 

**FISMA/NIST**

FISMA is United States legislation intended to protect the security, confidentiality, and integrity of government data systems. A FISMA audit is a test of an organisation’s system against the controls outlined in various NIST publications such as NIST SP 800-53, NIST SP 800-171, FIPS 199, and FIPS 200\.

·   	**Reporting requirements** – A FISMA audit is a test of an organisation’s system against the controls outlined in various NIST publications such as NIST SP 800-53, NIST SP 800-171, FIPS 199, and FIPS 200\.

·   	**Learn more** – [https://csrc.nist.gov/projects/risk-management](https://csrc.nist.gov/projects/risk-management)

**NERC/CIP**

The NERC Critical Infrastructure Protection (CIP) Standards apply to the cyber security aspects of the Bulk Electric System and its efficient and reliable supply.

·   	**Reporting requirements** – Reliability standards require the reporting of cyber security incidents that compromise, or attempt to compromise, a responsible entity’s Electronic Security Perimeter (ESP) or associated Electronic Access Control or Monitoring Systems (EACMS).

·   	**Learn more** – [https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)

**SOX**

Sarbanes-Oxley (SOX) is designed to reduce corporate fraud by requiring an increase in the strength and granularity of security controls for financial auditing and reporting.

·   	**Reporting requirements** – Companies must disclose failure of security safeguards and security breaches to SOX auditors.

·   	**Learn more** – [https://www.sarbanes-oxley-101.com/](https://www.sarbanes-oxley-101.com/)

**EU GDPR**

Any organisation dealing with EU citizens' Personally Identifiable Information is obligated to meet standards for effective data protection, adequate security measures, and privacy by design to comply with EU GDPR.

·   	**Reporting requirements** – Under GDPR, breach notification is mandatory in all member states where a data breach is likely to result in a risk for the rights and freedoms of individuals. This must be done within 72 hours of first having become aware of the breach. Data processors are required to notify their customers, the controllers, without undue delay after first becoming aware of a data breach.

·   	**Learn more** – [https://www.eugdpr.org/key-changes.html](https://www.eugdpr.org/key-changes.html)

##### 

# **APPENDIX C \- Playbook Activation Flowchart** {#appendix-c---playbook-activation-flowchart}

![][image2]

# **APPENDIX D \- Ransomware Flowchart** {#appendix-d---ransomware-flowchart}

# 

# **APPENDIX E \- Citations** {#appendix-e---citations}

1. Leadership and Governance \- BC Ferries \- [https://www.bcferries.com/our-company/leadership](https://www.bcferries.com/our-company/leadership)  
2. Computer Security Incident Handling Guide \- NIST \- [https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)  
3. This template is provided by Cynet \- [https://www.cynet.com/incident-response/incident-response-plan-template/](https://www.cynet.com/incident-response/incident-response-plan-template/)  