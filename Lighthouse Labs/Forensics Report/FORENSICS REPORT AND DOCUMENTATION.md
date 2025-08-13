

| FORENSICS REPORT AND DOCUMENTATION |
| :---: |

# Table of Contents {#table-of-contents}

[FORENSICS REPORT AND DOCUMENTATION](#forensics-report-and-documentation)

[Table of Contents](#table-of-contents)

[What’s the Operating System of the Server?](#what’s-the-operating-system-of-the-server?)

[What’s the Operating System of the Desktop?](#what’s-the-operating-system-of-the-desktop?)

[What was the local time of the server?](#what-was-the-local-time-of-the-server?)

[Was there a breach?](#was-there-a-breach?)

[What was the initial entry vector (how did they get in)?](#what-was-the-initial-entry-vector-\(how-did-they-get-in\)?)

[Was malware used? If so, what was it?](#was-malware-used?-if-so,-what-was-it?)

[What process was malicious?](#what-process-was-malicious?)

[Identify the IP Address that delivered the payload](#identify-the-ip-address-that-delivered-the-payload)

[What IP address is the malware calling to?](#what-ip-address-is-the-malware-calling-to?)

[Where is this malware on disk?](#where-is-this-malware-on-disk?)

[When did it first appear?](#when-did-it-first-appear?)

[Did someone move it?](#did-someone-move-it?)

[What were the capabilities of this malware?](#what-were-the-capabilities-of-this-malware?)

[Is this malware easily obtained?](#is-this-malware-easily-obtained?)

[Was this malware installed with persistence on any machine?](#was-this-malware-installed-with-persistence-on-any-machine?)

[What malicious IP Addresses were involved?](#what-malicious-ip-addresses-were-involved?)

[Were any IP addresses from known adversary infrastructure?](#were-any-ip-addresses-from-known-adversary-infrastructure?)

[Are these pieces of adversary infrastructure involved in other attacks around the time of the attack?](#are-these-pieces-of-adversary-infrastructure-involved-in-other-attacks-around-the-time-of-the-attack?)

[Did the attacker access any other systems?](#did-the-attacker-access-any-other-systems?)

[How? When?](#how?-when?)

[Did the attacker steal or access any data?](#did-the-attacker-steal-or-access-any-data?)

[What was the network layout of the victim network?](#what-was-the-network-layout-of-the-victim-network?)

[Recommended Architecture Changes](#recommended-architecture-changes)

[Did the attacker steal the Szechuan Sauce? If so, when?](#did-the-attacker-steal-the-szechuan-sauce?-if-so,-when?)

[Did the attacker steal or access any other sensitive files? If so, what times?](#did-the-attacker-steal-or-access-any-other-sensitive-files?-if-so,-what-times?)

[When was the last known contact with the adversary?](#when-was-the-last-known-contact-with-the-adversary?)

[Citations](#citations)

# What’s the Operating System of the Server? {#what’s-the-operating-system-of-the-server?}

![][image1]

Tools Used : Autopsy

The operating system of the server is Windows Server 2012 R2 Standard Evolution. To find this information, I used Autopsy, which is an end to end open source forensics solution. The steps for this are:

1. Start a new case after opening Autopsy.  
2. Once the case details have been configured, add the Disk Image (E01) file as a data source to Autopsy.  
3. Once the data has been added, various categories of the data on the left side can be seen. In this section, there is a category for Data Artifacts which contains concrete data extracted from the data source. Under it, Operating System Information for the selected disk image is listed under Program Name.

# What’s the Operating System of the Desktop? {#what’s-the-operating-system-of-the-desktop?}

![][image2]  
Tools Used : Autopsy

The operating system of the desktop is Windows 10 Enterprise Evaluation.

The process for this is the same as the previous question. Just select the disk image of the desktop under the Operating System Information instead of the server’s. 

# What was the local time of the server? {#what-was-the-local-time-of-the-server?}

![][image3]  
Tools Used : Registry Explorer

The local time of the server was Pacific Standard Time.

To get this information, load the system log file from protected files to Registry Explorer. These registry files contain information about configuration settings of the system. Under the system file, information about the general settings of the Operating System can be found. 

The time zone information is in ROOT \> ControlSet001 \> Control \> TimeZoneInformation. It can also be searched

# Was there a breach? {#was-there-a-breach?}

Yes, there was a breach. There is the existence of malware in the system as evidence. The malware was delivered after a successful brute force attack on the Administrator account on the Domain Controller from a remote attacker. The details of how this was carried out is provided in the next questions.

# 

# What was the initial entry vector (how did they get in)? {#what-was-the-initial-entry-vector-(how-did-they-get-in)?}

Tools Used : Windows Event Viewer  
![][image4]  
A screen capture of unsuccessful logins attempted by a kali workstation on the Administrator account. There were 95 unsuccessful attempts before the attack was successful.  
![][image5]Seconds after the last unsuccessful attempt, we can see a successful login on the Administrator account. We can also see the IP Address that logged in. It was 194.61.24.102.

The process for this requires the Security Log file from the Domain Controller Disc Image. It can be obtained by using Autopsy. Since all the files from the system are present, go to the partition where Windows is installed and find the file under Windows \> System32 \> winevt \> Logs. The name of the file is Security, and it has an evtx extension. Extract the file by right-clicking and exporting it.

Once the file is exported, it can be opened on a Windows device with the built in Event Viewer. Each kind of event has an ID that can be searched. For an unsuccessful login attempt, the event ID is 4625\. 

After searching that and finding the suspicious attempts, check for a successful logon around the same time from suspicious sources. The event ID for successful login is 4624\.

There was a successful attempt from a suspicious IP address seconds after the last unsuccessful attempt. From the evidence found till now, it seems highly likely that the system was subjected to a brute force attack and the attackers got in by brute forcing the correct password. This is further corroborated by the network capture which shows a lot of traffic from the IP address 194.61.24.102. 

The attack started at 03:21:48 UTC. The time shown in the Event Viewer is according to the time zone of the device it is viewed on. This one was viewed on a Windows device with the Eastern Daylight Time (-4) time zone.  
![][image6]  
UTC time shown in Details \> TimeCreated

# Was malware used? If so, what was it? {#was-malware-used?-if-so,-what-was-it?}

Tools Used : Wireshark, Windows Defender, Autostart file, Google

Yes, there was malware. The malware was coreupdater.exe. The sub questions below show how the answer was found and the relevant screenshots.

## What process was malicious? {#what-process-was-malicious?}

Look at the programs in the Autostart file and check for any suspicious programs. Check on Google for programs that are unknown. This “coreupdater” program looks suspicious as most of the other programs have a short summary of their usage and this program is missing that.  
![][image7]coreupdater in the autostart file

Searching on Google confirmed our suspicions about its maliciousness.   
![][image8]Joe’s Sandbox Analysis Report for coreupdater.exe

## 

## Identify the IP Address that delivered the payload {#identify-the-ip-address-that-delivered-the-payload}

The first thing to do would be to check if the IP Address that breached the system has communicated anything to the company system. For that, load the PCAP file, a packet capture that provides us with the information about all the communication that took place from a device, to Wireshark, a software that can read and analyse packet captures. Filter for traffic from the suspicious IP address, i.e. 194.61.24.102. All the brute force attempts can be seen in this as there is a lot of traffic originating from that IP address probing all the ports on the system. 

HTTP is used to transfer data on the internet, be it a website’s data or download files like malware. Filter for HTTP communication with that IP address as that could show any files downloaded from that IP address. The filter is **“ip.addr \== 194.61.24.102 && http”**. 

The filtered data shows that an .exe file named **“coreupdater.exe”** was requested by a device in the victim company system. An exe file is an executable file that installs software on Windows devices. 

Export the file by using Wireshark’s “Export Objects” feature. It is available under File \> Export Objects \> HTTP. Upon downloading it, it was instantly flagged as malicious by Windows Defender and deleted, which confirms the suspicions about it being malware. ![][image9]Where to find the export option in Wireshark  
![][image10]Exporting the http package containing coreupdater.exe  
![][image11]  
Windows Defender data about the program

## What IP address is the malware calling to? {#what-ip-address-is-the-malware-calling-to?}

![][image12]coreupdater.exe connecting to 203.78.103.109

Tools Used: Volatility Framework

Volatility Framework, which is an open-source Memory Forensics software, was used to run some tests on the memory files. Run a netscan command to find out all the communication on the system and which program they originated from. 

**python vol.py \-f "E:\\VolLab2\\citadeldc01.mem" windows.netscan**

Looking into it, it can be seen that the malware, coreupdater.exe has connected with 203.78.103.109.

## Where is this malware on disk? {#where-is-this-malware-on-disk?}

![][image13]  
Volatility scan finding coreupdater

Tools Used: Volatility Framework

The malware is at **“Windows\\System32\\coreupdater.exe”.** A filescan using the Volatility framework was run to find the location. Filescan looks for files on the memory image provided. Filter the data by providing the Select\_String function of the Powershell to only show files with “coreupdater” in them.

## When did it first appear? {#when-did-it-first-appear?}

![][image14]coreupdater.exe created at 03:24:12 UTC on 19 September 2020

Tools Used \- Autopsy

Autopsy was used to look at the disk image of the Server. As the location is known from the previous question’s answer, Autopsy can be used to go to that location on its File Explorer. Details about the file can be seen there. As you can see, the created time for the file is 03:24:12 UTC on September 19\.

## Did someone move it? {#did-someone-move-it?}

![][image15]Searching “coreupdater.exe” on Autopsy

![][image16]Log file showing updates to file

Tools Used : Autopsy, NTFS Log Viewer

Yes it has been moved. When searching for “coreupdater.exe” on Autopsy, it found a WebCache file that showed the file was downloaded from the IP address we discovered earlier and it was saved to the Downloads folder. But, earlier in the investigation, it was found in the System32 folder when using the Volatility Framework. So, it must have been moved. 

To verify, Log files can be used to check. The $LogFile contains all the data regarding the creation and changes to the file system in a Windows device. The $LogFile can be found in the root directory of the hard drive. Export it with Autopsy.

After exporting it, it can be analysed by using NTFS Log Tracker to parse and view its data. Once the data has been parsed, searching for “coreupdater.exe” shows details regarding its file history. As shown in the screenshot above, there is a record of moving it.

## 

## What were the capabilities of this malware? {#what-were-the-capabilities-of-this-malware?}

![][image17]  
VirusTotal Page of coreupdater.exe

Tools used : PowerShell, VirusTotal

Searching for coreupdater.exe on Google shows us some information about it. In the screenshot above, VirusTotal shows the capability of Data Manipulation. Data Manipulation is the ability to create, move, modify and delete data on a device. This can be used to delete sensitive data of the victim or exfiltrate data. To make sure this result is actually for the coreupdater malware found in this investigation, a hash number can be used to verify they are the same files.  
![][image18]Getting hash of the malware file  
Turn off AntiVirus protection and extract the **“coreupdater.exe”** file from the packet capture as shown earlier. The Windows Defender AntiVirus instantly identifies it and deletes the file so it is necessary to turn the protection off to keep the file. To get the hash number, open PowerShell and run the command **“Get-FileHash”.**

VirusTotal also stores the hash numbers. Searching for the one obtained in this investigation, it confirms the Google search found the correct one.

## Is this malware easily obtained? {#is-this-malware-easily-obtained?}

![][image11]  
Windows Defender shows it is a “Metasploit” malware

Tools Used : Windows Defender, Google

Metasploit is an open source penetration testing software that is typically used to find vulnerabilities. But, as it is open source, it can be modified and used as needed by the end user. And it being open source means it is easily obtainable.

## Was this malware installed with persistence on any machine? {#was-this-malware-installed-with-persistence-on-any-machine?}

![][image19]  
Searching “coreupdater” in registry files

![][image20]”coreupdater” in Autostart  
Tools Used : Registry Explorer, Autorun file

Yes, it looks like it has been installed with persistence on both the desktop and the server as it has set up Autorun on both. 

Searching in the protected files after loading them in the Registry Explorer also shows it as a service with auto start enabled.

Every time the computer reboots, the software is also terminated. However, adding it to the autostart allows it to automatically start itself when the computer powers on. This prevents a reboot or shut down from stopping the malware and can be called persistence. 

The registry explorer shows the last modified time as 03:42:42 UTC on 19th September on the Desktop and 03:27:49 on the Server.

# What malicious IP Addresses were involved? {#what-malicious-ip-addresses-were-involved?}

Tools Used: Wireshark, Volatility Framework ( Used in the previous questions to find the malicious IP Addresses) and VirusTotal

There are two malicious IP addresses found in this investigation. They are:

1. 194.61.24.102 \- The IP address that entered by brute force and delivered the payload

![][image21]  
VirusTotal analysis of 194.61.24.102

2. 203.78.103.109 \- The IP address contacted by the “coreupdater.exe” malware

![][image22]VirusTotal analysis of 203.78.103.109

## 

## Were any IP addresses from known adversary infrastructure? {#were-any-ip-addresses-from-known-adversary-infrastructure?}

Tools Used : VirusTotal

Searching the IP addresses on VirusTotal shows them as malicious. So, they’re both from a known infrastructure.

## Are these pieces of adversary infrastructure involved in other attacks around the time of the attack? {#are-these-pieces-of-adversary-infrastructure-involved-in-other-attacks-around-the-time-of-the-attack?}

Tools Used : VirusTotal

The IP address that dropped the payload (194.61.24.102) is referred to quite a few times by different files. This could mean the same infrastructure was used to drop other kinds of malware in other places around the same time of this attack. ![][image23]Files associated with the IP address 194.61.24.102

# Did the attacker access any other systems? {#did-the-attacker-access-any-other-systems?}

Tools Used : Autopsy, Wireshark

Yes, it does look like aside from the Server which was the entry point, the desktop on the network was also infected as seen from the previously referred registry entries and autorun files.

## How? When? {#how?-when?}

![][image24]”coreupdater.exe” search on Desktop Disk Image in Autopsy

Using Autopsy, a search for “coreupdater.exe” on the desktop disk image reveals that the file was created around 03:40:49 UTC. Further examination of the search results shows the program running at approximately 05:16 UTC under the Username “Administrator”.

The breach probably happened by the malicious agent taking control of the “Administrator” account on the Domain Controller and using Remote Desktop Protocol to install the malware on the Desktop.  
![][image25]Wireshark capture of remote connection between the two devices

## Did the attacker steal or access any data? {#did-the-attacker-steal-or-access-any-data?}

Tools Used : Wireshark, Autopsy, NTFS Log Viewer

Looking into the traffic between the two devices shows them communicating for a while but that looks like normal traffic. SMB2 communication also happens regularly between the two devices. But, around 04:08:16 UTC we see a request for a folder called FileShare on the Server.   
![][image26]SMB2 protocol connection between server and desktop and requesting FileShare

A look at the Autopsy disk image of the Server shows that the FileShare folder is recently accessed by the Administrator. The FileShare folder contains the files from the Secret Folder which includes the Szechuan Sauce file as well. It looks like the files were moved to the FileShare folder around 03:30 UTC.  
![][image27]Recent files accessed in the Server and Desktop

Usually, when exfiltrating data, the malware zips the files in a folder into one single file with a .zip extension as one file is easier to transfer. Searching for a log entry for files ending in the .zip extension reveals a trace of the file being created, moved and then deleted. As can be seen from the screenshot below, the file was created, moved and then deleted within 100 seconds. 

This could indicate the malware accessing the files in the folder named “Secret”, zipping it and then moving it to the FileShare folder to exfiltrate it and delete it once it was completed.![][image28]File history of Secret.zip found by searching “.zip” extension in Log File

Same process was followed on the Desktop disk image and two suspicious files with the .zip extension were found. They were named loot.zip and My Social Security Number.zip. These files appeared around 03:46 UTC and were deleted soon after. ![][image29]History of .zip extension files on Desktop found in the $UsnJrnl file  
![][image30]Recent files in the Desktop disk image shows a loot.zip file

“Loot.zip” also shows up in the “Recent Documents” on Autopsy. It also shows all the files were accessed and probably exfilitrated.  
![][image31]loot.zip was visited by the Administrator as seen in this search for the “loot.zip” keyword. “Loot.zip” can also be seen in the UsnJrnl Log file.

A WebCache file shows Administrator accessing the file in its history. The WebCache file stores the recent history of internet data.

When checking for traffic going to the malicious IP Address (203.78.103.109) that was contacted by “coreupdater.exe”, it can be seen that encrypted data was sent to that IP address starting at 02:25 AM and going all the way till 05:03 AM which was the last contact with that IP. Since the data is encrypted, it is not clear what it is but it would be a safe bet to assume it is the exfiltrated data from both the server and desktop.  
![][image32]  
Encrypted connection between server, desktop and malicious IP Address

# What was the network layout of the victim network? {#what-was-the-network-layout-of-the-victim-network?}

Tools Used : Wireshark

By looking at the IP addresses known to be on the network, it's possible to infer the subnet mask. The two IP addresses known from the network are: 10.42.85.115 \- Desktop 10.42.85.10 \- Server The first three octets of the IP addresses are the same, which implies a /24 subnet mask.

When filtering out the traffic from this subnet in WireShark, it covers 99.3% of the packets captured. To ensure there wasn't a different network layout, the traffic was filtered to only show the packets excluded in the previous search. This yielded the remaining 0.7% of the traffic, and examining it revealed only communication between MAC addresses, VMWare, and Broadcasts.

![][image33]Wireshark filter on the package capture to show traffic that may not be from the  victim network![][image34]  
Wireshark filter on the package capture to show traffic from the  victim network

This is what the topology diagram would look like:  
![][image35]

# Recommended Architecture Changes {#recommended-architecture-changes}

* Since the attack was made by logging in remotely from an outside network, the company can put in restrictions which would allow only local connection.  
* If remote connections are necessary, extra protections on them such as MFA (Multi Factor Authentication) and VPNs can be made mandatory.

# Did the attacker steal the Szechuan Sauce? If so, when? {#did-the-attacker-steal-the-szechuan-sauce?-if-so,-when?}

![][image36]  
This Autopsy screenshot shows the Szechuan Sauce was visited by Administrator

Tools Used : Autopsy

This search for “szechuan” on Autopsy shows it was accessed by the Administrator at around 03:32:21 UTC. It also shows up in a WebCache file which shows recent history of web activity. Since it shows up in that file, it’s very likely that it was accessed remotely by the Administrator account. 

# 

# Did the attacker steal or access any other sensitive files? If so, what times? {#did-the-attacker-steal-or-access-any-other-sensitive-files?-if-so,-what-times?}

Tools Used : Autopsy

Yes, some sensitive files on the Desktop were also stolen. As mentioned before, a loot.zip and My Social Security Number.zip files were created and deleted on the Desktop disk drive image in Autopsy. This gives some evidence of it being stolen as well. Searching for “loot.zip” shows a WebCache file which includes it. As shown before, this means it was accessed remotely. The time on the “loot.zip” file is 03:46:18 UTC.  
![][image31]Screenshot of Autopsy search for “loot.zip”

The WebCache file's modified time is not useful because it only reflects when the file was last updated, not when specific web communications occurred. Since it contains a history of web activity, the modified time does not indicate when individual web communications took place. 

# 

# When was the last known contact with the adversary? {#when-was-the-last-known-contact-with-the-adversary?}

Tools Used : Wireshark

The last known contact to the adversary is at 05:07 UTC which was with the IP Address  203.78.103.109  
![][image32]

# Citations {#citations}

1. Smith, James*. The Case of the Stolen Szechuan Sauce.* DFIR Madness. (September 21, 2020). Retrieved August 28, 2024\. [Case 001 \- The Stolen Szechuan Sauce \- DFIR Madness](https://dfirmadness.com/the-stolen-szechuan-sauce/)  
2. Lalvani, Tanvi. *Case of the stolen Szechuan sauce.* Medium. (August 23, 2023). Retrieved August 30, 2024\. [Case of the stolen Szechuan sauce | by Tanvi Lalwani | Medium](https://medium.com/@tanvilalwani5/case-of-the-stolen-szechuan-sauce-bd440e5c2a6d)  
3. Walshcat. *Case Write Up : The Stolen Szechuan Sauce.* Medium. (March 1 2023). Retrieved August 30, 2024\. [Case Write Up : The Stolen Szechuan Sauce | by walshcat](https://walshcat.medium.com/case-write-up-the-stolen-szechuan-sauce-2409344264c3)  
4. ChatGPT conversation \- [https://chatgpt.com/share/b6c6c957-294c-4181-9b12-3eca327e3c03](https://chatgpt.com/share/b6c6c957-294c-4181-9b12-3eca327e3c03)  
5. Pearson, Ashley. *Volatility 3 Cheatsheet.* ONFVP. (May 10, 2021). Retrieved August 28, 2024\. [Volatility 3 CheatSheet \- onfvpBlog \[Ashley Pearson\]](https://blog.onfvp.com/post/volatility-cheatsheet/)  
6. VirusTotal \- [VirusTotal](https://www.virustotal.com/gui/home/upload)
