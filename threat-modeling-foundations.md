Course: https://iriusrisk.academy/path-player?courseid=threat-modeling-program-roll-out&unit=68623bdae3811f0dfb08c09aUnit  
https://4550632.fs1.hubspotusercontent-na1.net/hubfs/4550632/Case%20Studies/MAR-1483%20The%20Beginners%20Guide%20to%20Threat%20Modeling%20v6.pdf  
tm-pro ---- is a threat modeling program rollout course -- for starting it from scratch -- skipping the course  
starting the other ones -- theat modeling foundations and threat modeling champion instead  

## 1.Introduction  
### What is threat modeling  
proactive methodology to identity, assess, communicate and mitigate potential threats **as early as possible in the development process**.  
by identifying vuln and predicting possible attack vectors and addressing them with security controls  

understand what could go wrong, how it could happen, and what controls are needed to prevent or reduce the impact of those threats  

Understand system--> Gain a comprehensive understanding of the system’s architecture, data flows, and intended functionality to form the foundation of the threat modeling process.  
identify threats--> Recognize potential vulnerabilities, attack surfaces, and threat actors. Common methodologies such as STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privileges) can be used to structure this process.  
assess risk--> Analyze the potential impact and likelihood of each identified threat to prioritize mitigation efforts. This ensures that the most critical risks are addressed first.  
mitigate threats--> Develop and implement effective countermeasures to address identified vulnerabilities, ensuring the system is resilient against potential attack vectors. 
validate--> Continuously review and refine the threat model to ensure its relevance as the system evolves and new threats emerge.  

### Why threat modeling, Benefits of threat modeling  
secure by design: proactive risk identification and mitigation, tm is one of the tool for sbd  
enhanced security posture -- reduces imapct and likelihood of breaches  
cost saving -- addressing risks during design and deve is much cost effective than after deployment  
compliance and regulatory adherence  
improved collaboration and comms -- bridges gap between technical and non technical stakeholders  

**Common misonceptions about threat modeling**  
threat modeling is a one-time exercise  
confusion with penetration testing -- pentesting is reactive tm is proactive focued on anticipating risks  

## Basic threat modeling concepts  
### Key threat modeling terms  
Asset -- product or application  
Business consequences -- How an incident will affect the organization externally.  
Business impacts -- How an incident will affect the organization internally.  
Risk capacity -- The maximum amount of risk that an organization is able to tolerate.  
Risk Tolerance -- The acceptable level of variation that management is willing to allow for any particular risk.  
Likelihood/Probability -- Is a measure of the possibility of a threat being carried out  
Risk -- accept, transfer, avoid, reduce  Risk = Likelihood x Impact  
Countermeasures -- preventive, detective, recovery, deterrant, compensating  
Threat -- anything that can harm the info systems  
Trust boundary -- Is a location on the data flow diagram where data changes its level of trust.  
Any place where data is passed between two processes is typically a trust boundary. If your application reads a file from disk,  
there's a trust boundary between the application and the file because outside processes and users can modify the data in the file.  
threat actor --- attacker or group  
Attack surface -- Is the number of all different attack vectors (or points) where an unauthorized user can access a system and extract data.  
The smaller the attack surface the easiest is to protect the application.  
Attack library -- possible attacks that could be used against an application component.  
Attack vector -- Is all the different points that an unauthorized user can access a system and extract data.   
Attack tree -- Are conceptual diagrams showing how an asset, or target, might be attacked.  
Attack -- attack  
Vulnerability -- weakness in people, process or technology in an environment, which could be exploited by one or more threat actors.  
threat scenario -- A set of discrete threat events, associated with a specific threat source or multiple threat sources, partially ordered in time.  
threat landscape -- all attack surfaces -- web, email, physical, logical  

**Assets**  -- Assets are anything valuable to an organization or system that needs protection from potential threats.  
data assets, software assets, human assets  
Asset identification and classification -- inventory all assets and classify them by imporatnce, location and any dependencies  

**Vulnerabilities** -- physical, owasp  

**Threats** -- internal, external, human factor, threat scenarios  

**Attack vectors and surface**  
Attack Vectors are the methods, paths, or means by which a threat actor gains unauthorized access.  
The Attack Surface refers to the total sum of all possible points or vectors where an unauthorized user (the "attacker") can attempt to enter  
Network based attack vectors -- DDos, MitM  
Application based attack vectors, Insider attack vectors, physical attack vectors,  
Reducing attack surface minimized attack vectors  

**Threat actors** -- characterisitcs of threat actor -- motivation, capabilities, intent, targeting  
types -- insider, state sponsered, script kiddie, hactivists, cyber terrorists  

**Countermeasures**  -- technical, administrative, physical  

## Threat modeling methodologies/Techniques  
The most common methodologies include STRIDE, PASTA, and LINDDUN
The most common methodologies include STRIDE, PASTA, and LINDDUN. STRIDE focuses on identifying different types of security threats,  
PASTA aligns business objectives with technical security needs, and LINDDUN specializes in addressing privacy-related threat.  

**STRIDE** is a threat modeling methodology developed by Microsoft to help identify security threats across various dimensions.  
The acronym stands for Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege.  
By analyzing each component of a system against these six threat types, security teams can systematically identify vulnerabilities and potential attacks.   
STRIDE is particularly useful in the early stages of software development, as it allows teams to anticipate and mitigate risks before they become critical.  
The process involves identifying system entities, defining data flows, and then mapping potential threats to these flows.  
STRIDE is favored for its structured approach and comprehensiveness, making it a standard choice for threat modeling in complex, multi-layered systems.  

## Theat modeling process  
A widely-used approach in thereat modeling involves asking four fundamental questions..  
**what are we building** -- This question aims to clearly define the system, application, or product being developed.  
It involves understanding the architecture, components, data flows, user interactions, and the overall purpose of the system.  
This foundational understanding helps identify the scope of the Threat Modeling exercise and sets the context for identifying potential threats.  
includes -- identify scope/trust boundaries, create dfd, id assets to protect, define trust levels and boundaries, determine system env(firewalls,ips etc)  

**what can go wrong**  
identify threats using STRIDE  
Analyze entry points and attack surfaces  
Map attack paths or attack trees  
Consider potential abuse and misuse cases  
Identify external and environmental theats  
Prioritize threats  

**what are we going to do about it**  
mitigate, transfer, accept, avoid threats  
Apply countermeasures or Security controls  
Consider defence in depth  
Evaluate mitigations against STRIDE threats  
Risk basde prioritization of mitigation  
Optional -- plan for incident response  

**Did we do good enough job** -- validate  
Review the effectiveness of mitigations  
Perform testing and validation -- pentest  
check for completeness  
preform regular threat modeling reviews  
gather feedback from stakeholders  
refine and improve the process  

<img width="489" height="163" alt="image" src="https://github.com/user-attachments/assets/1af6ac24-908c-4d14-a7f4-d59f72e43cce" />

**Threat modeling best practices**
understand system archite, Use STRIDE, Iterate and improve, collaborate, focus on practical mitigations  

## 5. Using IriusRisk to threat model  
sign up, create a project, add what are we building and the process is nice and easy    

## 6.Hands-on  
**Scenario**  
You are part of the Threat Modelling team for a company that has developed a new web application called "e-sectransfer."  
This application allows users to perform various banking operations online, such as checking account balances, transferring funds, and paying bills.  
Your task is to create a threat model for this application to identify potential security risks and suggest mitigations.  
The results will be presented to the Threat Modelling team and to Senior Management.  

Try both manual method and using IriusRisk platform  

https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html  




