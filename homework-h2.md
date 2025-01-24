# h2 Kill Chain
## Intelligence-Driven Computer Network Defense
### What is it about
Intelligence-driven computer network defense represents a proactive approach to cybersecurity, leveraging detailed insights into adversary tactics and strategies. The framework focuses on analyzing adversary campaigns to understand and disrupt their activities effectively. 

By applying intelligence to all aspects of cyber defense, organizations can anticipate, mitigate, and respond to threats with precision.

### Indicators and the Indicator Life Cycle
Indicators are artifacts or observables that suggest adversary activity, such as IP addresses, file hashes, or domain names. The life cycle of an indicator consits of the stages creation, deployment, operation, and eventual retirement. 
Managing this life cycle is critical for ensuring indicators remain relevant and effective. By categorizing indicators by type and source, organizations can prioritize their use and ensure actionable insights.

### Intrusion Kill Chain
The Intrusion Kill Chain provides a structured approach to understanding and countering adversary actions. 
It consists of the following seven phases.

#### Phase 1: Reconnaissance
The attacker identifies and selects their target through open-source intelligence gathering.

#### Phase 2: Weaponization
Malicious payloads are crafted, often combining an exploit and a delivery mechanism.

#### Phase 3: Delivery 
The adversary transmits the payload via methods such as phishing emails or infected USBs.

#### Phase 4: Exploitation
The malicious code is executed on the target system by exploiting a vulnerability.

#### Phase 5: Installation
The attacker establishes a foothold by installing backdoors or malware.

#### Phase 6: Command and Control (C2)
A channel is created for the attacker to remotely control the compromised system.

#### Phase 7: Actions on Objectives
The adversary achieves their intended goal, such as exfiltrating data or disrupting systems, causing severe damages within the whole IT environments.

### Courses of Action
Defenders can employ specific actions at various stages of the kill chain to disrupt an adversary's campaign. These courses of action are categorized into six types: detection, denial, disruption, degradation, deception, and destruction. 
Each course addresses a different phase of the attack to either halt its progression or reduce its impact.

For instance, detection involves identifying adversary activity early to prevent further action, while denial focuses on blocking access to resources or vulnerabilities. Disruption targets the attacker's ability to execute their plan, such as cutting off command and control channels. 

Deception, on the other hand, uses false information to mislead adversaries and waste their resources. These tailored approaches allow organizations to respond dynamically, reducing risk while maximizing defensive efficiency.

### Intrusion Reconstruction
When an intrusion occurs, it is essential to reconstruct the event to understand what happened and how it occurred. This process involves analyzing logs with a tool as Splunk or something simmilar, correlating data, and mapping the incident to the kill chain stages. 
By doing so, defenders can uncover gaps in their security posture and gain insights into the adversary's methods and objectives.

Therefore, reconstruction serves several purposes. It helps organizations identify the root cause of an incident, refine detection capabilities, and enhance their response mechanisms. In addition to that it enables security teams to piece together adversary tactics, techniques, and procedures, forming a more comprehensive picture of the attack. 

This information can then be fed back into defensive strategies to close vulnerabilities and anticipate similar threats in the future. That will result to a stronger and more secure IT environment.

### Campaign Analysis
Campaign analysis elevates the focus from individual incidents to the larger patterns of adversary behavior. 

By examining multiple intrusion attempts, analysts can discern an adversary's broader objectives, operational methods, and preferred tools. This macro-level perspective reveals how specific incidents fit into a larger strategy, providing deeper insights into threat actors.
One of the key outcomes of campaign analysis is the ability to attribute attacks to specific groups or motivations, such as financial gain, espionage, or sabotage. 

It also helps prioritize resources by identifying the most persistent or impactful threats. By tracking adversary campaigns over time, organizations can adopt a predictive stance, anticipating future actions and preparing defenses in advance.

### Summary of Intelligence-Driven Computer Network Defense
Intelligence-driven defense emphasizes understanding and countering adversaries through structured frameworks and actionable intelligence. 

