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

![][image1]

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
   

[image1]: <data:image/png;base64,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8eLFselR+jnBcePGEfpQGIS+YovVuyL8duhN6ECVROg6dqkClGKW0H8cZdVM6JswYUKNeu0WLVpk3nzzTbN//34zdepUs337drNp0yZz/PhxM2bMGPua5cuXm7Nnz5pjx47Zz1Pomzt3rtm3b5957bXX7M8VrV271uzZs6f2OStXrrSviX7+rl27zPr1623oO336tNm9e/c5X9MXQh/aRegrtli9K8Jvh96UYZ8Zuo527+JPRDGwbFrTTOiLlmeeecZs3brVBsABAwaYOXPm2Oma9/rrrzcPPvigDXYa13wq+jyFvoceesj069fPPqfffXY9fbfddpt54YUXap8X/fxoT5/eX9NOnDjR52v6QuhDuwh9xRard0X47dCb0IEqidB1JPQVGMumNc2EPn+arFmzxj43bdq02DwqO3bssD1ybvko9D322GO252/ZsmV1oU89eR988IENiRJ9r0aHd9Wz19dr+kLoQ7sIfcUWq3dF+O3Qm9CBKonQdST0FRjLpjXNhL4VK1bUee6552yv3axZs8xTTz1lg5ymHzx40IwcOdK+ZuzYsXbolo9C31dffWV763bu3GlX6ksvvdSGOQ2/+eYb84Mf/MDOH/38+fPn25Doh76+XtMXQh/alUfo8/+m/fEgCH11dGqJtnluPPQy8tuhN6EDVRKh60joKzCWTWuShr7eTJo0qXa4VXQuX/T50aNH26HCWXT65MmT7dBdtau6aKhDxeo19D9HRowYEZt2rtf0htCHduUR+np6eszs2bPt4y1btph58+bF5skdoa/O448/bvc/Q4cOteOEvvSEriOhr8BYNq1pN/SVFaEP7coj9ImKerldmFBZvXp13bhOj3DjmSP01VHoGzVqVN3ycMOFCxfmt1z+l98OvQkdqJIIXUdCX4GxbFpD6ANak1fo08VSKurR1gVQp06dsuevfvnll2bKlCn2OV1BP378+NhrM0Hoq+NCnw7zPvHEE3Z5qEd2wYIF9vm3337bnH/++bHXZcVvhzIj9KFXLJvWEPqA1uQV+kTFPdZV6xrOnDnTXHzxxebhhx+247qVkf+6TBD66rjQp8eu3HLLLeb555+303QLK/81WfLbocwIfegVy6Y1IUOfuyI3yc2Z00boQ7tChT53C6QjR47YcYUKlaNHj8ZelwlCXx318OnCNT3Wrwu5ZaULzFR071L/NVny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>