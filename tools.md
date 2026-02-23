## Semgrep  
pip install semgrep  
semgrep --config=auto .  //Run with default rules  
//Run with specific rulesets  
semgrep --config=p/owasp-top-ten .  
semgrep --config=p/security-audit .  
semgrep --config=p/secrets .  
// With custom rule  -- Can search or write one  
semgrep --config=custom-rules/ .  
//Output to JSON  
semgrep --config=auto --json -o results.json .  

## Sonarqube  
docker run -d --name sonarqube -p 9000:9000 sonarqube  
#### Scan project  
sonar-scanner \  
  -Dsonar.projectKey=myproject \  
  -Dsonar.sources=. \  
  -Dsonar.host.url=http://localhost:9000  

## Bandit for python specific code  
pip install bandit  
bandit -r . -f json -o bandit-report.json  
bandit -r . -x tests/     //Exclude test files  
bandit -r . -t B201,B301  # Only check eval() and pickle  // Specific tests only  














