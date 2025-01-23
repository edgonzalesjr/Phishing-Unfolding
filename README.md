## Objective

To equip with the practical skills required to respond to and investigate a live phishing attack within a corporate network. Actively monitor and analyze real-time security alerts, identifying key malicious activities such as PowerShell executions, reverse shell connections, and suspicious DNS requests. Develop the ability to prioritize and investigate alerts, utilizing advanced cybersecurity tools like SIEM and virtual machines for in-depth analysis. Document findings in detailed case reports, refine their incident response and reporting skills. To gain a comprehensive understanding of how phishing attacks unfold in real-time and how to effectively mitigate and document such incidents in a fast-paced, high-pressure environment.

### Skills Learned

- Alert Management & Prioritization
  - Prioritizing and investigating alerts based on severity (critical, high, medium, low).
  - Gaining proficiency in understanding alert contexts and determining the most critical alerts to investigate first.
- Investigating & Validating Alerts
  - Improving skills in recognizing true positives and false positives.
  - Using security tools to validate suspicious activities, correlating log data from different sources (e.g., SIEM, sysmon logs) to verify alerts.
- Hands-on Use of Security Tools    
  - Effectively utilizing SIEM to search and analyze security logs and events for indicators of compromise (IOCs).
  - Using virtual machines (VMs) for secure and isolated analysis of email attachments and potential threats.  
- Incident Documentation & Reporting    
  - Creating clear, concise, and well-organized reports that document the findings from security investigations.
  - Clearly categorize alerts as true positives or false positives. Document the steps taken during the investigation for future reference.
- Data Exfiltration & Attack Chain Analysis
  - Identifying the signs of data exfiltration and privilege escalation during a live attack scenario. (e.g., use of PowerShell, file transfers).    
  - Track and document attack chains as they happen. Connect different stages of the attack for complete incident analysis.

### Tools Used

- Splunk SIEM: Used for querying logs, filtering events, and correlating data from multiple sources to verify the legitimacy of alerts.    
- Analyst Workstation (VM): A dedicated virtual machine used to safely analyze suspicious email alerts and attachments, with tools for reviewing potentially dangerous files and performing incident analysis in a secure environment.

## Practical Exercises

- Low Alert
<p align="center">
<img src="https://imgur.com/thfKKZQ.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/0kheHlT.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>On the Dashboard, you can view the status of alerts. The Alert queue provides a breakdown of the reported alerts.</b>
<br/>

<p align="center">
<img src="https://imgur.com/raoWABU.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/AoNqbkH.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>When investigating alerts, it's best to sort them by severity. Start with critical alerts first. If there are no critical alerts, check for high alerts next.</b>
<br/>

<p align="center">
<img src="https://imgur.com/izFB0go.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/dFZ0PZn.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>We will have one low alert, review the descriptions, and take ownership.</b>
<br/>

<p align="center">
<img src="https://imgur.com/ee5pmbO.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Let's proceed with using Splunk SIEM. Please check the Data Summary for available sources.</b>
<br/>

<p align="center">
<img src="https://imgur.com/091qVBv.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/WpD41zF.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/GdIqX8M.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/zuY1TPR.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/dyqowsm.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/QtBLPcR.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Search for the process name. Taskhostw.exe is a system file associated with the Windows operating system. It stands for "Task Host for Windows," and its primary function is to launch Windows services that rely on dynamic link libraries (DLLs) during the computer's boot-up process. This file appears legitimate, as it is located in the C:\Windows\System32 folder and does not spawn any other processes.</b>
<br/>

<p align="center">
<img src="https://imgur.com/jl4vogN.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/10V7Z6T.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/10V7Z6T.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/cF967eG.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Document the case and close the alert.</b>
<br/>

- High Alert
<p align="center">
<img src="https://imgur.com/c0g0VJb.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>We will have one high alert, review the descriptions, and take ownership.</b>
<br/>

<p align="center">
<img src="https://imgur.com/53GT9dS.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/y2rL8gh.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/BzjemIG.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Let's check the Splunk SIEM for the process name. It is suspicious that the parent process name is powershell.exe and it was launched from the Downloads folder with a command line containing a base64 string.</b>
<br/>

