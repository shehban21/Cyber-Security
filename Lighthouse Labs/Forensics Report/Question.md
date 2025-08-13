## Forensic Investigation Project

### Case 001 – The Stolen Szechuan Sauce

## Project Introduction

This project uses a scenario created by DFIR Madness. You will work through Case 001, The Stolen Szechuan Sauce.

### IMPORTANT INSTRUCTIONS

1. The files needed for this assignment are already pre-installed in either the Windows1 machine in EVE or Windows 11 in VirtualBox/VMWare.  
2. For .mem files you can use the volatility tool to analyze them and for .pcap files you can use wireshark as you have done in previous exercises\!

Note

You can try to solve this without the artifacts from the desktop\! (This will save you a large download, but might make things a bit harder.)

The following link will take you to the Case, details and instructions. Read through ALL of the information presented first:

[CASE 001 – THE STOLEN SZECHUAN SAUCE](https://dfirmadness.com/the-stolen-szechuan-sauce/)

## Instructions

After reading the information that the case provides and reviewing ALL of the sections, you can find the artifacts in either your Windows1 machine (if using EVE) or Windows11 VM (if using VirtualBox).

* DC01 Disk Image (EO1) This is 4.7 GB\! (1 person gets this one)  
* DC01 Memory and PageFile 535MB and 12.9 MB  
* DC01 Autoruns  
* DC01 Protected Files  
* Case001 PCAP  
* Desktop Disk Image (E01) 6.4 GB\!\! (The 2nd person gets this\!)  
* Desktop Memory and PageFile  
* Desktop Autoruns  
* Desktop Protected Files (You can skip these if you want)

Note

Artifacts can be found on the website: [https://dfirmadness.com/the-stolen-szechuan-sauce/](https://dfirmadness.com/the-stolen-szechuan-sauce/)

1. On the site, after you have your artifacts, go to CHOOSE YOUR NEXT MOVE and do just that\!  
2. Pick a place to start, divide up the work if that is how you wish to approach things, and get at it\!  
3. In CHOOSE YOUR NEXT MOVE one item, I want to learn how to look at a super timeline of the disks is marked as (Coming soon) but can be found here [https://dfirmadness.com/case-001-super-timeline-analysis/](https://dfirmadness.com/case-001-super-timeline-analysis/)

## Questions to Answer and Goals from the Case

Answer the following questions and use the submission guidelines below to ensure you are providing an explanation of your process, screen captures of where you found each answer and the tools and artifacts you used.

1. What’s the Operating System of the Server?  
2. What’s the Operating System of the Desktop?  
3. What was the local time of the Server?  
4. Was there a breach?  
5. What was the initial entry vector (how did they get in)?  
6. Was malware used? If so, what was it? If there was malware answer the following:  
   * What process was malicious?  
   * Identify the IP Address that delivered the payload.  
   * What IP Address is the malware calling to?  
   * Where is this malware on disk?  
   * When did it first appear?  
   * Did someone move it?  
   * What were the capabilities of this malware?  
   * Is this malware easily obtained?  
   * Was this malware installed with persistence on any machine?  
     * When?  
     * Where?

Warning

The next questions are optional, meaning you are not required to complete them.

1. What malicious IP Addresses were involved?  
   * Were any IP Addresses from known adversary infrastructure?  
   * Are these pieces of adversary infrastructure involved in other attacks around the time of the attack?  
2. Did the attacker access any other systems?  
   * How?  
   * When?  
   * Did the attacker steal or access any data?  
     * When?  
3. What was the network layout of the victim network?  
4. What architecture changes should be made immediately?  
5. Did the attacker steal the Szechuan sauce? If so, what time?  
6. Did the attacker steal or access any other sensitive files? If so, what times?  
7. Finally, when was the last known contact with the adversary?

Note

Answer as much of this as you can\! It is NOT expected that you get all the way through\! You should be able to answer questions 1 to 6\.

Note

DFIR MADNESS [https://dfirmadness.com/](https://dfirmadness.com/) has lots more information. Bookmark it\! Have fun with the project\!

