# h2 Kill Chain
## Intelligence-Driven Computer Network Defense
ntelligence-driven computer network defense represents a strong approach to cybersecurity, leveraging detailed insights into adversary tactics and strategies. The framework focuses on analyzing the different stages of cyber attacks. This is crucial to understand and interfere with their activities on a efficient way. 

By applying intelligence to all aspects of cyber security, most of the organizations can expect, mitigate, and respond to threats with a precise way.

### Indicators and the Indicator Life Cycle
Indicators are artifacts that suggest adversary activity. Examples for that are IP addresses, file hashes, or domain names. The life cycle of an indicator consits of the stages creation, deployment, operation, and finally retirement. 
Managing this life cycle is of great importance for ensuring that they remain relevant and effective.

### Intrusion Kill Chain
The Intrusion Kill Chain provides a structured approach to understand and counter the necessery actions. 
It consists of the following seven phases.

#### Phase 1: Reconnaissance
The attacker identifies and selects its target through open-source intelligence gathering.

#### Phase 2: Weaponization
Malicious payloads are created in conjunction with combining an exploit and a delivery mechanism.

#### Phase 3: Delivery 
The adversary transmits the payload via several methods such as phishing emails or infected USBs.

#### Phase 4: Exploitation
The malicious code is executed on the target system by exploiting a vulnerability.

#### Phase 5: Installation
The attacker secures access to the system by deploying backdoors or installing malware.

#### Phase 6: Command and Control (C2)
A channel is created for the attacker to remotely control the compromised system.

#### Phase 7: Actions on Objectives
The adversary achieves their intended goal, such as exfiltrating data or disrupting systems, causing severe damages within the whole IT environments.

### Courses of Action
Defenders can execute specific actions at many stages of the kill chain to disrupt a hacker's  attack. These actions are categorized into six types. Detection, denial, disruption, degradation, deception, and destruction. 
Each course addresses a different phase of the attack to either halt its progression or reduce its impact.

For instance, detection involves identifying adversary activity early to prevent further action, while denial focuses on blocking access to resources or vulnerabilities. Disruption targets the attacker's ability to execute their plan. An example for that would be to cut off command and control channels. 

Deception uses false information to mislead the opponents and waste their resources. This is a very frustrating experience for them which might causes them to stop the attack.

### Intrusion Reconstruction
When an intrusion occurs it is essential to reconstruct the event. The most important things are to understand what happened and how it occurred, as the answers to these questions are of great value for the future. 

This process involves analyzing logs with a tool sucha as Splunk or something simmilar, correlating data and connecting the incident to the kill chain stages. By doing so defenders can uncover gaps in their security posture and gain insights into the adversary's methods and objectives. Therefore, reconstruction serves several purposes. It helps organizations to identify the root cause of an incident and refine detection capabilities which enhances their response mechanisms. 

In addition to that it enables the security teams to understand their opponents tactics and procedures. This gains them a more comprehensive picture of the attack. 
This information can then be fed back into defensive strategies to close vulnerabilities and anticipate similar threats in the future. That will result to a stronger and more secure IT environment.

### Campaign Analysis
Campaign analysis elevates the focus from individual incidents to the larger patterns of adversary behavior. 

Analyzing multiple intrusion attempts helps the security analysts to understand the attacker’s goals and methods. Even the tools can be figured out and many more details. This broader view shows how the incidents fit into a larger strategy and provides valuable insights into the hackers behaviors. A key benefit of campaign analysis is identifying who is behind the attacks and what their motivations are.

It also helps to prioritize resources by identifying the most persistent or impactful threats.

### Key Content and questions
Intelligence-driven cybersecurity is used in order to stay ahead of attackers by understanding their tactics and using that know-how to prevent threats and find risks. Tools like the Intrusion Kill Chain break down attacks into different Phases which help defenders to block or disrupt them at specific situations.

When attacks happen it is vital to analyze them as it helps to uncover vulnerabilities and improve defenses. Looking at broader patterns can reveal what attackers are after and how they operate. This allows organizations to adapt to future threats and respond more effectively. It is all about being proactive instead of reactive when it comes to defend a Information System against cyber threats.

Even though this framework is of big importance, I wonder how smaller companies implement this. Do they even have the resources? Could the framework be optimized for smaller teams while maintaining its effectiveness?

## Tactics, tools and procedures
### Definition of tactic
Every attack has its own reasons. Tactics are about the cause of an attack and it simply explains why the hacker performed the cyber crime or what he aims to achieve with it.

### Example of tactic
An example of tactic can be exfiltration where the adversary seeks to extract sensitive information from a network in order that he can sell it in the darknet. He would perform this attack to gain the information and make money with it.

### Definition of technique
Technique is all about how the attack is conducted, therefore it specifies the approaches or methods of the hacker to achieve their goals.

### Example of technique
In regards to the exfiltration tactic a technique could be Data Encrypted for Impact. Here the attackers encrypt files to disrupt access.

### Definition of subtechnique
A sub-technique provides a more detailed description of how the technique is implemented. 

### Example of subtechnique
For instance, a sub-technique of Data Encrypted for Impact might be Encrypt Network Share, where attackers target shared network drives for encryption.

### Definition of procedure
A procedure describes the practical implementation of a technique or a sub-technique. It states the specific actions taken by an adversary to achieve their objective.

### Example of procedure
Sending a phishing email with a malicious link to targeted users is a procedure used to achieve the Phishing technique.

### Additional questions
I wonder what kind of challenges the CISOs of organisations face when trying to implement ATT&CK principles in their environment. How do they monitor the progress of the implementation? 

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
Inromation Security course resources
https://terokarvinen.com/

Intelligence Driven Computer: https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf

Tactics, tools and procedures:
https://attack.mitre.org/resources/faq/#general-faq

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