<p align="center">
<img src="https://imgur.com/9nhK216.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Let's examine why powershell.exe is the parent process of nslookup.exe. The parent process ID of Powershell is 3728. Several instances of Powershell have been executed.</b>
<br/>

<p align="center">
<img src="https://imgur.com/zlSAt9f.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/SPmkKdC.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Since PowerShell.exe is involved in suspicious activity, we should investigate all events related to this executable. PowerShell was used to connect to a remote machine and download a script named Powercat.ps1. This utility tool allows for data transmission over TCP, UDP, DNS, and assists in payload generation. It was launched to connect to a command and control server at the ngrok.io domain.</b>
<br/>

<p align="center">
<img src="https://imgur.com/NimCeI9.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/qPknVma.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/QWcbg4B.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/eSN1tfa.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/dAdWLw5.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/yq9G1dm.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/3B2OLBM.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/rSIvqx9.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/yorFAfK.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/hOKVLit.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/v99S48G.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>It launched another process, systeminfo.exe, to retrieve information about the machine, logged-in user, and privileges. Then, it enumerated the users and local groups and downloaded the PowerShell script. There were processes created that accessed the network file share, using Robocopy to copy the files from the share. After that, it deleted the created file share, compressed the files, and then started to exfiltrate the data.</b>
<br/>

<p align="center">
<img src="https://imgur.com/hgsEMXz.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/J8QaXy8.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/eC2QZbT.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Document the case and close the alert.</b>
<br/>

- Suspicious Attachment found in email
<p align="center">
<img src="https://imgur.com/UNzF3Sp.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/7zlMhWs.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>We will have the next alert, review the descriptions and take ownership.</b>
<br/>

<p align="center">
<img src="https://imgur.com/EvcKu3Z.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>There is an attachment in the email that contains a PowerShell script. Let's examine it using Notepad on the Analyst VM. The script does not appear to be malicious and is actually designed for automating Windows updates.</b>
<br/>

<p align="center">
<img src="https://imgur.com/bHz3AG0.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/MB2vIwa.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/VpaHXnZ.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Document the case and close the alert.</b>
<br/>

## Outcome

- Incident Response Skills  
  - Gained practical experience in real-time phishing attack scenarios, learning to quickly assess and respond to security alerts.  
  - Developed a strong understanding of how to use cybersecurity tools (SIEM, VMs) to conduct detailed investigations and confirm alerts accurately.
- Alert Management & Analysis
  - Proven ability to effectively manage, prioritize, and investigate alerts in a fast-paced environment, ensuring that high-severity incidents are addressed first and efficiently.
- Documentation & Reporting
  - Learned to create clear and useful reports. These reports detail the findings of each investigation, outline the steps taken, and state the resolution status for each alert.
- Threat Detection & Mitigation
  - Improved ability to spot complicated phishing tactics. This includes recognizing PowerShell-based privilege escalation, reverse shell activity, and data theft while looking at the entire attack process.
- Real-World Cybersecurity Challenges
  - Prepared to effectively apply incident response techniques in real-world cybersecurity settings, with a solid understanding of how to respond to phishing attacks, decrease response time, and mitigate ongoing threats.
 
## Acknowledgements

This project combines ideas and methods from various sources, such as the TryHackMe SOC Simulator Phishing Unfolding room and my IT experience. These resources provided the fundamental information and techniques, which were then modified in light of practical uses.
 - [TryHackMe - SOC Simulator Phishing Unfolding](https://tryhackme.com/r/soc-sim/scenarios)
 - [Splunk](https://www.splunk.com/)

## Disclaimer

The sole goals of the projects and activities here are for education and ethical cybersecurity research. All work was conducted in controlled environments, such as paid cloud spaces, private labs, and online cybersecurity education platforms. Online learning and cloud tasks adhered closely to all usage guidelines. Never use these projects for improper or unlawful purposes. It is always prohibited to break into any computer system or network. Any misuse of the provided information or code is not the responsibility of the author or authors.
