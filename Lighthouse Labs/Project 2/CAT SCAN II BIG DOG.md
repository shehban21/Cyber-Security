

# Title: {#title:}

CAT SCAN II BIG DOG

# TABLE OF CONTENTS {#table-of-contents}

[**Title:	1**](#title:)

[**TABLE OF CONTENTS	2**](#table-of-contents)

[**EXECUTIVE SUMMARY	2**](#executive-summary)

[**RISKS AND VULNERABILITIES	3**](#risks-and-vulnerabilities)

[**SC and SIL Scores\[12\]	8**](#sc-and-sil-scores[12])

[**Prioritization by Importance	9**](#prioritization-by-importance)

[**TABLE OF SENSORS	10**](#table-of-sensors)

[**DISCUSSION OF SENSORS	13**](#discussion-of-sensors)

[**RECOMMENDATIONS:	16**](#recommendations:)

[**Citations:	17**](#citations:)

# 

# EXECUTIVE SUMMARY {#executive-summary}

This report takes a look at the company, Big Dog, and identifies the most valuable assets to it and how to best monitor them. All the assets are sorted by their priority to the company. We have taken a look at the Security Categorization of each asset which is calculated by looking at the impact an asset would have if compromised to the company’s Confidentiality, Integrity and Availability. The higher the impact, the higher the priority should be to keep that asset secure.

PRTG Monitor is a service used to monitor systems and it uses various sensors to monitor various aspects of a system. These sensors can give a baseline of regular operations which can be used as a guide to set up threshold monitors that can alert the company’s administrators to security and performance issues.

After taking a look at the risks and vulnerabilities faced by each asset, we take a look at the sensors we’ll use that cater the best to Big Dog’s infrastructure. We have also included a discussion of why these sensors have been used and what information they provide. Lastly, we have some more recommendations we’d like to make to Big Dog to increase their safety to industry standards.

# RISKS AND VULNERABILITIES {#risks-and-vulnerabilities}

The company, Big Dog, has a lot of valuable assets. 

For all these assets, there’ll be a table at the end of this section listing their Security Categorizations based on the Security Impact Level for each asset and their Confidentiality, Integrity and Availability. Any new terms will be explained in the following part of the report.

Let’s first take a look at all the assets they have and what vulnerabilities they face:

1. Windows Server \- This device is the most important part of the overall company infrastructure. It holds the Web Server that runs the company’s main systems. It also holds the SQL Database that has all the data relating to the company saved on it. This includes client, employee, sales and management data. It’s also where the monitoring system for the company, PAESSLER PRTG, is installed to keep an eye on the company’s assets.  
     
   So, the assets on the Windows Server can be listed as follows:  
1. SQL Database  
2. IIS Server  
3. PRTG Network Monitor

	  
	Let’s take a look at the vulnerabilities these assets face:  
	

1. SQL Database  
   1. Vulnerabilities:  
      1. SQL Injection \- This vulnerability can allow a malicious party to interfere with the queries that communicate between the website and the database.\[1\]  
      2. Unauthorized access \- Malicious agents can use phishing techniques or brute     force weak passwords to gain unauthorized access to privileged data  
      3. Privilege escalation \- Status of a user could be changed from user to administrator, which can be used by malicious agents\[2\]  
   2. Risks associated with this asset are:  
      1. Compromise of confidential data \- Confidential client and employee data can be made available publicly by anyone who can gain access to this database  
      2. Denial of Service \- By making the database unavailable, the malicious agents can affect the availability of the company systems

2. IIS Server  
   1. Vulnerabilities:  
      1. Cross Site Scripting (XSS) \- Malicious links are added to usually trusted websites and used for phishing.\[3\] (CVE-2023-51630)\[6\]  
      2. Buffer Overflow \- Buffers are temporary storage for data that is being transferred between two locations. They can be exploited by malicious agents to corrupt data on the server by overflowing the buffer with data\[4\]  
      3. Directory Traversal attacks \- Malicious agents can use the file directory system to gain access to files that should not be available to a user by using “../” to reference the file system.\[5\]  
   2. Risks:  
      1. Website Tampering \- With access to the web server, malicious agents can make unauthorized changes to the website and make it unusable or steal data from users  
      2. Data Leakage \- A lot of privileged data can be leaked by gaining access to this server

   

3. PRTG Network Monitor  
   1. Vulnerabilities:  
      1. Default credentials \- Using default credentials can allow unauthorized access to the company’s monitoring system  
      2. Insider threats \- Internal rogue elements can access this system and provide dangerous information to malicious agents  
      3. Cross site scripting \- A vulnerability in some older versions of PRTG allows a malicious agent to run an arbitrary script by getting an authenticated user to click on a link (CVE-2023-51630)\[6\]  
   2. Risks:  
      1. Disruption in Monitoring \- Malicious agents can cause problems with monitoring the company network by affecting it’s availability  
      2. Data Compromise \- Data relating to the local systems can be used by malicious agents to make further attacks.

   

   

   

   

   

   

   

   

   

2\. Linux Development Environment

Vulnerabilities:

Development tool exploits \- Vulnerabilities in the various development tools used by the company can be exploited to gain unauthorized access and leak data

Code injection \- Input elements of an application can be used to inject executable code onto a device\[7\]

Risks:

These vulnerabilities can result in loss of sensitive customer information and disruption in company operations

3\. Windows Workstations

There are three departments using Windows Workstations, Sales, Marketing and Management. Let’s take a look at the vulnerabilities and risks of each:

1. Sales  
   1. Vulnerabilities:  
      1. Phishing attacks \- Emails and social chats can be used to gain credentials from unsuspecting employees\[8\]  
      2. Malware \- Malicious agents can use an authenticated user to install malware that can be used to monitor and leak data\[9\]  
   2. Risks:  
      1. Customer data compromised \- Customer information, including private data like addresses and payment methods can be leaked by malicious entities  
      2. Sales Unavailability \- Loss of accounts to malicious activities can cause disruption in service  
2. Marketing:  
   1. Vulnerabilities:  
      1. Social engineering attacks \- Malicious agents can use tactics to talk authorized parties into revealing sensitive information\[10\]  
      2. Malware  
      3. Data Leakage

   2. Risks:  
      1. Reputation damage \- Damage to company’s reputation can have adverse effects for sales and would need more marketing to counter as well  
      2. Marketing data leaks \- Malicious agents can leak data related to future marketing that could reduce its effectiveness  
3. Management  
   1. Vulnerabilities:  
      1. Unauthorized access  
      2. Data Leakage  
      3. Spear phishing \- A specifically targeted phishing attack that generally targets employees in administrator positions\[11\]

4\. Kali Linux Systems

1. Vulnerabilities:  
   1. Testing tools \- Misuse of testing tools used to find vulnerabilities can cause issues like complacency during the test and false negatives that can allow a malicious party entry into the system  
   2. Insider threats  
2. Risks:  
   1. Internal system attacks \- With access to the IT systems management done by the Kali Linux systems, malicious agents can use them to attack and disrupt internal company systems

# SC and SIL Scores\[12\] {#sc-and-sil-scores[12]}

|              Impact Asset | Confidentiality | Integrity | Availability | Overall |
| :---- | :---- | :---- | :---- | :---- |
| SQL Database | High | High | High | High |
| IIS Web Server | High | Moderate | High | High |
| Linux IDE | High | High | Moderate | High |
| PRTG Network Monitor | High | High | Moderate | High |
| Sales | High | Moderate | High | High |
| Marketing | Moderate | Moderate | Moderate | Moderate |
| Management | High | High | High | High |
| Kali Test Systems | High | High | Moderate | High |
| Kali IT Management | High | High | High | High |

# Prioritization by Importance {#prioritization-by-importance}

1. SQL Database  
2. IIS Web Server  
3. Linux IDE  
4. Sales  
5. Management  
6. Kali IT Management  
7. PRTG Network Monitor  
8. Kali Test Systems  
9. Marketing

These are all the assets prioritized by the risks associated with them and their importance to the company.

# TABLE OF SENSORS {#table-of-sensors}

| Sensor | Description | System | IoCs | Rationale | Priority | Thresholds / Assumptions |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| HTTP Load Time\[13\] | Monitors the time it takes for a page to load | Linux | May be used to indicate malicious redirects, DDoS Attacks or Content Injection | Unexpected changes in load time can indicate anomalies or performance related issues that could be indicative of a security breach or compromise | Medium | Changes of 20% over the average load. SIL base on the fact that BIG DOG does not have a large Web presence, the linux server being internal and this one outward facing(Assumption) There is relatively low impact on CIA (Specifically A) but a higher chance of compromise I have assigned as high |
| MySQL v2\[14\] | Monitors the execution time and affected rows from queries | Linux | To check for SQL injection threats or for DDoS attacks | Changes is the results can indicate SQL injection affecting queries or load times of replies might indicate DDoS risk | High | Changes of more than 500ms in query execution time. Delays like that can cause a cascading effect on loading times for the whole system(Assumption)Impact of a breach would be on all 3 aspects of the CIA triad. |
| SSH Load Average\[15\] | Average load on a Linux / Unix system | Linux | Can be used to monitor DDoS attacks or data leakage | Sudden spikes in load average can indicate a security breach and data leak | Medium | An increase of 25% over the average load. Big Dog does not operate on big files, so a sudden rise of data transfer load can indicate leaks or tampering of data that affects Confidentiality and Integrity |
| SSH MemInfo \[16\] | Indicates memory usage of a Linux/Unix system | Linux | Can be used to monitor for Buffer overflow or Dos attacks | Random increase in the use of memory of the system can indicate external input | Medium | A 50% or more drop in memory availability from the baseline can indicate external influence on the system (Assumption). This can affect the availability mostly |
| WMI Security Center Sensor\[17\] | Monitors all the security products that are controlled by Windows Security Center | Windows | Can indicate disabled security | Having a down status can indicate compromised security on the device | Medium | This sensor just has a status. If it is in a warning status, it can indicate out of date security and the Down status indicates a not running security system |
| SFTP Secure File Transfer Protocol\[18\] | Monitors the FTP servers of a Linux system via the FTP over SSH | Linux | May be used to indicate data leakage or DoS | Very high response times can indicate data transfer happening elsewhere or the server being hit by Denial of Service | High | A consistent 50% or more rise in the response time can indicate an issue. This can affect all three elements from the CIA triad |
| Windows Event Log\[19\] | Monitors the event log entries via the Windows API | Windows 11 | May be used to indicate data breach or brute force attacks | A sudden rise in the event log entries may indicate malicious agents trying to breach a system | Medium | A 25% rise in the events can indicate a breach attempt on a device.  |
| SNMP Traffic\[20\] | Monitors Traffic on a device via the SNMP protocol | Linux, Windows | Can indicate data leakage Denial of Service | A rise in Traffic Out channel past the baseline can indicate a breach and a random increase in Traffic In channel may indicate Denial of Service | High | A 30% rise in Traffic Out or a 50% increase in Traffic In could indicate security lapses. This can affect all three aspects of Confidentiality, Integrity and Availability |
| Windows Network Card Sensor\[21\] | Monitors bandwidth usage and traffic of a network interface | Windows | Can indicate data leakage Denial of Service | A rise in Traffic Out channel past the baseline can indicate a breach and a random increase in Traffic In channel may indicate Denial of Service. This sensor has more detailed channels that are specifically for a Windows device | High | A 30% rise in Traffic Out or a 50% increase in Traffic In could indicate security lapses. This can affect all three aspects of Confidentiality, Integrity and Availability.  |

# DISCUSSION OF SENSORS {#discussion-of-sensors}

The first thing we need to do after setting any of these sensors is identify the baseline. The baseline gives us a standard we can use to set thresholds that can indicate suspicious activities on our system. Let’s take a look at all the sensors:

1. HTTP Load Time: This sensor monitors how long a page takes to load completely. The security breach can be a Denial of Service(DoS) attack that can cripple a system. \[13\]  
   1. IoCs:   
      1. Slower than usual load times can indicate resources being used by malicious agents  
      2. Random traffic increase from a lot of different IP addresses can indicate a DoS attack  
   2. Thresholds: Changes of 20% over the average load can indicate malicious activity as Big Dog does not have a large online presence.  
2. MySQL v2: This sensor can monitor the affected rows, downtime, execution time, and query execution time. \[14\]  
   1. IoCs:  
      1. Slower than usual load times can indicate resources being used by malicious agents  
      2. Large amounts of traffic that is outgoing can indicate a data exfiltration attack  
   2. Thresholds: Changes of more than 500 ms in the query execution time can indicate resources being used elsewhere by malicious agents to access or exfiltrate data.  
3. SSH Load Average: This sensor monitors the average load on a Linux system. SSH is Secure Shell, which is used to send secure commands over an unprotected network. This sensor shows the average load the system has in a 1 minute, 5 minute or 15 minute interval.\[15\]  
   1. IoCs:  
      1. A random increase in load could mean a data breach, a brute force attack or a DoS attack.  
   2. Thresholds: The Linux systems are used for development by Big Dog, so an increase of 25% would be a big enough spike to cause suspicion.  
4. SSH MemInfo: This sensor also uses SSH and is used to monitor the memory usage of the Linux system. \[16\]  
   1. IoCs:   
      1. A sudden drop in the Available Memory might indicate malicious agents using system resources  
   2. Thresholds: A drop of 50% or more in memory availability is a plausible threshold.   
5. WMI Security Center Sensor: This sensor monitors all the security products that are controlled by the Windows Security Center or Windows Action Center. It indicates the status of the security products with 3 status codes. Up status code means it is running properly. Warning status code indicates it is running but has outdated data. And the last status code, Down, indicates the product is not running. \[17\]  
   1. IoCs:  
      1. A down status code might indicate external malicious agents that might have turned off the security to install malware  
   2. Thresholds: This only needs a status threshold that indicates if it is running or not.  
6. SFTP Secure File Transfer Protocol: This sensor monitors the FTP servers of a Linux system. The only channel usable to set a threshold on this sensor is the response time. \[18\]  
   1. IoCs:  
      1. A sudden spike in response time can indicate data exfiltration or a DoS attack.  
   2. Thresholds: A consistent 50% or more rise on this response time can indicate an issue.   
7. Windows Event Log: This sensor monitors the number of events being logged on a Windows system by using the Windows API. \[19\]  
   1. IoCs:  
      1. A spike in the number of events being logged could indicate a brute force attack trying to break into a system  
   2. Thresholds: A 25% rise is the events being logged could indicate a breach attempt on a device  
8. SNMP Traffic: This sensor is used to monitor traffic going out and coming into a Windows and Linux device. This sensor can be used to monitor the Linux Development devices and the Windows workstations used by the employees. \[20\]  
   1. IoCs:  
      1. A sudden rise in traffic could indicate a breach exfiltrating data or a DoS attack. This can have a high impact on Confidentiality, Integrity and Availability  
      2. This sensor also has channels for errors which can be used to monitor port scanning attempts   
   2. Thresholds:  
      1. Since Big Dog doesn’t have a big online presence, a rise of 30% is suspicious enough to investigate.  
9. Windows Network Card Sensor: This sensor is similar to the previous one in that it also monitors network traffic. This sensor is only compatible with Windows and provides a few more channels that can be used to monitor more closely. This one is recommended for the Windows Server for Big Dog. \[21\]

   1. IoCs:  
      1. A sudden rise in traffic could indicate a breach exfiltrating data or a DoS attack. This can have a high impact on Confidentiality, Integrity and Availability  
      2. This sensor also has channels for errors which can be used to monitor port scanning attempts 

# RECOMMENDATIONS: {#recommendations:}

1. Network Segmentation \[22\]  
   1. Implementing Network Segmentation would prevent lateral movement of a malicious agent.   
2. Anti Virus and Anti Malware \[23\]  
   1. Endpoints used by employees need to be secured by anti virus and anti malware softwares to prevent entry of malicious entities into the system.  
3. Employee Education  
   1. As shown in the section, Risks and Vulnerabilities, a lot of risk lies on human error in the company. So, employees should be made aware of phishing and social engineering possibilities.\[24\]  
4. Data Encryption   
   1. As the proprietary Intellectual Property is the utmost priority of Big Dog, encrypting this data can provide a very robust security.\[25\]  
5. Multi Factor Authentication  
   1. Implementing multiple ways to authenticate employees can disrupt or delay a malicious agent's attempts at breaking in. \[26\]  
6. PRTG Sensor Recommendations:  
   1. Apart from the sensors mentioned in the table, Big Data can also use:  
      1. Windows IIS Application \- This sensor can be used to monitor files being transmitted, the number of users and the number of requests on the server. Any of these channels can be used to set a threshold to monitor the Windows Server environment. \[27\]  
      2. WMI Service Sensor \- This sensor can be set to monitor a particular service. It can monitor the CPU Usage and execution time of a request to this service which can be used as thresholds to monitor the SQL database or the IIS server. \[28\]  
7. We have included a link to a video explaining the basic premise of this report. The link is: [Cat Scan II Big Dog.mov](https://drive.google.com/file/d/1GezctRmHOh0GiXEBUc3Cf-xRQyDTVYRj/view?usp=drive_link)

# Citations: {#citations:}

1. SQL Injection Overview \- OWASP \- [https://owasp.org/www-community/attacks/SQL\_Injection](https://owasp.org/www-community/attacks/SQL_Injection)  
2. Privilege Escalation \- MITRE Tactic ID \- TA0004 \- [https://attack.mitre.org/tactics/TA0004/](https://attack.mitre.org/tactics/TA0004/)  
3. Cross Site Scripting (XSS) Overview \- OWASP \- [https://owasp.org/www-community/attacks/xss/](https://owasp.org/www-community/attacks/xss/)  
4. Buffer Overflow \- Fortinet \- [https://www.fortinet.com/resources/cyberglossary/buffer-overflow\#:\~:text=Also%20known%20as%20a%20buffer,the%20data%20in%20those%20locations](https://www.fortinet.com/resources/cyberglossary/buffer-overflow#:~:text=Also%20known%20as%20a%20buffer,the%20data%20in%20those%20locations).  
5. Path Traversal aka Directory Traversal \- OWASP \- [https://owasp.org/www-community/attacks/Path\_Traversal](https://owasp.org/www-community/attacks/Path_Traversal)  
6. CVE-2023-51630 \- Zero Day Initiative \- [https://cvedetails.com/cve/CVE-2023-51630/](https://cvedetails.com/cve/CVE-2023-51630/)  
7. Process Injection \- MITRE Tactic ID T1055 \- [https://attack.mitre.org/techniques/T1055/](https://attack.mitre.org/techniques/T1055/)  
8. Phishing \- MITRE Tactic ID T1598 \- [https://attack.mitre.org/techniques/T1598/](https://attack.mitre.org/techniques/T1598/)  
9. Malware Repository \- MITRE Data Source ID DS0004 \- [https://attack.mitre.org/datasources/DS0004/](https://attack.mitre.org/datasources/DS0004/)  
10. What is Social Engineering? \- ENISA \- [https://www.enisa.europa.eu/topics/incident-response/glossary/what-is-social-engineering](https://www.enisa.europa.eu/topics/incident-response/glossary/what-is-social-engineering)  
11. Spearphishing Service \- MITRE Sub-Technique ID \- T1598.001 \- [https://attack.mitre.org/techniques/T1598/001/](https://attack.mitre.org/techniques/T1598/001/)  
12. Security Categorization Case Study \- Compass \- [https://web.compass.lighthouselabs.ca/p/cyber/days/w02d2/activities/2835](https://web.compass.lighthouselabs.ca/p/cyber/days/w02d2/activities/2835)  
13. PRTG Manual: HTTP Sensor \- [https://www.paessler.com/manuals/prtg/http\_sensor](https://www.paessler.com/manuals/prtg/http_sensor)  
14. PRTG Manual: MySQL v2 Sensor \- [https://www.paessler.com/manuals/prtg/mysql\_v2\_sensor](https://www.paessler.com/manuals/prtg/mysql_v2_sensor)  
15. PRTG Manual: SSH Load Average Sensor \- [https://www.paessler.com/manuals/prtg/ssh\_load\_average\_sensor](https://www.paessler.com/manuals/prtg/ssh_load_average_sensor)  
16. PRTG Manual: SSH MemInfo Sensor \- [https://www.paessler.com/manuals/prtg/ssh\_meminfo\_sensor](https://www.paessler.com/manuals/prtg/ssh_meminfo_sensor)  
17. PRTG Manual: WMI Security Center Sensor \- [https://www.paessler.com/manuals/prtg/wmi\_security\_center\_sensor](https://www.paessler.com/manuals/prtg/wmi_security_center_sensor)  
18. PRTG Manual: SFTP Secure File Transfer Protocol Sensor \- [https://www.paessler.com/manuals/prtg/sftp\_secure\_file\_transfer\_protocol\_sensor](https://www.paessler.com/manuals/prtg/sftp_secure_file_transfer_protocol_sensor)  
19. PRTG Manual: Event Log (Windows API) Sensor \- [https://www.paessler.com/manuals/prtg/event\_log\_windows\_api\_sensor](https://www.paessler.com/manuals/prtg/event_log_windows_api_sensor)  
20. PRTG Manual: SNMP Traffic Sensor \- [https://www.paessler.com/manuals/prtg/snmp\_traffic\_sensor](https://www.paessler.com/manuals/prtg/snmp_traffic_sensor)  
21. PRTG Manual: Windows Network Card Sensor \- [https://www.paessler.com/manuals/prtg/wmi\_network\_card\_sensor](https://www.paessler.com/manuals/prtg/wmi_network_card_sensor)  
22. Network Segmentation \- Compass \- [https://web.compass.lighthouselabs.ca/p/cyber/days/w01d3/activities/2800](https://web.compass.lighthouselabs.ca/p/cyber/days/w01d3/activities/2800)  
23. Antivirus/Antimalware \- MITRE Mitigation ID M1049 \- [https://attack.mitre.org/mitigations/M1049/](https://attack.mitre.org/mitigations/M1049/)  
24. Employee Education is a Critical Defence Against Cyber Attacks \- Canadian Chamber of Commerce \- [https://chamber.ca/employee-education-is-a-critical-defence-against-cyber-attacks/](https://chamber.ca/employee-education-is-a-critical-defence-against-cyber-attacks/)  
25. What is encryption? \- Cloudflare \- [https://www.cloudflare.com/learning/ssl/what-is-encryption/](https://www.cloudflare.com/learning/ssl/what-is-encryption/)  
26. Multi-factor Authentication \- MITRE Mitigation ID M1032 \- [https://attack.mitre.org/mitigations/M1032/](https://attack.mitre.org/mitigations/M1032/)  
27. PRTG Manual: Windows IIS Application Sensor \- [https://www.paessler.com/manuals/prtg/wmi\_iis\_application\_sensor](https://www.paessler.com/manuals/prtg/wmi_iis_application_sensor)  
28. PRTG Manual: WMI Service Sensor \- [https://www.paessler.com/manuals/prtg/wmi\_service\_sensor](https://www.paessler.com/manuals/prtg/wmi_service_sensor)