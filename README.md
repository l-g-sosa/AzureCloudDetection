<h1>Azure Cloud Detection Lab</h1>

<h2>Description</h2>

Utilized Azure to create a lab detection environment using Microsoft Sentinel as a SIEM (Security Information and Event Management System). 
Deployed a virtual machine with Windows 10 to function as the possible victim, and configured Microsoft Sentinel to create an alert for a persistence attack. 
<br />

<h2>Objectives</h2>

- Configure and Deploy Azure Resources such as Log Analytics Workspace, Virtual Machines, and Azure Sentinel.
- Implement Network and Virtual Machine Security Best Practices.
- Utilize Data Connectors to bring data into Sentinel for Analysis.
- Understand Windows Security Event logs.
- Configure Windows Security Policies.
- Utilize KQL to query Logs.
- Write Custom Analytic Rules to detect Microsoft Security Events.
- Utilize MITRE ATT&CK to map adversary tactics, techniques, detection and mitigation procedures.

<br />

<h2>Lab walk-through:</h2>

- A data collection rule was created using Windows Security Events via AMA as a data connector:
<img src="https://i.ibb.co/tcBFFLY/image-5.png" height="80%" width="80%"/>

- Configured a rule against a possible persistence attack (MITRE ATT&CK Framework). The rule was set to see eventID 4698 (Scheduled tasks) occurrences. The rule was parsed, so it contained: computer, time generated, client process ID, name of scheduled task, and user:
<img src="https://i.ibb.co/Br1J48C/image-2.png" height="80%" width="80%"/>

 - Created a customized Analytic Rule showing entities account name, process ID, malware name, and host:
<img src="https://i.ibb.co/nk7LxRC/analytic-rule.png" height="80%" width="80%"/>

- A Persistence attack on the Windows 10 client was simulated, by creating a scheduled task. The MITRE ATT&CK tactic used in this lab is [TA0003 Persistence](https://attack.mitre.org/tactics/TA0003/). The following is the alert shown in Microsoft Sentinel once it detected:
<img src="https://i.ibb.co/8cSkrBZ/alert.png" height="80%" width="80%"/>
 

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
