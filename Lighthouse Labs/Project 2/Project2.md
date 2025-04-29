### Project Description

This is your project activity for this course\! In this project, you will create a formal report outlining your findings for the company in the case study Cat Scan II given a set of pre-selected sensors. While working on this report, you will focus on coming up with a rationale of prioritization, based on the sensor used and the IoCs that they assist in monitoring. You will prioritize based on the prioritization of the asset being monitored, vulnerabilities, threats, tactics, techniques, and risk severity to the organization, and prepare monitoring recommendations for the company in the case study.

## Instructions

Using the information you have collected on your own and from group & class discussions, as well as using the table given below, complete the case study tasks given here and then write a formal report outlining your findings for the Big Dog organization.

Note

On communicating with Cat and reviewing the Big Dog environment, the following table has been started; the column headings of the table have been explained here:

* Sensor: Generic sensor name  
* Description: A short non-technical description of the sensor  
* System: The endpoint that the sensor will be monitoring  
* IoCs: The Indicators of Compromise that the sensor is expected to monitor  
* Rationale: Why this sensor may have been chosen, linked to MITRE or some other framework information  
* Priority: Based on the nature of Risk/IoC/SIL, etc. SIL will be a factor in priority but does not need to be same.  
* Thresholds/ Assumptions: Based on what is monitored, do we monitor for a high condition, a low condition or both and why? This column can also be used to specify any assumptions made. You do not need to give specific numbers or percentages

Note

Sample explanations/ examples are given in the table in the *bold and italic format*.

| Sensor | Description | System | IoCs Associated (May be more than 1\) | Rationale | Priority | Thresholds /Assumptions |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| *HTTP Load Time* | *Monitors the time it takes for the page to load.* | *Linux* | *May be used to indicate Malicious Redirects, DDoS Attacks or Content Injection* | *Unexpected changes in load time can indicate anomalies or performance-related issues that could be indicative of a security breach or compromise* | *Medium (SIL of medium, see assumptions)* | *The sensor will monitor for high conditions, which are well above the average http load time. The SIL is assumed to be medium based on the fact that BIG DOG does NOT have a large Web Presence, the linux web server is internal and therefore not exposed to http traffic and there is only one outward facing server. Therefore there is a moderate impact on CIA (specifically Availability)* |
| HTTP Load Time |  | Linux |  |  |  |  |
| MySQL Database Query Sensor |  | Linux |  |  |  |  |
| SSH Sensor |  | Linux |  |  |  |  |
| Antivirus Status Sensor |  | All |  |  |  |  |
| File Sensor |  | Linux |  |  |  |  |
| Windows Event Log Sensor |  | Windows11 |  |  |  |  |
| Windows Event Log Sensor |  | Windows11 |  |  |  |  |
| Bandwidth Usage Sensor |  | All |  |  |  |  |
|  |  |  |  |  |  |  |

### Case Study Tasks

* Cat has provided a list of sensors (in the table given above) she wishes to add. Complete the table\!

Note

Revisit the column headings explanations given above as you try and complete the table.

### Case Study Report

Instruction

Once you have completed all the tasks, create a formal report; make sure you include the following elements and information in your report:

* Include an executive summary and overall conclusions.  
* The completed table.  
* List and explain the IoCs as they relate to vulnerabilities and risks/threats covered by the sensors.  
* Explain why you have prioritized them the way you have(set SIL) (this includes the risks and the company’s associated tolerances, and threats and the associated CIA impacts they may cause).  
* Specify what alert thresholds need to be set and why. You do NOT need to specify numbers, just if high, low or both conditions evaluate to a potential compromise.  
* Tie your findings and recommendations together with industry standard framework and tool references.

Instruction

Follow the template given below to prepare the formal report.

* Title: Title of the report should be Cat Scan II Big Dog.  
* Executive Summary: A short, one or two paragraph summary explaining what you have done. Include information about the top five SILs and the sensors and thresholds you are monitoring or recommending.  
* Table of Sensors: Complete the table as required; give appropriate explanation wherever required. To find information on what each sensor does try to look up the technology/protocol that the sensor is monitoring and understand what should be monitored for that piece of technology to detect a potential cyber attack.  
* Discussion Section: A discussion of each of the connections between the sensors, IoCs and thresholds.  
* Recommendation Section: A recommendation section where you should recommend how the client might enhance the security of their systems (for example added sensors); you must cite industry best practices as you make your recommendations.

## Project Outcomes

By the end of this project, you should have created a report which includes:

* Completed table of sensors, each described, with suggested alert thresholds, and tied to appropriate vulnerabilities/risks and IoC(s) supported by industry standard frameworks and tools  
* A prioritized list of sensors and any other recommended monitoring mitigations, with alert threshold suggestions and associated IoCs and risks supported by industry standard frameworks and tools  
* Explanations and rationales for the decisions you have made while selecting alert thresholds, and recommending security posture and monitoring improvements