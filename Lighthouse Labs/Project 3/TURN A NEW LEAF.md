

# TURN A NEW LEAF {#turn-a-new-leaf}

LOG MONITORING WORKFLOW

# TABLE OF CONTENTS {#table-of-contents}

[**TURN A NEW LEAF	1**](#turn-a-new-leaf)

[**TABLE OF CONTENTS	2**](#table-of-contents)

[**EXECUTIVE SUMMARY	3**](#executive-summary)

[**WORKFLOW	3**](#workflow)

[**PROGRAMMING TOOLS	5**](#programming-tools)

[**OUTPUT ANALYSIS	15**](#output-analysis)

[**POTENTIAL ITERATIONS	16**](#potential-iterations)

[**CONCLUSIONS	17**](#conclusions)

[**REFERENCES	18**](#references)

# EXECUTIVE SUMMARY {#executive-summary}

Turn a New Leaf is a non-profit organisation which provides support to youth in rural areas to find employment. They have a system which requires the members to login every Thursday and provide updates regarding their employment journey. They use Windows and Linux machines and have two web servers on their network.

This report looks at how to monitor logs for unusual network traffic and alert the management if there is an unusual number of failed logins. We’ll be using the number of 4xx errors faced by a particular IP address as a parameter to measure this. These errors are caused by a client mistake and could point to malicious agents brute forcing into the server.

We have also provided a way to automate this process. After automating it, the system will notify by a Slack message with an alert if there is an unusual amount of failed logins. This report includes documentation of how it was set up. This can prove useful in case any troubleshooting is needed. This can also be used to train new employees to alert them to these issues and what can be done to fix them.

# WORKFLOW {#workflow}

* Both the servers have Apache Logs which document all the IP addresses and the pages and files accessed by them. These server logs need to be monitored regularly to keep an eye on HTTP errors of the 4xx family. These codes represent client mishaps. It could mean a client making a mistake in the URL to access something or a malicious party probing the server to find vulnerabilities\[1\].   
* First step is to get all the logs in one place. Since there are two servers in this organisation, we can use SSH to transfer log files to one server where they can be monitored and alerts can be sent out accordingly.  
* Next, we need to filter the logs to only highlight unusual activity taking place on the network. Monitoring the full logs all the time can be taxing for even the most sophisticated system. So, keeping it as brief as possible is advantageous.  
* Once the anomalies have been filtered out, these files are fed to a Python script that can analyse and count infractions by IP addresses, which can be used to identify individual devices.  
* If the script finds a particular IP address with many counts of these errors, it can send an alert via Slack to the security team of the organisation who can then take steps to mitigate future activity from that device.  
* Since the members are required to update every Thursday on the system, the highest activity during the week would be on that day. So, this monitoring can be scheduled for midnight(00:00) on Friday as the best time to schedule these automations.  
* Scheduling these every week looks like the best option for the organisation.

# PROGRAMMING TOOLS {#programming-tools}

* Batch \- Batch is used in Windows to run commands that we normally use in the terminal.  
  ![Imgur](https://imgur.com/9WrVBIM)
  Batch file to copy log from Windows to Linux Server  
    
  The batch file we have programmed on our Windows Server only does one thing. It sends the log file to the Linux Server where we do most of our processing of the data.  
    
  scp refers to Secure Copy Protocol which is used to transfer files securely over the internet. scp usually requires the password of the user on the receiving device but we have set up a secure connection by using secure keys and configuring a secure connection between these two devices.  
    
  Here are the steps to set up that passwordless but secure connection:  
1. We run the command “ssh-keygen” on the source server, i.e. , the Windows Server. This generates a public/private rsa key pair. The path to the generated file is “.ssh/id\_rsa” in the folder where the command was executed.\[2\]

   ![][image2]

   ssh-keygen Result

   

2. The public key file is copied to the remote server where we want to send files to. The command for that is:  
   1. scp .ssh/id\_rsa.pub [user@ip.address](mailto:user@ip.address):\~/.ssh

      The user is the username on the remote server and the ip.address is the IP address of the remote server.\[2\]

      

3. Rename ‘id\_rsa.pub’ to ‘authorized\_keys’:  
   1. mv .ssh/id\_rsa.pub .ssh/authorized\_keys\[2\]  
4. Change permissions of ‘.ssh’ directory and ‘authorized\_keys’ file.:  
   1. chmod 700 ‘.ssh’ \- This permission allows the Owner to read, write and execute and no permissions to group or other.  
   2. Chmod 600 ‘.ssh/authorized\_keys’ \- This permission allows the Owner to read and write to this file and no permissions for anyone else.\[2\]  
5. Last thing to do is check if it works\[2\]

   

   

   

   

   

   

   

   

   

   

   

   

   

   

   

   

 


* Windows Task Scheduler \- Once this batch file is set up to do this task, we need to schedule it to do it on a regular basis. For this, we’ll make use of the Windows Task Scheduler.  
* There are some steps required to do the same\[3\]  
* First, open Windows Task Scheduler and click on Action \> Create Basic Task  
  ![][image3]  
  Step 1 in Windows Task Scheduler  
  Next, we schedule it to run weekly at midnight every Friday morning.![][image4]  
  Step 2 in Windows Task Scheduler  
* The action we select is “Start a program” which can be used to run our batch file.![][image5]Step 3 in Windows Task Scheduler  
* Finally, we select the program we want to run from the Browse button under “Program/script” and point it to our batch file. We also need to add the Start in value as the folder our Batch file exists in to make sure the terminal opens in that folder![][image6]  
  Last step in the Windows Task Scheduler  
* Now, we’re done with the Windows Server and move to the Linux one to do the analysis.\[3\]

* Bash \- Bash is the equivalent of Batch on Linux systems. It is used to run terminal commands in a batch by running them from one file.  
* This bash file does most of our heavy lifting in analysis. The first line describes the shell that will be used to run this script and is known as shebang\[4\]. Firstly, this script copies the log file from the local apache folder to the “logs” folder which also receives the file from the Windows Server.  
  ![][image7]  
  Bash script that aggregates both server logs and runs the python script later  
    
* Then, it navigates to the log folder and uses the “grep”\[5\] command to filter the logs and only show lines which contain errors that are “4xx” HTTP errors. These errors are generally caused by client error but a high number of these errors from the same IP address can indicate a malicious party trying to infiltrate but failing due to missing credentials\[1\].  
* Both the log files from the Linux and Windows server are filtered and combined in one file.  
* This file is then used by our Python script to analyse the data and provide the final report.

* Python \- Python is a high level programming language that is quite popular in Cyber Security to monitor and analyse log files.  
* The first few lines in our Python script are used to import prewritten components that make it easier for us to add features to our analysing Python script.  
  ![][image8]  
  Python script  
* The variable “pattern” defines the Regular Expression(regex) we’ll be using to filter IP addresses from our log.\[6\]   
* The regular expression we’ve used is very simple and could also accept “999.999.999.999” which is not a valid IP address. But, for the purpose of our script, the data it is filtering comes from Apache logs which would only have valid IP addresses in the first place.\[6\]   
* This script runs a “for” loop that opens the “log\_anomalies.txt” file, which contains our aggregated logs from our Servers. It looks for IP addresses and adds them to a list called “sus\_ips”.\[7\]  
* Then this script uses Counter to count the number of times an IP address has appeared in this log and filters out the ones that have a number below the minimum count referred to in the script earlier.\[8\]  
* Now that the results have been analysed, it’s time to output them. First, the IP addresses, the amount of times they have appeared and the day the script has added them to this file are written to a csv file that can be analysed at any time by the security section of the organisation.\[9\]  
* Lastly, in case IP addresses that have high occurrences of errors have been found by the script, it will send a message to the Slack channel specified by the organisation to alert the group responsible for security.\[10\]

![][image9]  
Results in the csv file outputted by the Python script.  
![][image10]  
Slack message sent by the python script bot on finding suspicious activity.

* Cron \- The last tool we use in this automated system is Cron, which is used to schedule tasks on a machine. It is similar to Windows Task Scheduler, but much more powerful.  
* The bash script we have programmed earlier is scheduled to run every Friday at midnight by this cron setup.  
  ![][image11]

	crontab scheduling

* First, we need to make sure the commands and scripts we’re running have permission to actually execute. If they don’t, we can change them by using the command “chmod”.\[11\]  
  ![][image12]  
  Giving appropriate permissions to files  
* Cron comes preinstalled on Linux in most cases. If it is missing, it can be installed by the following command:  
  * sudo apt install cron\[11\]  
* Next, it needs to be enabled and started to actually run anything. For that, it needs the following two commands to be run:  
  * sudo systemctl enable cron  
  * sudo systemctl start cron\[11\]  
* Once that is done, we can create a task to schedule it. For that, we need to run the following command:  
  * crontab \-e\[11\]  
* As seen in the screenshot that depicts the crontab scheduling, we schedule the script to run by specifying the schedule in cron’s format and referring to the file that contains the script.\[11\]

# OUTPUT ANALYSIS {#output-analysis}

![][image9]  
    Results in the csv file outputted by the Python script.

* The output from the automated process we’ve set up for the organisation is all in the csv file “ips.csv” in the “Logs” folder on the Linux Server.  
* This file contains the IP addresses and the amount of “4xx” HTTP errors generated by them while trying to access the two servers of the organisation.  
* If the script finds any IP addresses that have more than 5 errors generated by them in a particular week, it will add them to the csv file.  
* This data can be used by the Cyber Security division of the organisation to investigate the cause of these anomalies and determine if there is any malicious activity related to the IP addresses flagged by this automated process.  
* If the script does find any of these suspicious variables, it will notify the organisation by a Slack message, which is instantaneous after the script has run.  
* From the sample log files we have used to run these tests, we can see in the output there is an IP address that has been flagged 60 times, which seems quite suspicious. That IP address needs to be investigated more by monitoring its activity in WireShark or other monitoring systems.  
* If these continue, the Cyber Security team can ban the IP address and remove its access from the servers.

# POTENTIAL ITERATIONS {#potential-iterations}

* Smarter flagging \- Over time, with the knowledge gained from analysing the outputs, settings on these scripts can be tweaked to eliminate unnecessary data and reduce the time required to analyse these logs.  
* Better Regular Expression \- The regular expressions we’ve used for both the bash file to filter 4xx error codes and the python file to filter IP addresses could use better versions.  
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
  


  # CONCLUSIONS {#conclusions}

From this report, it can be seen that programming can really help in automating some mundane tasks like log monitoring and provide data that might be missed by the human eye. This report provides a look to the Turn a New Leaf organisation’s workflow to monitor for unusual network activity on their server. 

An Indicator of Compromise(IoC) for this organisation can be a particular IP address triggering a lot of “4xx” HTTP errors. These errors generally are client mistakes like wrong URL typed in or trying to access a page without logging in,etc. A couple of these errors triggered by an IP address does not have to mean there’s malicious activity. But a large number of occurrences from the same IP address can point to probing by a malicious party.

This data can then be used to analyse more activity that can be monitored by the Cyber Security team and especially focusing on the IP addresses flagged by the monitoring scripts. If that investigation does provide evidence of malicious activity, the IP address can be banned by including it in Firewall policies of the organisation and preventing further access.

To conclude, these programming tools can really streamline the process of monitoring data, especially when dealing with today’s network traffic conditions.

# REFERENCES {#references}

1. List of Error Codes \- Wikipedia \- [https://en.wikipedia.org/wiki/List\_of\_HTTP\_status\_codes\#4xx\_client\_errors](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_client_errors)  
2. Tips \- Using scp without password \- Medium \- DaBeen Yi \-[https://dabeen.medium.com/tips-using-scp-with-password-bd2ed6d9aecd](https://dabeen.medium.com/tips-using-scp-with-password-bd2ed6d9aecd)  
3. Run a batch file with Windows task scheduler \- StackOverflow \- Ghazi \- [https://stackoverflow.com/questions/4437701/run-a-batch-file-with-windows-task-scheduler](https://stackoverflow.com/questions/4437701/run-a-batch-file-with-windows-task-scheduler)  
4. Are You Ready for Your First Script? \- Compass \- [https://web.compass.lighthouselabs.ca/p/cyber/days/w03d4/activities/2922](https://web.compass.lighthouselabs.ca/p/cyber/days/w03d4/activities/2922)  
5. Grep Command in Linux – Usage, Options, and Syntax Examples \- freecodecamp \- [https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/\#:\~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use).  
6. How to Find or Validate an IP Address \- Regular Expressions Info \- [https://www.regular-expressions.info/ip.html](https://www.regular-expressions.info/ip.html) \- Slight modification made to the regular expression referred here to fit the organisation’s data  
7. Python \- Add List Items \- W3Schools \- [https://www.w3schools.com/python/python\_lists\_add.asp](https://www.w3schools.com/python/python_lists_add.asp)  
8. How do I count the occurrences of a list item? \- StackOverflow \- User52028778 \- [https://stackoverflow.com/questions/2600191/how-do-i-count-the-occurrences-of-a-list-item?answertab=trending\#tab-top](https://stackoverflow.com/questions/2600191/how-do-i-count-the-occurrences-of-a-list-item?answertab=trending#tab-top)  
9. CSV Reading and Writing \- Python Docs \- [https://docs.python.org/3/library/csv.html](https://docs.python.org/3/library/csv.html)  
10. Slack Bot \- PKM \- Shehban Patel  
11. How to Create a Cron Job in Linux: Ubuntu Cron Job \- BlueVPS \- [https://bluevps.com/blog/how-to-create-a-cron-job-in-linux-ubuntu-cron-job](https://bluevps.com/blog/how-to-create-a-cron-job-in-linux-ubuntu-cron-job)
