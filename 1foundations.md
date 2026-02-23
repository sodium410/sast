Course: Security Code Review and White Box Testing  
https://courses.redteamleaders.com/courses/4d70f388-ca16-4bfe-a97e-3a2dd9f01d06  
https://owasp.org/www-project-code-review-guide/  

## Introduction to Security Code Review  
**Security code review**: is the systematic examination of source code with the goal of identifying security vulnerabilities(xx,sqli),  
design flaws(no-auth), implementation weaknesses(weak ssl), configuration issues(defaul/hardcoded secrets),business-logic flaws that could be exploited by attackers.  
SAST -- without code execution  
DAST -- dynamic interaction  

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

## White Box vs Black Box vs Grey Box Testing  
Penetration testing(Black box)---Security testing(Grey box---Security code review(white box)  
Phase1 -- white box(pre-release) ci/cd --- maximum coverage  
Phase2 -- Grey box(pre-prod) -- balanced approach  
phase3 -- Black box(production)  -- exernal attacker view  

## Threat Modeling for Code Review  
is the process of identifying assets, threats, vulenrabilities, risks and defining countermeasures  
based on four questions: what is built, what can go wrong, how to mitigate, validate  

**Threat-Driven Code Review**  -- Why threat modeling for code reviews ?  
prioritize high-risk components first, prevent entire vuln class, focus on boundaries & attack surfaces  

**The STRIDE Framework**: Apply STRIDE to code reviews    
Spoofing -- authentication - weak pass validation  
Tampering -- Integrity -- SQL injection -- Data modification  
Redudiation -- Non-Repudiation  -- Missing audit logs -- Deny actions  
Information Disclosure -- Confidentiality -- Verbose error messages  -- Data leakage  
Denial of service -- Availability -- Infinite loops -- Service unavailability  
Elevation of Privileges -- Authorization -- Misssing access checks -- Unauthorized access  

**DFDs for Code review** -- helps visualize how data moves through app making trust boundaries obvious.  
DFD components --- entity(external actors - users,systems), Process - code that transforms data, Data store - db/files, Trust boundary -- security boundary.  
code review checks at trust boundaries -- input validation, authentication, authorization, sanitization, encoding, error handling  

**Attack trees** -- helps visualize how an attacker might achieve a goal by chaining multiple vulns.  
Goal: admin panel access ----> steal admin creds or Exploit authoriztion, sql injection or path traversal etc  
perform code reviews based on priority based attack trees -- high impact ones first then low priority paths  

**Risk Assessment and Prioritization**  Risk= likelihood X impact  
assessing likelihood based on attacker skills, exploitability, attack surface, detection  
Assessing impact based on Condidentiality, Integrity and availability  
Therefore prioritize code reviews based on risk level critical first  

When to threat model --- at every stage in SDLC, require, design, dev, testing, deplo and maintainance  

Tools for threat modeling --- irius, owasp threat dragon etc  

Use threat model to configure SAST rules  
prioritize SAST findings based on threat model  
Map vuln to STRIDE categories  

## Code Review Methodologies and Workflows   
### 1. Top-Down Methodology(Architecture-first)  
Start with big picture and then drill down into details  
Application architecture --> Component analysis --> Module review --> Function level analysis --> Line by line review  
When to use: new codebase, large apps, when context is critical  
### 2. Bottom-up Methodology(Code-First)  
Individual code lines-->Functions-->Modules-->Components-->System understanding  
When to use: time contrained, focused assessment, incremental code changes  
### 3. Hybrid Methodology(Recommended)  
combines top-down and bottom-up   
Process: Reconnaissance, automated discovery(sast tools), manual deep-dive, pattern analysis, validation  

### System code review workflow  
The 6-phase workflow  
**Phase1** - preparation and planning - get code, understand context, scope(full app/specific module?), identify time constraints, set up environment, review exisiting docs  
Questions: what are most critical functions, what does the app handle, any known security concerns, what is the threat landscape, who are the users  

**Phas2** - Information gathering  
technology stack identification  -- check package files, grep -r "Spring"  etc   
Architevure discovery  -- entry points and config files  
Create component map -- image below  
<img width="275" height="161" alt="image" src="https://github.com/user-attachments/assets/fb2fc9e3-3132-43ba-85c1-1fe38940d706" />

**Phase3**: threat modeling  
DFD, STRIDE Analysis, Create review checklist - for each vul  

**Phase4**: Automated scanning  
<img width="337" height="169" alt="image" src="https://github.com/user-attachments/assets/82ee7020-d09a-42d7-9174-f19cf02fb8b3" />

**Phase5**: Manual code review  
validate automated code findings, find complext vuln, identify business logic flaws  

**Phase6**: Documentation and reporting  

Review time= (Lines of code/Review rate) X Complexity factor  

## Manual code review techniques  
1. Control and data flow and semantic analysis  -- follow if/else branches  
2. Pattern matching -- find dangerous patterns  
3. Analyse trust boundaries  

## Assisted code review tools  
https://owasp.org/www-community/Source_Code_Analysis_Tools  
Semgrep(Recommended) - Great open source option  
Sonarqube -- enterprise and free trial --- good !!  
Checkmarx  Veracode HCL Appscan   
CodeQL for Github  -- free for open source github integration  
Bandit for python  
Gosec for go  
many more  

**Integrating SAST into your workflow**  
1. semgrep scan for local development -- pre-commit scans - google for bash code that monitors git diff and scans changed files  
2. Pull request review -- scan.yml code to scan any pull requests before merging them to the branch
3. Integrate with Jenkins pipelines  - using semgrep/sonarqube - docs available

**Triaging SAST findings**  
is it false positive ? is it exploitable ? whats the impact ?  

**SAST Tools limitations**  -- what they miss  
Business logic flaws, authentication/authorization logics, Race conditions, Complex data flows, Configuration issues  

**Best practice for SAST tools usage**  
Start with high confidence rules, tune for your codebases, combine multple tools, integrate with manual review  

## Secure Design Principles  -- stating with design phase  
Secure design principles help developers and reviewers build and assess systems with security in mind from the beginning.  
Core Secure design principles  
1. principle of least privilege
2. Deny by default
3. Seperationg of duties  - seperate authent from authoriz mecha, developers should not deploy code direct without reviews  
4. defence in depth  
5. Complete mediation  -- check perms everytime access is requested not once
6. Open design -- not depend on keeping code secret, instead on proper authen, authori, encryption and key management
7. Acceptability -- dont enforce mfa every 5 mins
8. Minimize attack surface - close unwanted ports
9. Secure defaults and configuration -- cookie attributes, hsts etc
10. Auditability and logging  

## Identifying attack surface in code  
The attack surface of an application includes all the points where an attacker could interact with, manipulate, or exploit the system.  
Why -- helps focus on whats exposed in large codebases, larger the surface more opportunities for bugs and exploitation  

Types: entry points, user inputs, confiuration interfaces, metadata and headers, client side interfaces  

**How to identify attack surface in code**  
1. Start with controller and route handlers  
2. Look for functions that process external data
3. Trace user input from entry to sink  
4. Identify all publicly accessible endpoints  
5. Review front-end inputs that hits the backend  
6. Look for integrations and webhooks  
7. Assess file uploads and downloads  
8. Dont forget background hobs and queues  
9. Map the infrastructure level surface -- open ports, public s3 bucket, bad dns proxies etc  

## Stativ vs Dynamic analysis  
Static Analysis (SAST): Examine the code without running it.  
Dynamic Analysis (DAST): Analyze the application while it is running.  
**SAST** great for early detection, covers all code paths  
Bad -- tools flag false positives, can miss logic flaws, can;t detect misconfigured authenti and access controls  
**DAST**  -- doesnt require code access, effective for business logic and auth and access control  
Bad-- can;t see internal logic or hidden routes, requires running env  

Use SAST during development  
DAST to scan testing/staging app  
run both before release  

## Identifying and Avoiding Hardcoded Secrets  
Secrets --- creds, sshs keys, tokens, access keys, smtp creds etc  
Better --- use env+secretsmanagers, OIDC federation over long lived access tokens,   

gitleaks detect --source . --redact  
trufflehog git file://. --only-verified  

## Labs pending  
lesson 6  exercises  
Lab1 from module 1  



