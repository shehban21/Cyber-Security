# 

# 

# RISK MANAGEMENT CASE STUDY {#risk-management-case-study}

# TABLE OF CONTENTS {#table-of-contents}

[**RISK MANAGEMENT CASE STUDY	1**](#risk-management-case-study)

[**TABLE OF CONTENTS	2**](#table-of-contents)

[**EXECUTIVE SUMMARY	3**](#executive-summary)

[**PURPOSE, SCOPE AND USERS	4**](#purpose,-scope-and-users)

[PURPOSE	4](#purpose)

[SCOPE	4](#scope)

[USERS	4](#users)

[**RISK ASSESSMENT AND RISK TREATMENT METHODOLOGY	5**](#risk-assessment-and-risk-treatment-methodology)

[● RISK ASSESSMENT	5](#risk-assessment)

[○ The Process	5](#the-process)

[● Assets, Vulnerabilities and Threats	6](#assets,-vulnerabilities-and-threats)

[○ Assets	6](#assets)

[○ Vulnerabilities	6](#vulnerabilities)

[○ Threats	7](#threats)

[● Determining Risk Owners	8](#determining-risk-owners)

[● Impact and Likelihood	8](#impact-and-likelihood)

[● Risk Acceptance	9](#risk-acceptance)

[● Risk Treatment	10](#risk-treatment)

[CONCLUSION	12](#conclusion)

[Appendices	13](#appendices)

[Appendix A \- Risk Assessment Table	13](#appendix-a---risk-assessment-table)

[Appendix B \- Risk Treatment Table	14](#appendix-b---risk-treatment-table)

[SOA \- Statement of Applicability	15](#soa---statement-of-applicability)

# EXECUTIVE SUMMARY {#executive-summary}

DHAEI is a software development company with a main office in Oshawa, Ontario and several branch offices. The company uses Rackspace and AWS to provide web hosting services to small office / home office individuals and organisations. There is a new branch opening in Brampton, Mississauga to handle more of their clients.\[1\]

Currently, all the branch offices have their own servers that contain the data for that branch with no cross-location access. The new branch will use the company’s file server, FS1, located at the main office while the server at the branch office is being set up. The programmers use L2TP VPNs to work remotely. \[1\]

This report provides the risk management strategy for DHAEI to protect against some threats and vulnerabilities detected by our analysis of the company’s assets and the changes to be implemented to the company’s infrastructure. The process involves Risk Assessment, a process which provides the overall impact a risk can have on the organisation.

There’s also a section included for Risk Treatment, a process which is used to provide industry standard mitigations to protect from threats detected in the assessment. The tables on Risk Assessment and Risk Treatment summarise the detailed information in this report into simplified tables, providing a quick overview of all the key details.

# 

# PURPOSE, SCOPE AND USERS {#purpose,-scope-and-users}

## PURPOSE {#purpose}

Risk means a “possibility of loss”.\[2\] In terms of Cyber Security, risks can refer to an organisation’s assets and any threats or vulnerabilities that might cause damage to the same. A risk for an organisation depends on the assets it has and the potential impact of damage to a particular asset on the entire organisation.\[3\] The purpose of a risk management plan is to identify the risks an organisation might face and mitigate them. The higher the likelihood of a risk and the greater the potential damage, the higher its priority.

## SCOPE {#scope}

The scope for this risk management plan is the main office and the new branch office in Brampton, Mississauga. The main office file server is handling the branch files until the new branch gets a server installed. And the branch office in Brampton is going to take over later. The other branches are not involved in this process as the company structure doesn’t allow inter-branch data sharing.\[1\] 

It also includes any remote workers that would work for the Brampton branch office. And due to this involvement of remote workers and the company policy of using VPN to work remotely, this risk management plan must include the VPN in its scope.\[1\]

## USERS {#users}

The users of this document are all the employees that will work at the new Brampton Branch Office and the main office. It also includes all the C Suite management which includes the CEO, Alan Hake, the CIO Amanda Wilson and the CISO Paul Alexander.\[1\]

# RISK ASSESSMENT AND RISK TREATMENT METHODOLOGY {#risk-assessment-and-risk-treatment-methodology}

* ## RISK ASSESSMENT {#risk-assessment}

  * ### The Process {#the-process}

  * The process for risk assessment starts with identifying the assets of the company and the threats and vulnerabilities faced by each of these assets. The impact an attack on the asset would have on the company as a whole also determines the severity of the risk.\[4\] The risk assessment process is done in a few steps:  
    * The whole process is coordinated by the information security analyst.\[4\]  
    * The asset owners identify the threats and vulnerabilities of the asset they own.\[4\]  
    * The risk owners assess the consequences and the likelihood of a risk on the asset.\[4\]

## 

  ## 

* ## Assets, Vulnerabilities and Threats {#assets,-vulnerabilities-and-threats}

  * ### Assets {#assets}

  * The first step in the risk assessment process is to identify all the assets which may affect the CIA(Confidentiality, Integrity and Availability) of information at the company. For DHAEI’s risk assessment for the new branch, the assets identified are the following\[1\]:  
    * Domain controllers: DC1 and DC2  
    * File Server: FS1  
    * Windows Update Server: WSUS1  
    * DNS Service Provider: DHADNS  
    * Brampton Branch Office RODC  
    * L2TP VPN  
    * Laptops / Desktops used by employees  
    * Network  
  * The owners of these assets are as follows:  
    * All the big assets like the domain controllers and all the servers would come under the ownership of the following\[1\]:  
      * Alan Hake, CEO  
      * Amanda Wilson, CIO  
      * William Freund, Systems Manager  
      * Jonathan Jasper, Senior Systems Admin  
      * Sy Truman, Systems Admin  
    * The Network and the VPN would come under the ownership of the following\[1\]:  
      * Alan Hake, CEO  
      * Amanda Wilson, CIO  
      * William Freund, Systems Manager  
      * Tina Mann, Senior Network Administrator  
      * Okelula M’buta, Network Administrator  
    * The laptops and desktops used by the employees are considered the property of the employee working on them\[1\].

  * ## Vulnerabilities {#vulnerabilities}

  * Some vulnerabilities associated with these assets are:  
    * A design flaw in RODCs can allow privileged data like passwords to be exposed to all privileged users. (CVE-2023-4154)\[5\]  
    * A Denial of Service Attack on the DNS server can disrupt the company infrastructure and make it unavailable\[6\].  
    * Some L2TP VPNs can be used by malicious agents to generate amplification / reflection traffic. (CVE-2024-38520\[7\])  
    * Equipment malfunction of the File Server can disrupt the whole company network.

    ## 

  * ## Threats {#threats}

  * Threats are ways a vulnerability can be exploited to cause harm to the organisation. For DHAEI, we have shortlisted the biggest threats:  
    * DDoS : A broad Distributed Denial of Service attack on the DNS or File Server can stop all operations of the company. The biggest challenge regarding this threat would be the detection and prevention of the attack\[6\].  
    * Insider Threats: An employee can cause harm to the company network by negligence or using their privileged access for malicious purposes. The challenge for this threat would be to keep privileges in check and monitoring user activity to identify suspicious behaviour\[8\]  
    * Data Exfiltration: Any leak of the data, by a breach or stealing of physical drives, can cause irreparable harm to the company’s reputation and also cause harm to the company’s clients. The challenge for this threat would be keeping systems up to date and monitoring systems properly with the proper thresholds\[9\].  
  * The individuals that are needed to be involved in this risk assessment process are:  
    * Alan Hake, CEO \- As the CEO, all the major executive decisions are to be made or approved by Alan\[1\]  
    * Amanda Wilson, CIO \- The company places high value on the information stores on its servers, so including the Chief Information Officer is a must.\[1\]  
    * Paul Alexander, CISO \- Same as the CIO, the Chief Information Security Officer should also be present when making important decisions about the company handling of the information\[1\]  
    * William Freund, Systems Manager \- In order to make sure the systems and network are maintained properly and are secure, the involvement of the Systems Manager is necessary.\[1\]

  ## 

* ## Determining Risk Owners {#determining-risk-owners}

  * The chain of ownership for risks in the organisation would be as follows:  
    * **Ground Level**: Security Technicians \- The first personnel to provide support to the users.   
    * **Mid Level**: Network and Systems Administrators \- The senior administrators can enforce security policies and monitor for inconsistencies.  
    * **Senior Level**: Paul Alexander, CISO and Amanda Wilson, CIO, will set the security objectives for the organisation and determine the policies.

* ## Impact and Likelihood {#impact-and-likelihood}

  * The impact score determines the damage a threat can have if faced by an organisation. Here, we use a scale of 0 to 10 to determine the impact of a threat.  
  * The likelihood is the possibility of that threat emerging as an attack. The scale of likelihood we use here ranges from 0 to 5 with 0 being negligible to 5 representing high chances.

| Threat | Impact | Likelihood | Details |
| :---- | :---- | :---- | :---- |
| DDoS | Confidentiality: 2 Integrity: 3 Availability: 10 Overall: 5 | 4 | A Distributed Denial of Service attack can cause a complete disruption to the company’s network which can also affect the users\[6\] |
| Insider Threat | Confidentiality: 8 Integrity: 9 Availability: 4 Overall: 7 | 2 | An insider can leak the data and even modify it which can affect the data’s integrity\[8\].  |
| Data Exfiltration | Confidentiality: 10 Integrity: 10 Availability: 7 Overall: 9 | 3 | This can happen via a breach by a malicious agent or an insider threat. It can have a big impact on the company’s reputation if exposed\[9\]. |

  ## 

* ## Risk Acceptance {#risk-acceptance}

  * The highest risk is faced from the threat of Data Exfiltration, which makes it a priority for the organisation to mitigate.  
  * The other risks, Insider Threat and DDoS, are both medium level threats which also need mitigation but with lower priority.

* ## Risk Treatment {#risk-treatment}

* Risk treatment is needed to minimise the impact of any risk on the organisation. There are a few methods that can be used to treat the most prioritised risks\[4\]:  
  * Selecting controls to keep the risk in check  
  * Transferring the risks to third party ( Insurance or Security Contractors )  
  * Avoiding the risk by stopping the activity which causes such risk  
  * Accepting the risk which would be acceptable if the cost of mitigation is higher than the impact  
* The controls DHAEI should implement to keep the risks in check are:  
  * DDoS  
    * Summary : A distributed denial of service attack can cause extensive disruptions to the company network by denying access to users and employees by directing massive traffic to the company servers. This can be done by redirecting unsuspecting victims or using bots (programmed devices) to simulate the traffic\[6\].  
    * Recommended Mitigations\[10\]:  
      * Detection: A denial of service attack can be hard to determine from legitimate traffic and taking measures to detect it can help an organisation to prevent this threat.  
      * Routing: Routing detected bot IPs from the server to elsewhere can reduce traffic and help in mitigating this attack.  
      * Response: Banning repeat offender’s IP Addresses can help in preventing this issue from happening in the future.  
      * DDoS Mitigation Service: Instead of spending company resources in mitigating this threat, it can be outsourced to specific service providers who can provide a more specialised approach to solving this issue.  
    * Priority: High  
  * Insider Threat  
    * Summary: Insider threat can refer to risks caused by an organisation’s employees, third-party contractors and business affiliates. These risks can be malicious or negligent. A malicious insider threat can cause big problems for an organisation as they would have privileged access to the company’s information and can leak sensitive information\[8\].  
    * Recommended Mitigations:  
      * Access Management: Access Management technologies can be used to implement authorization policies to support user identification and authorization\[11\].  
      * Authorization Enforcement: Role Based Access Control schemes can help better control privileges to read, write and execute on a company system\[12\].  
      * Multi Factor Authentication: This can prevent employee negligence like weak passwords from causing issues as it would require more than one factor to authenticate a user\[13\].  
    * Priority: Medium  
        
  * Data Exfiltration  
    * Summary: Data exfiltration refers to data being sent outside the company network without the organisation’s knowledge or permission. This can cause leakage of sensitive data which can cause great impact on the Confidentiality and Integrity of data\[9\].  
    * Recommended Mitigations:  
      * Encryption: Encrypted data is gibberish without having the key to decrypt it. This can prevent data exfiltration’s major issues as the data accessed by malicious parties would be unreadable.  
      * Data Loss Prevention (DLP): DLP technologies can  be used to identify malicious activity to access the sensitive data of an organisation. Extra controls on firewalls, physical ports like USB and the like can be used to prevent exfiltration of data.  
      * Network Segmentation: Separating devices with sensitive data to their own network and monitoring connections between that network and the wider internet can prevent important data from leaking.  
    * Priority: MediuM

## CONCLUSION {#conclusion}

The risk management report for DHAEI provides the organisation with an overview of their assets, the risks, vulnerabilities and threats associated with them and ways to mitigate them. The assets most important to the organisation are the ones that handle the sensitive client information and protecting them is of the highest priority for the organisation.

The new branch office in Brampton has to follow the company security policies and maintain employee training to prevent some of these risks. The initial phase requires the use of the server in the main office and proper care should be taken by the monitoring teams to ensure the safety and integrity of data. Once the data has been moved to the branch office server, the security policies should continue to be implemented and negligence in that duty can cause problems for the organisation.

The mitigations provided by reputable sources such as MITRE ATT\&CK, NIST NVD and ISO 27001 can be used across the organisation to minimise the risks by a considerable degree. This risk assessment process should be repeated regularly to keep up with emerging threats and audit the mitigations. 

## Appendices {#appendices}

### Appendix A \- Risk Assessment Table {#appendix-a---risk-assessment-table}

| ID \# | Asset Name | Asset Owner | Threat | Vulnerability | Impact (0-10) | Likelihood (0-5) | Risk (I+L) | Notes |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | Laptop / Desktop | Employee | Breach | Weak Password | 7 | 3 | 10 | Can be prevented by mandating complex passwords |
| 2 | DC1 and DC2 (Domain Controller Servers) | Systems Admin | DDoS | Inadequate DDoS protection | 5 | 3 | 8 | Can be prevented by using DDoS prevention systems |
| 3 | FS1 (File Server) | Systems Admin | Data Leak | Weak Access Control | 9 | 4 | 12 | Can be prevented by managing data access |
| 4 | DHADNS (DNS Server) | Systems Admin | DDoS | Inadequate DDoS protection | 5 | 3 | 8 |  |
| 5 | Network | Network Admin | Man in the Middle | Lack of Encryption | 6 | 2 | 8 | Can be prevented by implementing encryption |
| 6 | L2TP VPN | Network Admin | VPN host traffic redirection | Can use VPN network hosts to redirect traffic | 3 | 2 | 5 | Can be prevented by updating the VPN softwares |

### Appendix B \- Risk Treatment Table {#appendix-b---risk-treatment-table}

| ID \# | Computed Value of Risk | Proposed Risk Response | Description of the Proposed Response | Estimated Cost | Implementation Priority (1-3) | Planned Start | Review Date | Planned Closure |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | 1 Million CAD | MFA (Multi Factor Authentication) | Require a second factor besides a password to log in | 100,000 CAD | 2 | 1 August | 1 October | 1 December |
| 2 | 500,000 CAD | DDoS Mitigation Service | A third party service provider to stop DDoS attacks | 250,000 CAD | 3 | NA | NA | NA |
| 3 | 10 Million CAD | Role-Based Access Control | Distributing Access depending on the roles | 500,000 CAD | 1 | 1 August | 1 September | 1 October |
| 4 | 500,000 CAD | DDoS Mitigation Service | A third party service provider to stop DDoS attacks | 250,000 CAD | 3 | NA | NA | NA |
| 5 | 2 Million CAD | Encryption | Encrypting data saved on the company network to make it gibberish in case of leak | 250,000 CAD | 2 | 1 August | 1 October | 1 December |
| 6 | 100,000 CAD | Update of VPN Systems |  | 10,000 CAD | 3 | NA | NA | NA |

### SOA \- Statement of Applicability {#soa---statement-of-applicability}

The statement of applicability provides the controls implemented by DHAEI according to the ISO 27001 standard. These controls provide the guidelines for DHAEI to implement the recommended mitigations according to the ISO 27001 standard. 

| Control Number | Control Objective | Control Description |
| :---- | :---- | :---- |
| A.5.1 | Information Security Policies | The security policies to keep company information secure |
| A.6.1 | Internal organisation | How the organisation deals with information security inside the organisation |
| A.7.2 | During Employment | Policies applicable while employed |
| A.7.3 | Termination and change of employment | Policies applicable after employment has ended |
| A.8.1 | Responsibility for assets | Asset owners and risk owners categorization |
| A.9.4 | System and application access control | Setting access controls to prevent unauthorised access |
| A.10.1 | Cryptographic controls | Encryption specifications |
| A.12.1 | Operational procedures and responsibilities | Any updates to the organisation management and the documentation of operating procedures |

## CITATIONS

1. Risk Management Case Study \- Compass \- [https://web.compass.lighthouselabs.ca/p/cyber/projects/risk-management?day\_number=w05d2](https://web.compass.lighthouselabs.ca/p/cyber/projects/risk-management?day_number=w05d2)  
2. Risk \- Merriam Webster Dictionary \- [https://www.merriam-webster.com/dictionary/risk\#:\~:text=Synonyms%20of%20risk-,1,3](https://www.merriam-webster.com/dictionary/risk#:~:text=Synonyms%20of%20risk-,1,3)  
3. Cybersecurity Risk \- NIST Glossary \- [https://csrc.nist.gov/glossary/term/cybersecurity\_risk\#:\~:text=Cybersecurity%20risks%20relate%20to%20the,individuals%2C%20other%20organizations%2C%20and%20the](https://csrc.nist.gov/glossary/term/cybersecurity_risk#:~:text=Cybersecurity%20risks%20relate%20to%20the,individuals%2C%20other%20organizations%2C%20and%20the)  
4. Sample Risk Management Plan \- Lighthouse Labs \- [https://learningimages.lighthouselabs.ca/Cyber+BC/Cyber+BC+C5/Cyber+BC+C5.2/Sample+Risk+Management+Plan.pdf](https://learningimages.lighthouselabs.ca/Cyber+BC/Cyber+BC+C5/Cyber+BC+C5.2/Sample+Risk+Management+Plan.pdf)  
5. CVE-2023-4154 \- CVE NVD \- [https://nvd.nist.gov/vuln/detail/CVE-2023-4154](https://nvd.nist.gov/vuln/detail/CVE-2023-4154)  
6. Botnet \- MITRE Attack Technique  \- T1583.005 \- [https://attack.mitre.org/techniques/T1583/005/](https://attack.mitre.org/techniques/T1583/005/)  
7. CVE-2024-38520 \- CVE NVD \- [https://nvd.nist.gov/vuln/detail/CVE-2024-38520](https://nvd.nist.gov/vuln/detail/CVE-2024-38520)  
8. Defining Insider Threats \- CISA \- [https://www.cisa.gov/topics/physical-security/insider-threat-mitigation/defining-insider-threats](https://www.cisa.gov/topics/physical-security/insider-threat-mitigation/defining-insider-threats)  
9. Data Exfiltration \- Fortinet \- [https://www.fortinet.com/resources/cyberglossary/data-exfiltration\#:\~:text=Data%20exfiltration%20typically%20involves%20a,any%20data%20from%20a%20device](https://www.fortinet.com/resources/cyberglossary/data-exfiltration#:~:text=Data%20exfiltration%20typically%20involves%20a,any%20data%20from%20a%20device).  
10. DDoS Mitigation \- Cloudflare \- [https://www.cloudflare.com/learning/ddos/ddos-mitigation/\#:\~:text=DDoS%20mitigation%20refers%20to%20the,%2Dservice%20(DDoS)%20attack](https://www.cloudflare.com/learning/ddos/ddos-mitigation/#:~:text=DDoS%20mitigation%20refers%20to%20the,%2Dservice%20\(DDoS\)%20attack).  
11. Access Management \- MITRE Mitigation M0801 \- [https://attack.mitre.org/mitigations/M0801/](https://attack.mitre.org/mitigations/M0801/)  
12. Authorization Enforcement \- MITRE Mitigation M0800 \- [https://attack.mitre.org/mitigations/M0800/](https://attack.mitre.org/mitigations/M0800/)  
13. Multi-factor Assessment \- MITRE Mitigation M1032 \- [https://attack.mitre.org/mitigations/M1032/](https://attack.mitre.org/mitigations/M1032/)  
14. Encrypt Sensitive Information \- MITRE Mitigation M1041 \- [https://attack.mitre.org/mitigations/M1041/](https://attack.mitre.org/mitigations/M1041/)  
15. Data Loss Prevention (DLP) \- MITRE Mitigation M1057 \- [https://attack.mitre.org/mitigations/M1057/](https://attack.mitre.org/mitigations/M1057/)  
16. Network Segmentation \- MITRE Mitigation M1030 \- [https://attack.mitre.org/mitigations/M1030/](https://attack.mitre.org/mitigations/M1030/)