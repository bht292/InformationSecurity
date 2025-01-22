# h2 Kill Chain
## Intelligence-Driven Computer Network Defense
### Indicators and the Indicator Life Cycle
### Intrusion Kill Chain
### Courses of Action
### Intrusion Reconstruction
### Campaign Analysis
### Summary

# Attack Story - A Cybersecurity Incident: The Supply Chain Compromise
## The Attack
On a quiet Thursday morning, an international logistics company noticed strange traffic from a server used to manage third-party vendors 
such as consultants or other kind of supporters. This was the start of a cyberattack that used a supply chain compromise (T1195) to break in.

### Initial Access
Hackers sent fake emails to employees at one of the company’s vendors. These emails included a stranfe file "you won the lottery.xlsx" 
(Phishing: Spearphishing Attachment 1566.001) that took advantage of a software vulnerability (Exploit Public-Facing Application T1190) to install a backdoor called “Main Entrance” 
The hackers then tampered with a software update the vendor provided to the logistics company. The update included hidden malware but appeared safe because it was signed with the vendor’s valid digital certificate, which gained trust of all surrounding systems.

### Execution
When the company installed the update, the malware ran on their servers. Hackers used Command and Scripting Interpreter called Windows PowerShell (T1059.001) to execute commands and stay hidden without leaving obvious traces. 

### Persistence
The attackers ensured they could return by creating fake administrative accounts as there was no sufficien PAM solution in place (Account Manipulation T1098) and setting up automatic startup programs on infected systems (Registry Run Keys / Startup Folder T1547.001).

### Privilege Escalation
To gain full control, they stole administrator passwords using a hacking tool (OS Credential Dumping: Credential Dumping T1003) that avoided detection by antivirus software.

### Defense Evasion
The attackers hid their tracks by deleting logs that could reveal their actions (Indicator Removal on Host: Clear Windows Event Logs T1070.001). This made it harder for the company’s security tools to catch them.

### Lateral Movement
The attackers moved through the company’s internal network using remote desktop tools such as RDP Manager or SecureFX (Remote Services: Remote Desktop Protocol T1021.001), taking advantage of weak security between different parts of the network.

### Collection
The hackers gathered sensitive data, including customer shipping information in order to sell it on the darknet later.
For that they used Archive Collected Data (Archive Collected Data: Archive via Utility T1560.001).

### Exfiltration
The stolen data was sent out of the company’s network to an external server controlled by the attackers. 
This filthy thieves used Exfiltration Over C2 Channel (T1041) to encrypt the data and make it look like normal web traffic.

## The Defense
By Thursday noon the company’s SOC Team (Security Operations Center) spotted unusual network activity through monitoring tools such as Tivoli and self-tailored Splunk Dashboards (Network Traffic Analysis T1071). Suspicious web traffic was flagged which triggered an instant investigation. The CISO was immediately informed and he called a crisis meeting with all whole infrastructure heads and the support head which would have to inform all users.

The final report for the management and executive board included all the steps which took place for the defense of this attack.

Containment
The affected servers were immediately isolated to stop the attack from spreading further.

Eradication
Security teams removed the malware and deleted fake accounts. They also cleared any malicious changes made to the system.

Recovery
The company restored clean backups of their systems and improved their network security to prevent similar attacks.
All the threats of the criminals were ignored and no money has been transfered. The issue had been reported immediately to the cyber crime department of the state.

Detection Improvements
New security rules were added to catch hacking tools and unauthorized scripts in the future.
A great deal of penetration tests were conducted in order to find more gaps.
More security meetings with the third-party vendors were planned to stay alligned and on track.
Audits are to take place this year which shall reveal other security gaps.

## Aftermath
Although some data was stolen, the company’s quick response minimized the damage. However a huge fine was issued by the state as crucial data had been stolen and been made public and the Chief Informartion Security Officer was forced to leave his position as the shareholders were not satisfied at all.

After the attack, the company improved their security practices, including stricter controls on third-party vendors and software updates, to prevent future incidents.


# References
Intelligence Driven Computer: https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf

Story: 
https://attack.mitre.org/techniques/T1195/
https://attack.mitre.org/techniques/T1566/001/
https://attack.mitre.org/techniques/T1190/
https://attack.mitre.org/techniques/T1059/001/
https://attack.mitre.org/techniques/T1098/
https://attack.mitre.org/techniques/T1547/001/
https://attack.mitre.org/techniques/T1003/
https://attack.mitre.org/techniques/T1070/001/
https://attack.mitre.org/techniques/T1021/001/
https://attack.mitre.org/techniques/T1560/001/
https://attack.mitre.org/techniques/T1041/
