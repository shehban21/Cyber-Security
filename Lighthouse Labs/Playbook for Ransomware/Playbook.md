# TITLE \-  PLAYBOOK FOR CAT AND BOX {#title---playbook-for-cat-and-box}

# TABLE OF CONTENTS {#table-of-contents}

[**TITLE \-  PLAYBOOK FOR CAT AND BOX	1**](#title---playbook-for-cat-and-box)

[**TABLE OF CONTENTS	2**](#table-of-contents)

[**EXECUTIVE SUMMARY	3**](#executive-summary)

[**PLAYBOOK STEPS	3**](#playbook-steps[4][5])

[1\. Event Detection	3](#event-detection)

[2\. Affected Devices Check	4](#affected-devices-check)

[3\. Backup / Restore	4](#backup-/-restore)

[4\. Reset and Reconfigure	4](#reset-and-reconfigure)

[5\. Incident Report	4](#incident-report)

[6\. Escalate Matter	5](#escalate-matter)

[**WORKFLOW FLOWCHART	5**](#workflow-flowchart[2])

[**LIST OF TRIGGER ITEMS	6**](#list-of-trigger-items)

[● Malware Detection	6](#malware-detection)

[● Phishing bait	6](#phishing-bait)

[● Suspicious applications	6](#suspicious-applications)

[● User Reports	6](#user-reports)

[● Suspicious Network Activities	6](#suspicious-network-activities)

[**TECHNICAL LETTER	8**](#technical-letter)

[**NON TECHNICAL LETTER	9**](#non-technical-letter)

[**CITATIONS	10**](#citations)

# 

# EXECUTIVE SUMMARY {#executive-summary}

This report takes a look at Box, a small manufacturing company, and describes a response playbook that will give the company a set of steps to follow in the case of a ransomware attack.

Ransomware is a type of attack that blocks access to a device’s data and demands a sum of money, i.e., a ransom to reinstate access to that data. If the attackers are sophisticated, that data is encrypted by a key that they claim will be provided once the payment is made.\[1\] Encryption is generally used to keep conversations between two parties confidential and make it inaccessible to outside parties.\[2\] But, it can be used by malicious agents to lock an organisation or individual’s data.\[1\] Though, even if payment is made, there is no guarantee of the data being returned. Almost all payments are made through cryptocurrency which is untraceable.\[3\]

Ransomware can enter the organisation through phishing or social engineering. In this case, a malicious agent poses as a reputable agency like a service provider or bank and lures the target into installing a software, an update or clicking on a link. This can result in a ransomware program entering the organisation.\[1\]

This report will provide steps to recognise and stop an attack like this one with minimal damage.

# 

# PLAYBOOK STEPS\[4\]\[5\] {#playbook-steps[4][5]}

1. ### Event Detection {#event-detection}

   1. If a ransomware attack has happened, it is generally pretty easy to detect as there is a demand for ransom to release the data that is being held captive. On devices that are facing this attack, the whole screen is blocked by a pop up that doesn’t allow access to anything.\[1\] If it is a less sophisticated attack, it might only be a browser pop up that populates the attacked device and panicked users might fall for it.\[6\]  
   2. The first and simplest option is to restart the device when this event is detected. If it was just a pop up from a browser tab or something similar, this can solve this issue. If not, follow the next steps.  
      

2. ### Affected Devices Check {#affected-devices-check}

   1. Once the ransomware attack has been detected, the organisation needs to take stock of the assets it has and what has been affected by the attack. This gives a better understanding of the risks and impact of the attack and can determine the next step to take.  
   2. For determining the risk and impact, the organisation can use the Security Categorization(SC) and Security Impact Level(SIL) by determining which assets are affected and how\[7\].  
   3. The SIL shows how a risk can affect the Confidentiality, Integrity and Availability of an organisation’s data and/or services. The SC uses SIL scores to determine the overall risk to the organisation\[7\].  
   4. If the affected device is of a low-level employee with limited access to important company data, the SC will be low or moderate.  
   5. In that case, the easiest solution is going to Step 4 and following the process from there.   
   6. If the SC is high due to the device belonging to company resources or a high level employee, the next step should be Step 3\. Step 3 can also be used if the SC is low and a backup exists.  
      

3. ### Backup / Restore {#backup-/-restore}

   1. First step in this is to check if a backup exists at all.  
   2. If it does, the device can be wiped to remove all data from it including the ransomware and reconfigured from scratch to get it back to a pre-attack position.  
   3. Once that is done, the next step would be Step 5\.  
   4. If it does not, it is best to take a look at the SC of the asset. If the SC is low, the data on that asset will have minimal impact if it is lost. That means the asset can be wiped and reset and the impact on the organisation will be minimal. That is part of Step 4\.  
   5. If the SC is high, escalate the matter to Tier 2 and follow Step 6\.

4. ### Reset and Reconfigure {#reset-and-reconfigure}

   1. In this step, the asset device is wiped to remove all traces of any data on it, including the ransomware malware.   
   2. Once the device is wiped, it is set up again as a new company device with all the configurations required installed.  
   3. Once this is done, go to Step 5\.  
      

5. ### Incident Report {#incident-report}

   1. After the asset has been cleaned of the ransomware and reconfigured back to company defaults, the last step is to create an Incident Report.  
   2. This report details everything about the incident, including but not limited to, the what, why, where, how and when this incident occurred.  
   3. This can give the organisation an insight into all the factors which caused the incident to occur and how to mitigate for them in the future.  
   4. This is the last step in all cases.  
      

6. ### Escalate Matter {#escalate-matter}

   1. If the asset that has been affected has a Security Categorization of high and no backup exists for it, the matter should be escalated to Tier 2\[2\].  
   2. The administration must decide what to do about the asset that is affected. What can be done to recover it since there is no back up?  
   3. If the asset is irrecoverable, can the asset be replaced and what would be the cost to the organisation?  
   4. How will it affect company operations going forward if important data like employee payroll information, customer information and order information are missing?  
   5. The administration has to decide and move forward with the required steps. This also needs an incident report so it can be avoided in the future.

# WORKFLOW FLOWCHART\[2\] {#workflow-flowchart[2]}

![Imgur](https://imgur.com/eoIbWnF.png)

This flowchart shows the steps described in the previous section, Playbook Steps. 

# LIST OF TRIGGER ITEMS {#list-of-trigger-items}

* ### Malware Detection {#malware-detection}

  * Ransomware programs are malware, programs that mean harm to a device.  
  * Any detection of these by Antivirus or Anti Malware programs is a trigger to investigate further.\[6\]

* ### Phishing bait {#phishing-bait}

  * Ransomware can infiltrate the system by phishing, which is described as a trick to get sensitive information from unsuspecting parties by acting as a reputable organisation.\[6\]  
  * Any bait for that, which can include fishy emails or messages, can be considered as a trigger to prevent the attack from happening in the first place.

* ### Suspicious applications {#suspicious-applications}

  * Random applications found on the system which are not part of the company’s or manufacturer’s configurations can be an indication of a malware.   
  * These applications are sometimes waiting on the system to trigger by escalating permissions from an unsuspecting user.

* ### User Reports {#user-reports}

  * The simplest and generally the most common way for this playbook to be triggered is by users reporting ransomware.   
  * Ransomware is not a sneaky attack. It relies on the victims knowing there has been an attack and a demand for ransom is sent to the victims which is generally quite attention grabbing.

* ### Suspicious Network Activities {#suspicious-network-activities}

  * Some ransomware attacks exfiltrate sensitive data that can be used as a bargaining chip to seek the ransom.  
  * Even if the organisation is okay with losing some of this data, the attackers use it to threaten reputational damage by releasing it to the public to force the ransom to be paid.

# TECHNICAL LETTER {#technical-letter}

To: Cat ([cat@soc.cat](mailto:cat@soc.cat))  
Subject: Ransomware Playbook

Dear Cat,

Hope you’re doing well.

I’m writing this email to give you a brief summary of what work Mr. Percy has given us. He has assigned us the work to monitor the systems and provide you with extended instructions on what to do in case of a breach.

To accomplish this, we have analysed your network and realised it is vulnerable to a ransomware threat. To mitigate it, we have created a playbook for you and provided the same as an attachment.

The playbook has two types of steps:

1. Investigative: These steps are questions that are needed to answer what the scope of the attack is and determine the impact on the company by using the SC and SIL.  
2. Actions: Based on the answers given to the investigative questions, we’ve surmised the steps you and the company should take to be safe from the threat.

Check the attached playbook and let us know if you think there should be any changes and the reasons for them. Your previous work with the company will provide us with valuable insight.

Once approved by you, forward this playbook to the relevant parties on the company network and provide them with our contact in case an escalation is required.

Best Regards,

Shehban Patel  
SOC Analyst  
SOC

# NON TECHNICAL LETTER {#non-technical-letter}

To: Percy  
CC: Misha, Minka

Subject: Monitoring Results

Hello,

Hope this email finds you well.

Thank you for giving us an opportunity to monitor your network. Cat has done a remarkable job keeping the systems secure. We’ve some suggestions after taking a look at your systems and network.

We’ve sent Cat a playbook for approval. A playbook is used by Cyber Security Professionals to deal with a particular threat. It provides them with steps to follow in case of an attack and secure the company with the minimal damage. Once Cat has approved it, she’ll be forwarding the relevant parts to everyone on the company network.

You can contact Cat on 905-4616 during work hours and 902-4321 after hours. If the issue needs escalation, contact Cat whenever needed.

If you have any questions regarding this report, don’t hesitate to reach out.

Best Regards  
Shehban Patel  
SOC Analyst  
SOC

# CITATIONS {#citations}

1. Data Encrypted for Impact \- MITRE ATT\&CK Technique \- T1486 \- [https://attack.mitre.org/techniques/T1486/](https://attack.mitre.org/techniques/T1486/)  
2. What is encryption? \- Google Cloud \- [https://cloud.google.com/learn/what-is-encryption](https://cloud.google.com/learn/what-is-encryption)  
3. A timeline of ransomware \- IBM \- [https://www.ibm.com/topics/ransomware](https://www.ibm.com/topics/ransomware)  
4. Top Security Playbooks 2022 \- Google Cloud \- [https://learningimages.lighthouselabs.ca/Cyber+BC/Cyber+BC+C4/Top\_Security\_Playbooks\_2022.pdf](https://learningimages.lighthouselabs.ca/Cyber+BC/Cyber+BC+C4/Top_Security_Playbooks_2022.pdf)  
5. Federal Government Cybersecurity Incidents and Vulnerability Playbooks \- CISA \- [https://www.cisa.gov/sites/default/files/2024-03/Federal\_Government\_Cybersecurity\_Incident\_and\_Vulnerability\_Response\_Playbooks\_508C.pdf](https://www.cisa.gov/sites/default/files/2024-03/Federal_Government_Cybersecurity_Incident_and_Vulnerability_Response_Playbooks_508C.pdf)  
6. What is Ransomware? \- Fortinet \- [https://www.fortinet.com/resources/cyberglossary/ransomware](https://www.fortinet.com/resources/cyberglossary/ransomware)  
7. Security Categorization Case Study \- Compass \- https://web.compass.lighthouselabs.ca/p/cyber/days/w02d2/activities/2835  