The kill chain provides a systematic approach to identifying and mitigating threats at each stage of an attack. Managing indicators ensures relevant and timely responses, while intrusion reconstruction uncovers valuable lessons for refining defenses. Campaign analysis broadens the scope of understanding, linking individual incidents to broader adversary strategies. This proactive and intelligence-led approach shifts cybersecurity from reactive measures to predictive and preventive strategies.

With this information organizations can strengthen their resilience against the evolving landscape of cyber threats.


## Attack Story - A Cybersecurity Incident: The Supply Chain Compromise
### The Attack
On a quiet Thursday morning, an international logistics company noticed strange traffic from a server used to manage third-party vendors 
such as consultants or other kind of supporters. This was the start of a cyberattack that used a supply chain compromise (T1195) to break in.

#### Initial Access
Hackers sent fake emails to employees at one of the company’s vendors. These emails included a stranfe file "you won the lottery.xlsx" 
(Phishing: Spearphishing Attachment 1566.001) that took advantage of a software vulnerability (Exploit Public-Facing Application T1190) to install a backdoor called “Main Entrance” 
The hackers then tampered with a software update the vendor provided to the logistics company. The update included hidden malware but appeared safe because it was signed with the vendor’s valid digital certificate, which gained trust of all surrounding systems.

#### Execution
When the company installed the update, the malware ran on their servers. Hackers used Command and Scripting Interpreter called Windows PowerShell (T1059.001) to execute commands and stay hidden without leaving obvious traces. 

#### Persistence
The attackers ensured they could return by creating fake administrative accounts as there was no sufficien PAM solution in place (Account Manipulation T1098) and setting up automatic startup programs on infected systems (Registry Run Keys / Startup Folder T1547.001).

#### Privilege Escalation
To gain full control, they stole administrator passwords using a hacking tool (OS Credential Dumping: Credential Dumping T1003) that avoided detection by antivirus software.

#### Defense Evasion
The attackers hid their tracks by deleting logs that could reveal their actions (Indicator Removal on Host: Clear Windows Event Logs T1070.001). This made it harder for the company’s security tools to catch them.

#### Lateral Movement
The attackers moved through the company’s internal network using remote desktop tools such as RDP Manager or SecureFX (Remote Services: Remote Desktop Protocol T1021.001), taking advantage of weak security between different parts of the network.

#### Collection
The hackers gathered sensitive data, including customer shipping information in order to sell it on the darknet later.
For that they used Archive Collected Data (Archive Collected Data: Archive via Utility T1560.001).

#### Exfiltration
The stolen data was sent out of the company’s network to an external server controlled by the attackers. 
This filthy thieves used Exfiltration Over C2 Channel (T1041) to encrypt the data and make it look like normal web traffic.

### The Defense
By Thursday noon the company’s SOC Team (Security Operations Center) spotted unusual network activity through monitoring tools such as Tivoli and self-tailored Splunk Dashboards (Network Traffic Analysis T1071). Suspicious web traffic was flagged which triggered an instant investigation. The CISO was immediately informed and he called a crisis meeting with all whole infrastructure heads and the support head which would have to inform all users.

The final report for the management and executive board included all the steps which took place for the defense of this attack.

#### Containment
The affected servers were immediately isolated to stop the attack from spreading further.

#### Eradication
Security teams removed the malware and deleted fake accounts. They also cleared any malicious changes made to the system.

#### Recovery
The company restored clean backups of their systems and improved their network security to prevent similar attacks.
All the threats of the criminals were ignored and no money has been transfered. The issue had been reported immediately to the cyber crime department of the state.

#### Detection Improvements
New security rules were added to catch hacking tools and unauthorized scripts in the future.
A great deal of penetration tests were conducted in order to find more gaps.
More security meetings with the third-party vendors were planned to stay alligned and on track.
Audits are to take place this year which shall reveal other security gaps.

### Aftermath
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
