### Project Description

You’ve just been tasked with an important project by your company’s security team: build a powerful log monitoring tool that can detect suspicious activity before it becomes a full-blown security incident.

Your manager wants this tool to be simple, effective, and—most importantly—open-source so that other security teams around the world can use and improve it. Your job is to develop the first version of this tool, and if it’s good enough, it might just become a must-have in the cybersecurity community.

Introducing LogHawk: a script-based log analysis tool designed to quickly scan logs for security threats, system errors, and unusual activity.

### What LogHawk Needs to Do

Your tool should:

* ✅ Monitor log files for security threats and errors.  
*   
* ✅ Detect patterns using \`grep\`, regex, or Python’s \`re\` module.  
*   
* ✅ Generate alerts when something suspicious is found.  
*   
* ✅ Run automatically using cron so logs are checked regularly.  
*   
* ✅ Allow users to customize search rules via a config file or command-line arguments.


Your goal is to create a lightweight, easy-to-use security tool that automates log analysis and helps security teams catch potential threats faster. Some log files have been provided to you as a reference, and can be downloaded [here](https://github.com/lighthouse-labs/cybersec-program-files/tree/main/Project%20LogHawk).

Warning

The log files provided are examples of potential log events you might want to search for in your code. Keep in mind that not every log event is malicious, and you don't need to identify every single type of suspicious activity from the files. Focus on developing your tool to detect key patterns or behaviors that could indicate potential issues, but don't worry if you don't catch every event in the examples.

### Threats LogHawk Should Catch 🔎

Your company’s security team has identified some key threats to watch for:

🛑 Too Many Failed Logins – Possible brute-force attack\! Watch for multiple 401 Unauthorized errors in web server logs or failed SSH login attempts in /var/log/auth.log.

⚠️ Unusual Traffic Spikes – A single IP hammering your servers? Might be a bot or a vulnerability scanner.

🔥 Critical System Errors – If ERROR or CRITICAL messages are flooding the logs, something could be failing fast.

🦠 Suspicious Script Activity – Unexpected cron jobs or unauthorized script executions? That’s a red flag for malware.

These are just a few starting points. Your company wants LogHawk to be flexible enough for users to define their own search rules.

### Project Deliverables

1️. The LogHawk Code Write a Python or Bash script that can:

* Scan a log file for predefined patterns.  
* Output the findings in a clear, readable format.

Note

You can either hardcode the file name into your script, or allow users to specify the name of the file.

2\. The LogHawk Repo Since LogHawk is going to be open-source, it's super important to have a well-organized repo that anyone (especially other security analysts) can easily understand and use. A clear and easy-to-follow README is key to making sure others can quickly jump in and make the most out of your project.

Here’s what you should include in your README:

* What LogHawk does and why security teams need it: Let people know what LogHawk is all about. For starters, you could say, “LogHawk is a tool designed to help security teams automatically monitor and analyze log files for suspicious activity like failed login attempts or unauthorized access.”  
* Installation steps: Help others get started easily\! Make sure the setup process is clear, and include all the necessary steps. For example: “Before using LogHawk, make sure you have Python 3 installed. You can install it by running: sudo apt-get install python3”

  ### Project Requirements

* Executive Summary  
* Code should include essential commands with explanatory comments.  
* Provide sample output demonstrating the script's execution results (use screenshots from your virtual environment).  
* Document the monitoring process thoroughly.  
* Identify flag elements for manager alerts, linked to Indicators of Compromise (IoCs).  
* Utilize both Bash and Python languages.  
* Integrate the usage of Cron and Windows Task Scheduler to your workflow.

