# 

# 

# 

# CAT’S COMPANY VULNERABILITIES {#cat’s-company-vulnerabilities}

# TABLE OF CONTENTS {#table-of-contents}

[**CAT’S COMPANY VULNERABILITIES	1**](#cat’s-company-vulnerabilities)

[TABLE OF CONTENTS	2](#table-of-contents)

[**EXECUTIVE SUMMARY	3**](#executive-summary)

[**SCAN RESULTS	4**](#scan-results)

[**METHODOLOGY	6**](#methodology)

[NMAP	6](#nmap)

[List of Devices	7](#list-of-devices)

[OPENVAS/GVM	8](#openvas/gvm)

[**FINDINGS	9**](#findings)

[**RISK ASSESSMENT	10**](#risk-assessment)

[1\. VMWare Host	10](#vmware-host)

[2\. VMWare	13](#vmware)

[3\. Linux	13](#linux)

[4\. Windows 11	13](#windows-11)

[5\. Kali Linux	14](#kali-linux)

[**RECOMMENDATIONS	15**](#recommendations)

[Remediation	15](#remediation)

[1\. VMWare Host	15](#vmware-host-1)

[2\. Other devices	15](#other-devices)

[**CITATIONS	16**](#citations)

# EXECUTIVE SUMMARY {#executive-summary}

This report contains a vulnerability assessment scan of the company network for Cat’s Company to help them make critical decisions and security preparations to uphold the security of the organization. The assessment takes a look at all the devices active on the network and all the vulnerabilities that are present on them. The vulnerability assessment scan provides us with vulnerabilities that can be exploited by malicious agents looking to infiltrate the company network and some ways to mitigate them.

The first step to find vulnerabilities on the network was to list all the active devices on the network. 5 devices were found on Cat’s Company Network. After achieving that, we have run individual scans on each of these active devices to find vulnerabilities associated with them.

We have found some low and medium severity class vulnerabilities on the devices present on Cat’s Company network. As there is no vulnerability with a high severity class, there is no urgent need to overhaul the company network. But, steps should be taken to mitigate the medium and low class vulnerabilities as they can still pose a threat. 

Some steps are provided in this report to mitigate all the vulnerabilities found by the scan we have undertaken. The step which can provide the most protection for the organization involves uninstallation or modification of the configuration of a software which is responsible for most of the more critical vulnerabilities. The rest of the low level vulnerability mitigations require negligible work and cost.

Overall, the cost and work effort required to enhance the security of Cat’s Company network is manageable.

# 

# SCAN RESULTS {#scan-results}

We have run a vulnerability assessment scan on the company network, with the targets being all the hardware devices on the network. The scan has provided us with a few vulnerabilities. This section divides these vulnerabilities by device and severity.

![Imgur](https://imgur.com/a1FuCCn.png)
Chart showing devices and the severity of vulnerabilities found on them by the assessment.

As we can see, the scan was executed on a total of 5 devices, all of which exist on the company network. 

There are three severity classes of the vulnerabilities that have been found on the company network.\[1\] These classes indicate the level of risk associated with the vulnerabilities found on that system.\[1\] The highest vulnerability found and the severity level of that vulnerability determines the class of severity assigned to the device.\[1\] The severity classes can be:

1. Log: These are just informational messages that provide details about the scan execution or system configuration. These are not vulnerabilities so no action is needed to counter them.\[1\]  
2. Low: The risk posed by these vulnerabilities is low. These vulnerabilities are unlikely to be exploited or have little impact if they are.\[1\]  
3. Medium: Medium and High class severities are the most important and it should be a priority to fix them as soon as possible. Examples for medium class severity include misconfigurations that could allow for some unauthorized access or small software vulnerabilities.\[1\]  
4. High: High severity class is the most dangerous. It means a significant vulnerability is present on the system which can be used by malicious agents to gain remote access or configurations that can provide significant access to unauthorized users.\[1\]  
     
* From the chart, we can see that two devices have the highest severity class of Log.  
* Those devices can be ignored as no mitigations are needed to safeguard them.\[1\]  
* There are two more devices which have low class severity vulnerabilities on their systems. These devices need to be looked at.  
* The one device with medium class severity of vulnerabilities is the one that should be top priority to mitigate the vulnerabilities on this device.

# METHODOLOGY {#methodology}

This section details the methods used to find these vulnerabilities and all the details surrounding them. 

All of these tests have been run on a Kali Linux machine. It is a part of the cyber security division of the company. Kali Linux is a Linux distribution that is tailored towards information security tasks in particular.\[2\]

## NMAP {#nmap}

The first tool we used was nmap, which we use to find all the available devices on the company network.\[3\] This is done in order to make sure all the devices on the network are tested.

There are two steps to this.

1. First we run an IP address scan on the terminal of the Kali Linux Device to get the network address. This also provides us with the subnet mask, which is used to create sub networks under the main network. This can tell us how many devices can be on the network in total.\[4\]  
   ![Imgur](https://imgur.com/bCzW6kS.png)
   IP address scan that provides us with the network address and the subnet mask.  
2. Using the network address we have obtained from this, we can use nmap, a tool that can map networks to find all the active devices on our network.\[5\]  
   ![Imgur](https://imgur.com/IqZAVol.png)
   nmap scan provides us with active devices on the network  
   

As seen in the above screenshot, we can see that nmap has detected five active devices on the company network. All the further tests will be conducted with these five devices as targets.

## List of Devices {#list-of-devices}

Since there are only five devices on the company network, this report will categorize all vulnerabilities by device.

1. VMWare Host \- 192.168.219.1  
   1. The host machine that is running the Virtual Machine environment is the first device on this network. In this case, it is a Mac device.  
2. VMWare \- 192.168.219.2  
   1. The VMWare software that runs the Virtual Machines is the second device detected on the network.  
3. Linux \- 192.168.219.134  
   1. The Linux server machine on the network which runs on Ubuntu distribution that handles the file server  
4. Windows 11 \- 192.168.219.135  
   1. The Windows 11 machine on the network which manages the web server  
5. Kali Linux \- 192.168.219.136  
   1. As mentioned at the start of this section, the Kali Linux machine is a part of the cyber security division of the company and used to monitor activity on the company network.

   

   ## OPENVAS/GVM {#openvas/gvm}

All the security tests we have performed are on the Open Vulnerability Assessment Scanner (OpenVAS) which is an open-source Linux-based vulnerability scanner. It is supported by a community led by a German organization called Greenbone Networks. There are three main parts for this system.\[6\] They are:

1. The scanner applications that run the vulnerability scans  
   1. These scanners compare information from the target devices and their scan results to a database of known vulnerabilities, which provides the users all the information about any potential vulnerabilities found in the scan.\[6\]  
2. Greenbone Vulnerability Manager Database (GVMD)  
   1. This is the database of known vulnerabilities used by the scanners to find potential threats. It is part of an overall Manager daemon that is the heart of the overall system. This daemon allows control of scanner applications either directly or remotely.\[6\]  
   2. It also includes a user management function with permissions control which can be used to assign access to trusted parties only. It also provides the ability to schedule tasks, which can be used to test systems at an appropriate time to not interfere with a company's busy hours.\[6\]  
3. Greenbone Security Assistant  
   1. The Greenbone Security Assistant, also known as GSA, is a web-based user interface that connects and communicates with the GVMD. This works as the main interface for users to run, schedule and view test results.\[6\]  
      

Other tools used to research the vulnerabilities found include MITRE ATT\&CK and the NIST NVD. Both are industry standard databases of known vulnerabilities and their mitigations.

# FINDINGS {#findings}

All the systems were successfully scanned by the OpenVAS/GVM. Of the five devices shown as active by the nmap scan, all five were scanned successfully without any issues. As mentioned in the first section of this report, the Log severity class can be ignored. The rest of the vulnerabilities are detailed in the section, Risk Assessment, on page 9\.

# RISK ASSESSMENT {#risk-assessment}

This report identifies the highest priority vulnerabilities that need to be addressed on the company network. The severity level is determined by the Common Vulnerability Scoring System(CVSS) Score that has been assigned to a vulnerability by the National Vulnerability Database(NVD). All the tables containing vulnerabilities are sorted from highest to lowest severity. The number of vulnerabilities are divided in to these classes by severity:

![Imgur](https://imgur.com/z4rQM3A.png)
There are 5 low severity vulnerabilities and 14 medium severity vulnerabilities found in total on the whole network. Let’s separate them by the 5 devices as found by nmap and get more details on them:

1. ### VMWare Host {#vmware-host}

There are 15 total vulnerabilities found on this device, the most of any on the company network. 14 out of the 15 vulnerabilities found are of medium severity.

| Vulnerability | Summary | Severity | Source App | Solution |
| :---- | :---- | :---- | :---- | :---- |
| SSL/TLS: Report Weak Cipher Suites\[7\] (CVE-2015-4000) | Detection of the acceptance of weak Cipher Suites (set of algorithms used to secure networks) | Medium / 5.9 | XAMPP | Disable acceptance of weak cipher suites |
| HTTP Trace / Track Methods Allowed\[8\] (CVE-2014-7883) | Trace and Track are methods used to debug web server connections. These are enabled on the target device. | Medium / 5.8 | XAMPP | Disable these HTTP methods |
| MacOS X Finder ‘.DS\_Store’ Information Disclosure\[9\] (CVE-2018-6470)  | MacOS X creates a hidden file in each directory viewed with Finder App. This can provide an attacker the structure of the website | Medium / 5.3 | XAMPP | Block access to hidden files within the web server (starting with a dot in filename) |
| phpinfo() output Reporting\[10\] (CVE-2023-49283)  | File usually created during a tutorial when setting up is left in the web server directory. This file can provide privileged info to attacker | Medium / 5.3 | XAMPP | Delete the files or restrict access |
| SSL/TLS: Server Certificate / Certificate in Chain with RSA keys less than 2048 bits\[11\] | Certificates using RSA keys with less than 2048 bits are considered unsafe | Medium / 5.3 | XAMPP | Replace the certificate with a new one with the appropriate keys |
| SSL/TLS: Known Untrusted / Dangerous Certificate Authority Detection\[11\] | The service is using a security certificate issued by a known untrusted or dangerous authority | Medium / 5.0 | XAMPP | Replace the certificate with a new one from a more trustable agency |
| SSL/TLS Certificate Expired\[11\] | The server’s SSL/ TLS certificate is expired | Medium / 5.0 | XAMPP | Replace the certificate with a new one |
| FTP Unencrypted Cleartext Login\[11\] | The remote host is running a FTP service that allows cleartext logins over unencrypted connections | Medium / 4.8 | XAMPP | Enable FTPS or enforce the connection via AUTH TLS command |
| SSL/TLS: Deprecated TLSv1.0 and TLSv1.1 Protocol Detection\[12\] (CVE-2015-0204) | Usage of deprecated protocols has been detected | Medium / 4.3 | XAMPP | Disable the ability to use deprecated protocols |
| SSL/TLS Certificate signed using a weak signature algorithm\[11\] | The algorithm used to sign the security certificates is a weak security algorithm | Medium / 4.0 | XAMPP | Replace the certificate with a new one |
| SSL/TLS: Diffie-Hellman Key Exchange Insufficient DH Group Strength Vulnerability\[11\] | The key size used to administer the SSL/TLS service uses less than recommended key size | Medium / 4.0 | XAMPP | Use 2048-bit key size |
| TCP Timestamps Information Disclosure\[11\] | The remote host implements TCP timestamps which can be used to calculate the uptime of a device which can be used by attackers | Low / 2.6 | \- | Disable TCP timestamps |

2. ### VMWare {#vmware}

   1. On this device, there are no notable vulnerabilities found by the scan.

3. ### Linux {#linux}

   1. This system accounts for 3 vulnerabilities, all of which are in the low class severity.

| Vulnerability | Summary | Severity | Source App | Solution |
| :---- | :---- | :---- | :---- | :---- |
| TCP Timestamps Information Disclosure\[11\] | The remote host implements TCP timestamps which can be used to calculate the uptime of a device which can be used by attackers | Low / 2.6 | \- | Disable TCP timestamps |
| Weak MAC Algorithm(s) Supported (SSH)\[11\] | The remote SSH server is configured to allow / support weak MAC algorithms | Low / 2.6 | \- | Disable the reported weak MAC algorithms |
| ICMP Timestamp Reply Information Disclosure\[13\] (CVE-1999-0524) | The remote host responded to an ICMP timestamp request | Low / 2.1 | \- | 1\. Disable the support for ICMP timestamps 2\. Protect with a firewall and block ICMP packets passing through |

4. ### Windows 11 {#windows-11}

   1. This system has only one vulnerability which is of the low class severity.

| Vulnerability | Summary | Severity | Source App | Solution |
| :---- | :---- | :---- | :---- | :---- |
| TCP Timestamps Information Disclosure\[11\] | The remote host implements TCP timestamps which can be used to calculate the uptime of a device which can be used by attackers | Low / 2.6 | \- | Disable TCP timestamps |

5. ### Kali Linux {#kali-linux}

   1. No vulnerabilities are found on this system by this scan. This could be due to it being the host device for the scan and it might require a scan from an external source.

# RECOMMENDATIONS {#recommendations}

This report should not be considered as the definitive measurement of the company’s cyber security. There are other elements which should also be investigated before a complete picture can be achieved. Internal penetration testing, a review of company policies and testing user compliance to company policies can be implemented to get more information.

## Remediation {#remediation}

Overall, the company network is quite secure. There are some vulnerabilities which need mitigation. Here are some recommendations for them. All the recommendations are categorized by device. Taking the following recommendations will mitigate 100% of the vulnerabilities found in the company network.

1. ### VMWare Host {#vmware-host-1}

   1. Almost all of the vulnerabilities and all of the most severe ones are the result of one application by the name of XAMPP. This was found due to some of the vulnerabilities referencing expired certificates issued by the organization that makes this software. If the application is not an essential one, the easiest solution would be to uninstall it.\[14\]  
   2. If the application is required, it would be recommended to follow the solutions provided for each of the vulnerabilities in the table in  the Risk Assessment Section.  
   3. Some of the vulnerabilities can be mitigated by updating the security certificate of the server with a new one with a valid certifying authority and the recommended keys and encryption algorithm.  
   4. The highest severity level vulnerabilities are found on this system. The priority of these vulnerabilities is the highest.  
   5. The cost of applying the mitigations is quite low compared to the impact an attack from these vulnerabilities can have. 

2. ### Other devices {#other-devices}

   1. For all the other devices, the provided solutions in the table are the best way to mitigate any risks associated with the vulnerabilities that have been found by the scan.  
   2. All of the vulnerabilities found on these devices are of a low level severity or just informational logs. So the priority is low on the order of solving them.  
   3. The cost to apply the mitigations is negligible. So, it is recommended to apply these mitigations once the higher priority ones have been mitigated.

# CITATIONS {#citations}

1. 11.2.1.2 Interpreting a Report \- GSM Manual \- [11 Reports and Vulnerability Management \- Greenbone Enterprise Appliance – GOS 22.04.22](https://docs.greenbone.net/GSM-Manual/gos-22.04/en/reports.html)  
2. Kali Linux \- [Kali Linux](https://www.kali.org/)  
3. Nmap \- What is nmap? \- [Nmap](https://nmap.org/)  
4. Linux IP Commands \- [Linux ip Command Examples \- nixCraft](https://www.cyberciti.biz/faq/linux-ip-command-examples-usage-syntax/)  
5. nmap Cheat Sheet \- [Nmap Cheat Sheet 2024: All the Commands & Flags](https://www.stationx.net/nmap-cheat-sheet/)  
6. What is OpenVAS? \- Compass \-   
7. Weak Cipher Suites \- NVD \- [NVD \- CVE-2015-4000](https://nvd.nist.gov/vuln/detail/CVE-2015-4000)  
8. HTTP Trace / Track Methods \- NVD \- [NVD \- CVE-2014-7883](https://nvd.nist.gov/vuln/detail/CVE-2014-7883)  
9. MacOS X Finder ‘.DS\_Store’ \- NVD \- [NVD \- CVE-2018-6470](https://nvd.nist.gov/vuln/detail/CVE-2018-6470)  
10. phpinfo() output Reporting \- NVD \- [NVD \- CVE-2023-49283](https://nvd.nist.gov/vuln/detail/CVE-2023-49283)  
11. Network Vulnerability Tests \- OpenVas \- [10 Scanning a System \- Greenbone Enterprise Appliance – GOS 22.04.22](https://docs.greenbone.net/GSM-Manual/gos-22.04/en/scanning.html)  
12. Deprecated TLSv1.0 and TLSv1.1 Protocol \- [NVD \- CVE-2015-0204](https://nvd.nist.gov/vuln/detail/CVE-2015-0204)  
13. ICMP Timestamp Reply \- [NVD \- CVE-1999-0524](https://nvd.nist.gov/vuln/detail/CVE-1999-0524)  
14. Report Export \- [report-05723afa-8a39-469c-9d0b-56384750e3f4.pdf](https://drive.google.com/file/d/1bMp8gbRHRiOX461Eqc6S5zVCUxi2w4fV/view?usp=drive_link)
