# h1 Should Tero wear a helmet?
## Threat Modelling
The Threat Modeling Manifesto outlines a structured and principled approach to threat modeling, emphasizing the importance of building secure systems by addressing potential risks early and effectively. 
It advocates for a proactive culture where security considerations are integrated into the design and planning phases, rather than being treated as an afterthought. 
The manifesto highlights the value of people and collaboration, emphasizing that diverse stakeholders and teamwork are more critical than relying solely on tools and processes. 
It encourages critical thinking and flexibility by promoting the use of tailored questions to uncover threats, rather than adhering strictly to generic checklists.
The manifesto identifies threat modeling as an iterative process that evolves alongside the system. The Threat Modeling Manifesto underscores the significance of continuous learning and improvement, recognizing that threat modeling is not a one-time task but an ongoing effort aligned with the dynamic nature of systems and threats. 

It emphasizes the importance of empowering individuals to ask insightful questions, challenge assumptions, and adapt methodologies to the unique context of their projects. By fostering a culture of collaboration, critical thinking, and early engagement with security, the manifesto aims to create robust, secure systems that stand resilient against evolving threats.


## Security Hygine
### What basic security practices should everyone follow?
* Use Strong, Unique Passwords: Avoid common passwords and reuse. Use a mix of characters, numbers, and symbols
* Enable Multi-Factor Authentication (MFA): Add an extra layer of security to your accounts
* Update Software Regularly: Keep operating systems, apps, and antivirus software up to date
* Be Wary of Phishing Scams: Avoid clicking on suspicious links or downloading unknown attachments
* Secure Home Wi-Fi Networks: Use strong passwords and encrypt your Wi-Fi with WPA3 or WPA2
* Use Antivirus and Anti-Malware Tools: Regularly scan devices for malware and viruses
* Limit Personal Information Sharing: Avoid oversharing on social media and other platforms
* Back Up Important Data: Use secure cloud storage or external drives for regular backups
* Lock Devices: Set strong passwords or biometrics for locking phones, laptops, and tablets
* Be Careful with Public Wi-Fi: Avoid sensitive transactions on public Wi-Fi or use a VPN for encryption
* Monitor Account Activity: Regularly check bank statements and online accounts for unauthorized access
* Dispose of Devices Securely: Wipe personal data before recycling or selling old devices

### Are there some security hygiene practicies that every company or average Joe should follow?
* Regular Security Training: Educate employees on cybersecurity best practices and recognize threats
* Enforce Password Policies: Require strong passwords and mandate periodic changes
* Implement MFA Across the Organization: Add layers of security for all access points
* Maintain a Patch Management System: Ensure software and systems are always updated
* Limit Privileged Access: Adopt the principle of least privilege for users and applications
* Conduct Regular Security Audits: Test and assess systems for vulnerabilities
* Use Endpoint Protection: Secure all endpoints with robust antivirus and endpoint detection solutions
* Encrypt Sensitive Data: Protect stored and transmitted data with encryption
* Monitor Network Activity: Implement tools to detect and respond to unusual behavior
* Establish an Incident Response Plan: Prepare for and mitigate the impact of security breaches
* Secure Physical Access: Use locks, access controls, and monitoring for server rooms and offices
* Implement Secure Software Development Practices: Include security testing in the software lifecycle
* Encourage Reporting: Create a culture where employees feel comfortable reporting potential security concerns

## Make-belief boogie-man - a threat model for imaginary company
### What are we working on?
Company Overview: 
DreamCloud Services is a Software-as-a-Service (SaaS) company providing cloud-based solutions for project management and collaboration. 
Its flagship product, "CloudCollab," integrates real-time chat, task management, and file sharing tailored for medium-sized businesses.

Assets:
Crown Jewels
* Customer data
* Intellectual property
* Financial systems

Supporting Assets: 
* User authentication system (OAuth2-based)
* Customer-facing website and APIs
* Employee laptops and office network
* Development environment

Low-priority Assets:
* Internal employee gaming server

Prioritization
* Protect customer data and ensure uptime for CloudCollab
* Secure backend servers hosting the proprietary application
* Safeguard the user authentication system

Customer Perspective: Customers see DreamCloud through:
* Touchpoints: Mobile app, web app, REST APIs, and email support
* Expectations: Fast, reliable service with robust security for their business-critical data

Business Goals:
* Provide uninterrupted, secure access to CloudCollab
* Retain customer trust by preventing data breaches
* Minimize downtime to ensure steady cash flow

### What can go wrong?
In order to answer this question the following modells are applied:
#### STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege):
* Spoofing: Fake accounts accessing customer data
* Tampering: Hackers modifying project files
* Information Disclosure: Unauthorized access to sensitive files
* Denial of Service: Attackers overwhelming servers to disrupt service

#### CIA (Confidentiality, Integrity, Availability)
* Confidentiality risk: Insider threat exposing sensitive files
* Integrity risk: Injection of malicious scripts in project data
* Availability risk: Ransomware attack shutting down CloudCollab

#### Risks
The three biggest risks which we are facing are the following:
Risk 1: Phishing Attack
Impact: Compromised admin accounts could lead to a data breach
Likelihood: High due to the prevalence of phishing campaigns
Expected Value: High (probability * customer trust damage)

Risk 2: Denial of Service (DDoS Attack)
Impact: Prolonged downtime causing financial losses
Likelihood: Moderate, as DDoS tools are widely available
Expected Value: Medium (probability * revenue loss per hour)

Risk 3: Rogue Employee
Impact: Insider leak of customer data or sabotage
Likelihood: Low but catastrophic if it happens
Expected Value: High due to trust implications

#### Threat Actors
Nowadays the threat actors which are most to be expected are: 
* Hacktivists: Targeting DreamCloud for perceived ethical missteps
* Organized Cybercriminals: Seeking financial gain
* Insiders: Disgruntled employees or contractors

The known TTPs are Credential stuffing, ransomware and API scraping.

#### Business Continuity Risks
If our Business is attacked and damage is made the following consequences are to be expected due to reputational damage: 
Service disruption affects customer trust and revenue
Loss of data damages credibility and invites legal challenges

### What are we going to do about it?
In order to mitigate the mention dangers above we can implement a lot of defense mechanisms such as:

Reduce Attack Surface in general
* Limit API access with rate-limiting and IP whitelisting
* Decommission unused development environments

Strengthen Defenses:
* Implement Multi-Factor Authentication (MFA) for all admin accounts
* Encrypt all sensitive data at rest and in transit
* Shred phyiscal documents after their use is done

Monitor and Respond
* Deploy an intrusion detection system (IDS)
* Regularly monitor logs for unusual activity

Employee Training
* Phishing simulations and security awareness training
* Basic IT Security trainings
* Monthly refresher course with all actual dangers

The META Framework can also be applied to that:
Mitigate: Encrypt data, enforce MFA
Eliminate: Disable legacy systems no longer in use
Transfer: Buy cybersecurity insurance for ransomware scenarios
Accept: Low-probability risks like rogue employees, given other controls

### Did we do a good enough job?
Continuous improvement can be achieved by holding Audits, doing own reflections and ask ourselves if we are secure enough on a regular bases.
This includes reporting all incidents and monitoring attacks and track these in statistics.
Penetration tests are always a good challange to see if we are secure.

DreamCloud Services must focus on protecting customer data, ensuring service availability, and maintaining customer trust. 
Continuous evaluation and adaptation to new threats will safeguard its business goals and reputation.
