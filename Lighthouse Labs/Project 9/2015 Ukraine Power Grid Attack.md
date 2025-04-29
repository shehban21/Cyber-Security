## Investigation & Research Report

Develop an investigation and research report for your chosen Cyber Security attack. Include the following information in your report:

* Who were the victims of the attacks?  
* What technologies and tools were used in the attack? (stolen data, ransom, system damage, etc.)  
* When did the attack happen within the network?  
* What systems were targeted?  
* What was the motivation of the attackers in this case? What did they hope to achieve?  
* What was the outcome of the attack? (stolen data, ransom, system damage, etc.)  
* What mitigation technique would you recommend to prevent these attacks in future?  
* Describe security controls that would help and mitigate these risks.

| 2015 Ukraine Power Grid Attack |
| :---: |

# Table of Contents {#table-of-contents}

[**2015 Ukraine Power Grid Attack	1**](#2015-ukraine-power-grid-attack)

[**Table of Contents	2**](#table-of-contents)

[**Executive Summary	3**](#executive-summary)

[**Introduction	4**](#introduction)

[**The Victims	4**](#the-victims)

[**Tools and Technologies Used	5**](#tools-and-technologies-used)

[**Timeframe of the Attack	5**](#timeframe-of-the-attack)

[**Targeted Systems	5**](#targeted-systems)

[**Attackers Motivation	6**](#attackers-motivation)

[**Outcome of the Attack	6**](#outcome-of-the-attack)

[**Mitigation Techniques	6**](#mitigation-techniques)

[**Recommended Security Controls	7**](#recommended-security-controls)

[**Conclusion	7**](#conclusion)

[**Citations	8**](#citations)

# Executive Summary {#executive-summary}

Ukraine is the largest country entirely in Europe. It came into existence following the fall of the Soviet Union in 1991\. Since then, the relations between Russia and Ukraine have deteriorated. The annexation of Crimea by Russia has put a dent in any resolution to these strenuous relations. In the wake of all this tension, there was a cyber attack in 2015 that rocked the world of cyber security.

On December 23, 2015, three power control centres in Western Ukraine were attacked by malicious agents from an Advanced Persistent Threat known as “**Sandworm**”. Sandworm is based in Russia as per sources. The attack resulted in a power outage that affected 230,000 people in three regions of Ukraine.

What this attack demonstrated was the ability of a foreign / rogue state entity to take control and disable essential services. An attack like this on US infrastructure could result in loss of life due to loss of facilities in hospitals and other essential places. It could also lead to losses in the billions as industry would be unable to function without power.

A look at this attack and ways to mitigate the same are provided in this report.

# Introduction {#introduction}

Ukraine is the largest country entirely situated in Europe. Ukraine has 24 regions, with a different power distribution company for each region. On December 23, 2015, residents of the three regions of Western Ukraine were subjected to a power outage due to hackers taking control of three control centres and disabling the power for hundreds of thousands of people. Before the Russian invasion of Ukraine started a war in 2022, the relations between the two nations have been strained since the annexation of Crimea, an island region of Ukraine with a majority Russian population in 2014\. Ukrainian authorities have tried putting the blame on Russia but there is not enough evidence to support any claim. Though the attack is attributed to a Russian Advanced Persistent Threat (APT) known as “**Sandworm**” and attacks did come from IP addresses allocated to the Russian Federation.

# The Victims {#the-victims}

The victims of this attack were:

1. **Power Control Centres:** Three control centres, namely Prykarpattyaoblenergo, Chernivtsioblenergo and Kyivoblenergo which serve the regions of Ivano-Frankivsk, Chernivtsi and Kyiv respectively, were the major victims of this attack. The attack resulted in the systems being faulty for months due to malicious firmware updates and the loss of remote control breakers due to this attack.   
     
   Around 30 substations under the Prykarpattyaoblenergo control centre alone were turned offline and the total number when including the other two control centres takes it to almost double the number.  
     
2. **Employees:** The employees of the Power Control Centres were also left in the dark after the hack also turned off the backup power for two of the locations. The hack also left some employees unable to login to their accounts as the hackers had changed the login credentials after gaining access to the system.  
     
3. **General Public:** Around 230,000 people living in the Ivano-Frankivsk,Chernivtsi and Kyiv regions of Ukraine were affected by the outage caused by this hack. The power was brought back on in approximately 6 hours.  
     
4. **Power Grids:** The attack was a first of its kind on a power grid infrastructure and exposed some vulnerabilities associated with it. The US power grid also uses some similar components to the Ukrainian one and could be vulnerable to the same kind of attack if a party dedicates some time to it. Surprisingly, some Ukrainian facilities were better protected from the cyber threats than US ones but still faced this attack.

# Tools and Technologies Used {#tools-and-technologies-used}

Some of the tools and technologies used in this attack are:

1. **Spear-Phishing:** IT staff and system administrators were targeted in a spear phishing campaign to install malware on their systems which provided a backdoor to the hackers. It gave the hackers access to employee credentials as well.  
2. **Scripting:** The files sent for the spear-phishing were Word files. When the file was opened, it prompted the victims to allow macros via a popup. If the victim approved it, it installed malware on their system.  
3. **Malware:** A malware called “**BlackEnergy3”** infects the systems if the victims comply with the pop up asking for permission to enable macros.  
4. **Malicious Firmware:** While the attack was happening, the hardware used was compromised by the use of malicious firmware updates that prevented operators from sending remote commands. This forced the operators to manually change any controls needed to run the system.  
5. **DoS:** When the attack started on the power systems, a telephone Denial of Service attack was simultaneously launched on the customer service lines of the power companies. This prevented them from knowing an attack was in progress for a while. A telephone Denial of Service attack works by spam calls hitting the company’s network.

# Timeframe of the Attack {#timeframe-of-the-attack}

* The attack itself started happening around 3:30 PM on December 23, 2015 and it lasted for a few hours.  
* Around 90 minutes after the attack started, a piece of malware called “KillDisk” which wipes files was run on the operator stations which made them inoperable.  
* The forensic data gathered for the investigation implies that the layout for the attack began at least six months before the attack actually occurred.

# Targeted Systems {#targeted-systems}

Systems that were targeted in this attack include:

* **Network:** The corporate network of the power centres was breached by using the malware planted by the phishing campaign.  
* **Hardware:** Hardware that controls the breakers was compromised by using malicious firmware to prevent operators from using them.  
* **Storage:** The hard drives were wiped by a KillDisk malware to remove traces of the attack from the system.  
* **Customer Service:** A telephone Denial of Service attack was launched on the customer service phone numbers to delay the operators knowing about the attack.

# Attackers Motivation {#attackers-motivation}

The attackers were determined to be “**Sandworm**”, a Russian Advanced Persistent Threat (APT). The motivation seems to be a state sponsored attack of cyber-warfare by Russia on Ukrainian Infrastructure. There wasn't enough evidence to support this in a court but the events preceding and following the attack does make that a possibility.   
But some Ukrainian activists had stopped the power going to Crimea, the Ukrainian island annexed by Russia just days before this attack. This power blockage might have been the catalyst that drove the December cyber attack. 

The DoS attack on the telephone service also came from numbers allocated to the Russian Federation and were tracked to Moscow, Russia’s capital. This could suggest some involvement of the Russian state in the attack.

The results from the attack also indicate it was more of a message than an actual attack to the infrastructure. A US demonstration in 2007 had shown that power generators could be physically destroyed by getting the access the attackers in Ukraine had and just running 21 lines of malicious code. So, not using such a big vulnerability indicates that it was meant more as a message.

# Outcome of the Attack {#outcome-of-the-attack}

The attack caused a power outage that affected approximately 230,000 people in Western Ukraine for a few hours. Although power was restored by the end of the day, the operators' ability to remotely control the breakers remained unfixed even in 2022\. As a result, operators have had to manually turn the switches on and off as needed.

The attack was also the first of its kind in the world on power infrastructure. It showed weaknesses in a system that is essential to everyday life. The consequences of such an attack on US infrastructure could result in billions of damages if successful. Thus, it showed an area of cyber security that has often been neglected.

# Mitigation Techniques {#mitigation-techniques}

Some mitigation techniques could have been used to prevent this type of attack and they are:

1. **Multi Factor Authentication:** The lack of multi factor authentication was a major cause for this attack. Due to the spear-phishing campaign by the attackers, they were able to gain credentials from operators in the company network which provided them with the access required to do all the damage they did. Requiring a second token to login would have made it almost impossible for the attackers to gain the access they did.  
2. **Update to Infrastructure Vulnerabilities:** A lot of essential infrastructure uses software and firmware that is quite old in technology sectors. Due to this, they have a lot of vulnerabilities. Taking steps to protect against this is needed.  
3. **Disabling Macros:** The macros feature on the Word software provided attackers with an entry point that allowed the installation of malware. Disabling such avenues of attack can help in preventing any future ones.  
4. **Employee Education:** Employees need to be educated on the best safety practices. Protecting themselves from phishing and social engineering attacks is imperative to keeping the whole organisation safe.

# Recommended Security Controls {#recommended-security-controls}

Several security controls can be implemented to mitigate the future risks. These include:

1. **Program Whitelist:** A list of only necessary programs that have any authority to run on the systems is required. This would prevent scripting attacks that can infuse malware into the organisation network.  
2. **Network Traffic Restriction:** Restricting the company network from outside is required to prevent an attacker from gaining access even when they have credentials for company authentication. Additionally, this would also prevent Denial of Service attacks from outside the company from being effective.  
3. **Multi-Factor Authentication:** The best security option is to add a second method to authenticate the employees. This would prevent attackers who have login credentials from having access.  
4. **Role Based Access Control:** Only maintenance engineers and required personnel should have access to privileges that allow for firmware or software installation. This will make it harder for attackers to affect the system even if they get access to it.

# Conclusion {#conclusion}

The 2015 Ukraine power attack is a proof of concept attack more than anything. The ability to interfere with power that is essential for the public and industry from outside the country by malicious agents is terrifying. The use of such an attack in a confrontation between two countries can be catastrophic and can lead to loss of life and astronomical losses. Using the mitigation techniques is imperative to keep the attackers at bay. 

# Citations {#citations}

1. *Ukraine.* (n.d). Wikipedia. Retrieved August 24, 2024\. [Ukraine \- Wikipedia](https://en.wikipedia.org/wiki/Ukraine)  
2. *2015 Ukraine Power Grid Hack*. (n.d). Wikipedia. Retrieved August 24, 2024\. [2015 Ukraine power grid hack \- Wikipedia](https://en.wikipedia.org/wiki/2015_Ukraine_power_grid_hack)  
3. *2015 Ukraine Electric Power Attack.* (06 October 2023). MITRE ATT\&CK. Retrieved August 24, 2024\. [2015 Ukraine Electric Power Attack, Campaign C0028 | MITRE ATT\&CK®](https://attack.mitre.org/campaigns/C0028/)  
4. Zetter, Kim. *Inside the Cunning, Unprecedented Hack of Ukraine's Power Grid.* (03 March 2016). Wired. Retrieved August 24, 2024\. [Inside the Cunning, Unprecedented Hack of Ukraine's Power Grid | WIRED](https://www.wired.com/2016/03/inside-cunning-unprecedented-hack-ukraines-power-grid/)  
5. Pollard, Miles. *A Case Study of Russian Cyber-Attacks on the Ukrainian Power Grid: Implications and Best Practices for the United States.* (23 April 2024). Pepperdine University. Retrieved August 24, 2024\. [A Case Study of Russian Cyber-Attacks on the Ukrainian Power Grid: Implications and Best Practices for the United States](https://digitalcommons.pepperdine.edu/cgi/viewcontent.cgi?article=1216&context=ppr#:~:text=2016%20Electrum%20Hack%20on%20Ukraine,systems%20\(Buchana%2C%202022\))