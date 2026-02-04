Course: https://iriusrisk.academy/path-player?courseid=threat-modeling-program-roll-out&unit=68623bdae3811f0dfb08c09aUnit  
https://4550632.fs1.hubspotusercontent-na1.net/hubfs/4550632/Case%20Studies/MAR-1483%20The%20Beginners%20Guide%20to%20Threat%20Modeling%20v6.pdf  
tm-pro ---- is a threat modeling program rollout course -- for starting it from scratch -- skipping the course  
starting the other ones theat modeling foundations and threat modeling champion instead  

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
Risk -- accept, transfer, avoid, reduce  
Countermeasures -- preventive, detective, recovery, deterrant, compensating  
Threat -- anything that can harm the info systems  
Trust boundary -- Is a location on the data flow diagram where data changes its level of trust.  
Any place where data is passed between two processes is typically a trust boundary. If your application reads a file from disk,  
there's a trust boundary between the application and the file because outside processes and users can modify the data in the file.  






