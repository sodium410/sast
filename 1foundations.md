Course: Security Code Review and White Box Testing  
https://courses.redteamleaders.com/courses/4d70f388-ca16-4bfe-a97e-3a2dd9f01d06  
https://owasp.org/www-project-code-review-guide/  

## Introduction to Security Code Review  
**Security code review**: is the systematic examination of source code with the goal of identifying security vulnerabilities(xx,sqli),  
design flaws(no-auth), implementation weaknesses(weak ssl), configuration issues(defaul/hardcoded secrets),business-logic flaws that could be exploited by attackers.  

**The Security Testing Pyramid**..  
Penetration testing(Black box)---Security testing(Grey box---Security code review(white box)  

**Benefits**: Cost benefit, Early detection, complete coverage, no environment needed, prevent vul classes, RCA  

**When to perofrm security code review**:  
1. Design phase --- review architectural docs, evaluate tech choices, id secu requirements
2. Development phase - continous --- pull request reviews, pre-commit hoOks with SAST, secure coding enforcement
3. Pre-release phase --- Mandatory -- dedicated security sprint, full app review
4. Post-Incident -- reactive --- Rca, vul remediation verification, pattern iden to prevent recurrence
5. Third-part code --- open source library eval, composition scan mend.io

**priotitize scope** based on high priority code areas such as  
Authentication & Authorization, Input validation & sanitization, Crypto operations, db queries & data access,  
File operations & system commands, Business logic & workflows  

**Metrics that matter**: track these to demonstrate value    
Vulnerability found, vulnerability density - issues per 1000 line of code, time to remediate, recurrance rate, coverage - % of code reviewed  

**Common Misconceptions**  
we have waf, we have sast so no manual verification of its results, we do pentests, only security xperts can do code review  

**Getting Sarted**: your first code review  
understand the application, identify trust boundaries, follow data flow, look for security hotpots(auth,author,crypto,inputvali,errorhandling)  














