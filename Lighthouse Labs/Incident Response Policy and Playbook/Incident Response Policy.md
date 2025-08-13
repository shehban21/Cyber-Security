

| ![][image1]Incident Response Policy  |
| ----- |

# Table of Contents {#table-of-contents}

[**Incident Response Policy	1**](#incident-response-policy)

[**Table of Contents	2**](#table-of-contents)

[**Executive Summary	3**](#executive-summary)

[**Introduction	4**](#introduction)

[Policy Outlines	4](#policy-outlines)

[**Policy 1 \- Security Awareness Training	4**](#policy-1---security-awareness-training)

[**Policy 2: Data Backup and Encryption	5**](#policy-2:-data-backup-and-encryption)

[**Policy 3: Legal and Regulatory Compliance	6**](#policy-3:-legal-and-regulatory-compliance)

[**Policy Implementation	8**](#policy-implementation)

[**Conclusion	8**](#conclusion)

[**Citations	9**](#citations)

# Executive Summary {#executive-summary}

BC Ferries is one of the largest ferry operators in the world. They move 60000 passengers and 23000 vehicles daily. Their services are essential to the BC Coast population as it provides them with essential transportation and shipping.\[1\] Therefore, securing their systems is paramount to keeping travel disruptions to a minimum.

This report provides a few policy outlines to keep BC Ferries’s network protected from ransomware. These policies provide a few steps to keep in mind when using the playbook for ransomware designed for BC Ferries. The playbook referred in this policy is [BC FERRIES RANSOMWARE INCIDENT PLAYBOOK](https://docs.google.com/document/d/1syQiky0ZWH2G33v_O6cByv6wkjncL7WwidWAoNJFKDc/edit#heading=h.58lnn6b8fa24)\[2\]. 

This report deals with three policies. They are: 

1. Security Awareness Training: This policy outlines steps to provide training for employees to increase their awareness regarding security practices. This can help make the organisation secure by keeping human errors to a minimum.  
2. Data Backup and Encryption: This policy gives some steps to take to protect from ransomware and how to keep data secure even in case an attack happens.  
3. Legal and Regulatory Compliance: This policy provides an overview to keep the BC Ferries system compliant to legal and regulatory requirements.

Implementing these three policies can greatly help in protecting against ransomware and keeping financial and reputational damage to a minimum in case of an attack.

# Introduction {#introduction}

BC Ferries is one of the largest ferry operators in the world. They connect coastal BC and also provide an essential connection to the mainland for the islands on the West Coast. They move 60,000 passengers and 23,000 vehicles everyday.\[1\] They are essential to the everyday lives of BC coast residents and their security is important to prevent unnecessary hardships to the general public.

BC Ferries deals with customer and employee information, ferry maintenance, routes and their schedules and a lot more data that should be kept secure. They also have payment methods and transit pass data that can have catastrophic effects if leaked. Keeping all this data safe is important and there are some cybersecurity measures that can be taken to achieve that.

## Policy Outlines {#policy-outlines}

Policy outlines provide an overview of objectives and goals to achieve the highest cybersecurity standard. It gives an idea about the activities to perform to keep that security. It also delegates the responsibilities to the appropriate employees and gives a timeline of when to do these activities.\[3\]

# Policy 1 \- Security Awareness Training {#policy-1---security-awareness-training}

**Purpose:** The purpose of this policy is to train all employees to have an awareness regarding the best security practices to keep their accounts and the company system secure.\[4\]

**Importance:** Human errors are some of the most likely causes for infiltrations into otherwise secure systems. This policy mandates training for all the employees to ensure that chances of human error are minimum.

**Responsible Parties:** IT Team, All Employees

**Activities and Frequency:**

1. **Test:** A test can prove the knowledge that employees actually have. It can miniaturise the need for education. It can be tested annually and on hiring.  
2. **Education:** There needs to be an education for employees that have little idea about the issue. Education can be spread out over the year on different topics.  
3. **Demonstration:** This demonstration would show all the employees how something is secure or not and also shows them the possible ways to make something more secure. Demonstration can be done together with Education.  
4. **Communication:** The employees should have an easy way to communicate about their lack of knowledge about a topic. This would make them a part of the class that needs to learn about the topic. This can be done anytime.  
5. **Regular Emails:**  Regular weekly emails from the company’s security section can be used to keep employees up to date on safety policies and any new threats.   
   

**Related Playbook:** The playbook for ransomware attack, [BC FERRIES RANSOMWARE INCIDENT PLAYBOOK](https://docs.google.com/document/d/1syQiky0ZWH2G33v_O6cByv6wkjncL7WwidWAoNJFKDc/edit#heading=h.58lnn6b8fa24), can be used to provide the employees with the knowledge about ransomware, what it is, and how to avoid it. It can also provide the employees with the steps of what to do in case they discover a ransomware attack.

**Consequence of Non-Compliance:** 

1. **Individual:** A lack of knowledge regarding safety can cause employee accounts to be compromised.  
2. **Company:** If an employee account is hacked, malicious agents can use it to access sensitive data and exfiltrate it, install malware (including ransomware) or gain more permissions to do more damage.

# Policy 2: Data Backup and Encryption {#policy-2:-data-backup-and-encryption}

**Purpose:** The purpose of this policy is to keep regular backups of important data relating to the company operations. All this data also needs to be encrypted to keep it secure. This data can be invaluable in case of a ransomware attack.\[5\]\[6\]

**Importance:** In case the company has all its important data backed up, any attack on the regular systems can be ignored. The data backup can provide a copy of the original data. This can be invaluable in case of an attack on that data or even failures of the storage devices. What the encryption does is render the data as gibberish to outside parties. This can prevent sensitive data from being released or being held as ransom.\[5\]\[6\]

**Responsible Parties:** IT Team

**Activities and Frequency:**

1. **Backup:** The data needs to be backed up regularly. It can be scheduled to automatically backup daily.\[5\]  
2. **Restore:** In case of an attack or a device hardware failure, data can be restored from the existing backup. Restoring can be done when required.\[5\]  
3. **Encryption:** The data needs to be encrypted before backing up to keep the data secure. Encryption should be required before backing up the data.\[6\]  
4. **Access Control:** The access to this backup data needs to be limited. This can be monitored regularly and audited semi-annually.  
5. **Strong Authentication:** The authentication needed to access this data from backups needs to be strong. Methods like strong passwords and MFA (Multi Factor Authentication) can provide a good basis for the same. This can be monitored regularly.  
   

**Related Playbook:**  The playbook for ransomware attack, [BC FERRIES RANSOMWARE INCIDENT PLAYBOOK](https://docs.google.com/document/d/1syQiky0ZWH2G33v_O6cByv6wkjncL7WwidWAoNJFKDc/edit#heading=h.58lnn6b8fa24), can be used to provide the situations in which data backups are required to safeguard against ransomware attacks. It can also provide the steps that are required before restoring a device due to the ransomware.

**Consequences of Non-Compliance:**

1. **Individual:** The Cyber Security or IT Section employees should be responsible to keep the backups on schedule. Failure to do so can lead to disciplinary action.  
2. **Company:** It can be a big catastrophe for the company in case of a ransomware attack or hardware failure if there is no backup or no encryption for the backup. It can lead to long downtime, leakage of sensitive data and reputation damage for the company.

# Policy 3: Legal and Regulatory Compliance {#policy-3:-legal-and-regulatory-compliance}

**Purpose:** This policy mandates the requirements to achieve legal and regulatory compliance. It also ensures compliance with industry standard practices to protect against ransomware.\[7\]

**Importance:** This policy provides protection against legal and regulatory incidents. The company is required by law to conform to data protection laws such as PIPEDA and HIPAA. 

**Responsible Parties:** Legal Officer, Regulatory Officer

**Activities and Frequency:**

1. **Compliance Audits:** There needs to be regular auditing of compliance to all the applicable laws and regulations. This helps identify the gaps in the compliance and can help with corrective actions. This should be performed annually.  
2. **Incident Reporting:** In case of a ransomware attack, incidents should be reported promptly to the concerned authorities and regulators. Failure to do so can lead to legal repercussions. This needs to be performed within 72 hours of a ransomware incident.  
3. **Third-Party Vendor Contracts:** This is required to mitigate risks associated with third-party vendors to ensure they are legally bound to protect the company data. This needs to be performed every time a third party vendor is signed.  
4. **Data Protection Impact Assessments(DPIA):** This assessment ensures that data handling practices are complying with legal requirements. It also makes sure that appropriate safeguards are in place to protect the data.  
5. **Compliance Documentation:** This is essential as it provides evidence of compliance in the case of an investigation. It also helps the organisation to keep track of its progress.

**Related Playbook:**  The playbook for ransomware attack, [BC FERRIES RANSOMWARE INCIDENT PLAYBOOK](https://docs.google.com/document/d/1syQiky0ZWH2G33v_O6cByv6wkjncL7WwidWAoNJFKDc/edit#heading=h.58lnn6b8fa24), can provide the steps to keep legal and regulatory compliance in case of a ransomware attack.

**Consequences of Non-Compliance:**

1. **Individual:** Doing any actions that can jeopardise the company’s compliance to laws and regulations can lead to disciplinary actions.  
2. **Company:** A lack of compliance to legal and regulatory requirements can lead to lawsuits and a risk of penalties.

# Policy Implementation {#policy-implementation}

These policies provide a basis for a strong protection against ransomware. The playbook, [BC FERRIES RANSOMWARE INCIDENT PLAYBOOK](https://docs.google.com/document/d/1syQiky0ZWH2G33v_O6cByv6wkjncL7WwidWAoNJFKDc/edit#heading=h.58lnn6b8fa24) provides the steps to take to prevent data loss and exploitation. Some steps to take before implementing these policies are:

1. **Presentation:** These policies should be presented to the management before implementing them for the company. Any suggestions should be welcome to improve the compliance of the whole company.  
2. **Approval:** Securing formal approval from senior management can help in implementing the policy. It ensures the policy has the necessary support and authority.  
3. **Legal and Regulatory Review:** The policies, once drafted should be sent to the legal and regulatory compliance officers to make sure there are no compromises in the compliance.  
4. **Investment:** Before implementing any policy, it should be required to calculate the required investment. Failure to do so can lead to unexpected costs and losses.  
5. **Distribution:** The policies, once approved, should be distributed to all the relevant parties, including the employees. There should be clear communication regarding the policy and questions should be answered promptly.

# Conclusion {#conclusion}

BC Ferries is essential to the lives of many in coastal BC. That makes it paramount to keep their service up and running without any unnecessary interruptions. Keeping the company systems secure from malicious parties plays an important part in that. This report gives an outline of the policies to implement to maintain that security. Ransomware is the third-most used cyberattack method and there needs to be company procedures to protect against the same.

# Supporting Documents

* Ransomware Playbook: [BC FERRIES RANSOMWARE INCIDENT PLAYBOOK](https://docs.google.com/document/d/1syQiky0ZWH2G33v_O6cByv6wkjncL7WwidWAoNJFKDc/edit#heading=h.58lnn6b8fa24)  

# Citations {#citations}

1. About Us \- BC Ferries \- [About Us | BC Ferries](https://www.bcferries.com/our-company)  
2. BC Ferries Ransomware Incident Playbook \- Shehban Patel \- [**BC FERRIES RANSOMWARE INCIDENT PLAYBOOK**](https://docs.google.com/document/d/1syQiky0ZWH2G33v_O6cByv6wkjncL7WwidWAoNJFKDc/edit#heading=h.58lnn6b8fa24)  
3. How to write a policy? \- Sweet Process \- Owen McGab Enaohwo \- [How to Write a Policy for Your Business and Employees](https://www.sweetprocess.com/how-to-write-a-policy/#:%7E:text=A%20policy%20is%20simply%20a,is%20your%20organization's%20action%20plan)  
4. MITRE ATT\&CK Mitigations \- User Training \- M1017 \- [User Training, Mitigation M1017 \- Enterprise | MITRE ATT\&CK®](https://attack.mitre.org/mitigations/M1017/)  
5. MITRE ATT\&CK Mitigations \- Data Backup \- M1053 \- [Data Backup, Mitigation M1053 \- Enterprise | MITRE ATT\&CK®](https://attack.mitre.org/mitigations/M1053/)  
6. MITRE ATT\&CK Mitigations \- Encryption \- M1041 \- [Encrypt Sensitive Information, Mitigation M1041 \- Enterprise | MITRE ATT\&CK®](https://attack.mitre.org/mitigations/M1041/)  
7. Cyber Security Legal Compliance \- Anchore \- [Cybersecurity Compliance: Laws & Regulations to Know | Anchore](https://anchore.com/compliance/#:~:text=Cybersecurity%20compliance%20is%20the%20practice,set%20by%20various%20governing%20bodies).
