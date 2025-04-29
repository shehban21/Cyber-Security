# 

| NETWORK ADMINISTRATION |
| :---: |

# 

[NETWORK ADMINISTRATION	1](#network-administration)

[Executive Summary	3](#executive-summary)

[NETWORK DEVICES INFORMATION	4](#network-devices-information)

[INFORMATION COLLECTION METHODOLOGY	12](#information-collection-methodology)

[NETWORK TOPOLOGY	17](#network-topology)

[CITATIONS	19](#citations)

# 

# Executive Summary {#executive-summary}

This project was conducted in two phases to assess and document the network environment of a virtual lab setup, utilizing network scanning and traffic analysis tools.

**Part 1: Network Scans and Information Collection**  
The first phase focused on turning on all virtual machines (Windows11, Linux Server, and Kali OpenVAS), performing comprehensive network scans using Nmap, and capturing network traffic with Wireshark. Each device’s IP address, MAC address, hostname, operating system details, open ports with services, and ARP Ping Scan times were collected. Wireshark captures provided additional verification of device MAC addresses and evidence of network activity during the scans. Data was cross-validated directly on each virtual machine to ensure accuracy.

**Part 2: Reporting and Analysis**  
The second phase involved documenting all findings in an organized, clear format. Each device’s information was presented in a structured table for easy reference. A network topology diagram was created, illustrating current network connections and providing segmentation recommendations to improve security posture, suggesting VLAN implementation and IP address range adjustments based on detected services. The report also detailed the methodology of data collection, including step-by-step explanations and screenshots from Wireshark and Nmap scans to validate the processes used.

By completing this project, a strong understanding was demonstrated of network discovery, operating system fingerprinting, traffic analysis, and network design improvements. This comprehensive approach ensures better network security practices and documentation standards.

# NETWORK DEVICES INFORMATION {#network-devices-information}

Running a scan on our network shows us there are 6 hosts up out of a possible 256\. Upon further inspection of the data provided by our search, we can list the devices as follows:

1. The first device we have is our local device which is running the Virtual Machines on it. In my case, it is a MacBook Pro and it has been assigned the IP address 1\.  
   1. Machine Designation \- MacBook Pro (The actual hardware)  
   2. Device Host Name \- MACBOOK-PRO  
   3. IP Address \- 192.168.219.1  
   4. MAC Address \- FA:4D:89:69:F5:65  
   5. OS & Version \- No exact OS matches from nmap. TTL gives us a Unix/Linux option  
   6. Open Ports with Associated Services:  
      1. 21/TCP for FTP  
      2. 80/TCP for HTTP  
      3. 443/TCP for HTTPS  
      4. 3306/TCP for MySQL  
      5. 5000/TCP for UPNP  
      6. 7000/TCP for AFS3-Fileserver (AirTunes)  
      7. 7070/TCP for Realserver (AnyDesk)  
   7. ARP Ping Time: 0.05 Sec  
   8. Table

| Layer | Address/Port |
| :---- | :---- |
| Data Link Layer | MAC Address \- FA:4D:89:69:F5:65 |
| Network Layer | IP Address \- 192.168.219.1 |
| Transport Layer | Ports \- 21, 80, 443, 3306, 5000, 7000, 7070 |

![Imgur](https://i.imgur.com/2TmpDtk.png)
![Imgur](https://i.imgur.com/C5YgFZO.png)
The above 2 screenshots show the nmap scan report for IP Address “192.168.219.1” which is the hardware MacBook Pro the VM is running on.

2. The next 3 devices are the Virtual Machines we’re checking for. The second device is as follows:  
   1. Machine Designation \- Ubuntu  
   2. Device Host Name \- linux-server  
   3. IP Address \- 192.168.219.128  
   4. MAC Address \- 00:0C:29:14:F5:60  
   5. OS & Version \- Linux 4.15 \- 5.8  
   6. Open Ports \- 80/TCP for HTTP  
   7. ARP Ping Time: 0.04 Sec  
        
   8. 

| Layer | Address/Port |
| :---- | :---- |
| Data Link Layer | MAC Address \- 00:0C:29:14:F5:60 |
| Network Layer | IP Address \- 192.168.219.128 |
| Transport Layer | 80 |

![Imgur](https://i.imgur.com/l5INh4B.png)
This screenshot shows the nmap scan report for the IP address “192.168.219.128” which is our Ubuntu Linux VM.

3. The third device is as follows:  
   1. Machine Designation \- Windows 11  
   2. Device Host Name \- DESKTOP-LHL  
   3. IP Address \- 192.168.219.132  
   4. MAC Address \- 00:0C:29:49:EC:D9  
   5. OS & Version \- Windows 11 21H2  
   6. Open Ports \- 80/TCP for HTTP  
   7. ARP Ping Time: 0.05 Sec  
        
   8. 

| Layer | Address/Port |
| :---- | :---- |
| Data Link Layer | MAC Address \- 00:0C:29:49:EC:D9 |
| Network Layer | IP Address \- 192.168.219.132 |
| Transport Layer | 80 |

![Imgur](https://i.imgur.com/HWIZQEu.png)
![Imgur](https://i.imgur.com/Ro4MCMT.png)
The above two screenshots show the nmap scan report for the IP address “192.168.219.132” which is our Windows 11 VM.

4. The fifth device is as follows:  
   1. Machine Designation \- Kali Linux  
   2. Device Host Name \- kaliopenvas  
   3. IP Address \- 192.168.219.131  
   4. MAC Address \- 00:0C:29:B5:17:0F  
   5. OS & Version \- Kali Linux  
   6. Open Ports \- None  
   7. ARP Ping Time: Not Done by nmap  
        
   8. 

| Layer | Address/Port |
| :---- | :---- |
| Data Link Layer | MAC Address \- 00:0C:29:B5:17:0F |
| Network Layer | IP Address \- 192.168.219.131 |
| Transport Layer |  |

![Imgur](https://i.imgur.com/mYKPzmx.png)
The above screenshot shows the nmap scan for the IP address “192.168.219.131” which is our Kali Linux VM and the same device it is running on.

# INFORMATION COLLECTION METHODOLOGY {#information-collection-methodology}

This screen capture shows us the local IP address and the subnet mask which gives us an idea about which IP address we need to use to run our NMAP procedure.

![Imgur](https://i.imgur.com/UrDvI7k.png)
This screenshot shows the IP address we retrieved on the KaliLinux machine \[2\].  
Running the nmap command on the IP address and supplying the subnet mask enables it to scan all the available IP addresses and find the active ones.![Imgur](https://i.imgur.com/M7YUoHW.png)
![Imgur](https://i.imgur.com/l0fcM06.png)
The above screenshots show the results of the command ”nmap 192.168.219.0/24”.

As we can see from this, there are 6 hosts active on our Virtual Machine Network. Next, we use the nmap command on each of these IP addresses to check what devices they are and what ports are open on them. The command we use is:

nmap \-T4 \-A \-v IPADDRESS where IPADDRESS is replaced by one of the IP addresses we want to look into.

nmap is the command we use to map our network. It’s called the Network Mapper. The \-T flag indicates the Timing Options with 4 denoting an Aggressive scan time. \-A enables OS detection, version detection,script scanning and traceroute. \-v enables the verbose mode which gives a more detailed output. The IP address is the device identifier we use to target specific devices. 

You can see on the images we included in the first device in our Network Devices Information section the scan we ran on the IP address “192.168.219.1” which represents our actual hardware device MacBook Pro. As you can see, it shows the ports that are open on it currently. Port numbers are generally fixed for the service they provide. The TCP  port number 80 for example is used for HTTP communication which runs most of our internet. The port 443 is reserved for HTTPS which is used for secure communication with websites that have SSL/TLS security. Port number 21 is used for FTP which is used for transferring files. On this device, you can see a couple ports which might not be on others. The port 3306 is open for mysql which could be due to a XAMPP server running on the device that has a mysql server on it configured to run on that port. There’s also a port 7000 which on further inspection is used by a service called AirTunes. It looks like an Apple service used to communicate with iTunes. Another fascinating port is 7070 which indicates it’s from a program called AnyDesk. It is a remote desktop server generally used for remote IT support but some nefarious elements have used it to run scams on unsuspecting individuals, especially older ones, who are less tech savvy. I have observed that after quitting the application and running the nmap again indicates the port as closed.

On this device, nmap has been unable to determine the OS or the Device Name. I used another command called nmblookup which can get the device details to get these. If we’ve been unable to retrieve this from nmap like we did on Ubuntu and Kali, we’ve retrieved the data from the respective devices. The following information has also been verified on the corresponding devices. \[3\]  
![Imgur](https://i.imgur.com/HYhnKf6.png)
![Imgur](https://i.imgur.com/7ZhWat9.png)

We have also used WireShark to capture the packets that travel on our device that ran these mapping commands. These give us an insight into the communication processes used by our devices to connect to each other. The wireshark screenshots are as follows:

![Imgur](https://i.imgur.com/XB8eUsr.png)
The above screenshot shows the communication between our nmap tracker KaliLinux device (192.168.219.131) and the MacBook Pro hardware(192.168.219.1). It also shows all the OSI layer addresses including the open port 7070\. There are other open ports on this device all listed in the table above including the services they are used for. \[4\]

![Imgur](https://i.imgur.com/tS7Dk9M.png)
This screenshot shows the communication between our nmap tracker KaliLinux device (192.168.219.131) and this VMWare software as a device(192.168.219.2). It also shows all the OSI layer addresses and these greyed out and red packet numbers indicate all the failed communication with ports. The conversation completeness on all of these is “Incomplete”.

![Imgur](https://i.imgur.com/9sTCZBN.png) 
This screenshot shows the communication between our nmap tracker KaliLinux device (192.168.219.131) and this Ubuntu Linux VM(192.168.219.128). It also shows all the OSI layer addresses including the open port 80\.

![Imgur](https://i.imgur.com/BLWtT4B.png)
This screenshot shows the communication between our nmap tracker KaliLinux device (192.168.219.131) and this Windows VM(192.168.219.132). It also shows all the OSI layer addresses including the open port 80\. 

# NETWORK TOPOLOGY {#network-topology}

![Imgur](https://i.imgur.com/WIu4RKp.png)
This screenshot is the network topology currently.

I believe this is what the current network topology looks like. All of the Virtual Machines should have their own firewalls which connect to the VMWare NAT. VMWare is working on the MacBook Pro hardware which is connected by its own hardware network card to the actual router hardware. This hardware is used to connect to the Internet. All the devices in the VMWare, including the VMWare itself, has the IP Address of the format 192.168.219.0/24. So it makes sense that VMWare has made a VLAN which is running all these devices on its Virtual Network. 

This creates some noise on the Linux systems. When running a wireshark capture, we can see the Windows 11 VM broadcasting a lot of communication even when nothing is actively using that connection.    
![Imgur](https://i.imgur.com/lyvkifG.png)
This screenshot shows the communication sent by the Windows VM over the network.  
A better network topology would be achieved by isolating the Windows 11 VM which would reduce the noise on the KaliLinux device. That would give us a better look at what is going on in our network.  
![Imgur](https://i.imgur.com/cUzSRm8.png)
This screenshot shows the updated network topology which should reduce the noise on Linux systems when tracking network activities.

# CITATIONS {#citations}

1. nmap Cheat Sheet \- Contains the commands we used to do nmap scans \- [https://cdn.comparitech.com/wp-content/uploads/2019/06/Nmap-Cheat-Sheet.pdf](https://cdn.comparitech.com/wp-content/uploads/2019/06/Nmap-Cheat-Sheet.pdf)  
2. ip a \- [https://www.cyberciti.biz/faq/linux-ip-command-examples-usage-syntax/](https://www.cyberciti.biz/faq/linux-ip-command-examples-usage-syntax/)  
3. nmblookup \- [https://www.samba.org/samba/docs/current/man-html/nmblookup.1.html](https://www.samba.org/samba/docs/current/man-html/nmblookup.1.html)  
4. WireShark \- [https://www.wireshark.org/](https://www.wireshark.org/)  
5. Network Topology \- Lighthouse Labs \- [https://web.compass.lighthouselabs.ca/p/cyber/days/w01d2/activities/2792](https://web.compass.lighthouselabs.ca/p/cyber/days/w01d2/activities/2792)
