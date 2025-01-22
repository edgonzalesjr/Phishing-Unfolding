
## Practical Exercises

<p align="center">
<img src="https://imgur.com/thfKKZQ.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/0kheHlT.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>On the Dashboard to see the status of the alerts. We'll have the Alert queue for the breakdown of the reported alerts.</b>
<br/>

<p align="center">
<img src="https://imgur.com/raoWABU.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/AoNqbkH.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>To approach in investigating the alerts, it's better to sort based on the severity. Start with the critical alerts. If there's none, check the other alerts for High alerts.</b>
<br/>

<p align="center">
<img src="https://imgur.com/izFB0go.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<img src="https://imgur.com/dFZ0PZn.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>We'll have one Low alert and take a look at the descriptions and take ownership.</b>
<br/>

<p align="center">
<img src="https://imgur.com/ee5pmbO.png" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>Let's go ahead on the Splunk SIEM. Take a look at the Data Summary for available sources.</b>
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
<b>Search for the process name. Taskhostw.exe is a system file of the Windows operating system. It stands for Task’s Host for Windows. It's main function is to start the Windows services based on DLLs whenever the computer boots up. Seems legitimate is located in the C:\Windows\System32 folder and no other spawned processes.</b>
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
<b>Write the case and close the alert.</b>
<br/>

<p align="center">
<img src="https://imgur.com/" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>.</b>
<br/>

<p align="center">
<img src="https://imgur.com/" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>.</b>
<br/>

<p align="center">
<img src="https://imgur.com/" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>.</b>
<br/>

<p align="center">
<img src="https://imgur.com/" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>.</b>
<br/>

<p align="center">
<img src="https://imgur.com/" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>.</b>
<br/>

<p align="center">
<img src="https://imgur.com/" height="90%" width="90%" alt="Device Specification"/>
<br/>
<b>.</b>
<br/>



## Acknowledgements

This project combines ideas and methods from various sources, such as the TryHackMe SOC Simulator Phishing Unfolding room and my IT experience. These resources provided the fundamental information and techniques, which were then modified in light of practical uses.
 - [TryHackMe - SOC Simulator Phishing Unfolding](https://tryhackme.com/r/soc-sim/scenarios)
 - [Splunk](https://www.splunk.com/)

## Disclaimer

The sole goals of the projects and activities here are for education and ethical cybersecurity research. All work was conducted in controlled environments, such as paid cloud spaces, private labs, and online cybersecurity education platforms. Online learning and cloud tasks adhered closely to all usage guidelines. Never use these projects for improper or unlawful purposes. It is always prohibited to break into any computer system or network. Any misuse of the provided information or code is not the responsibility of the author or authors.
