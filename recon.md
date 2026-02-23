## Technology stack identification  
### Check package files  
cat package.json          # Node.js  
cat requirements.txt      # Python  
cat pom.xml              # Java  
cat Gemfile              # Ruby  
cat composer.json        # PHP  

### Check frameworks  
grep -r "import.*express" .    # Express.js  
grep -r "from flask import" .  # Flask  
grep -r "Spring" .             # Spring Boot  

## Architecture Discovery  
### Find entry points  
find . -name "main.*"  
find . -name "*routes*"  
find . -name "*controller*"  

### Find configuration files  
find . -name "*.config.*"  
find . -name "*.env*"  
find . -name "*.yaml"  
find . -name "*.json"  

### Analyze directory structure  
tree -L 3  

## Pattern matching  
### Find dangerous patterns  
grep -rn "eval(" .                    # Code injection  
grep -rn "exec(" .                    # Command injection  
grep -rn "system(" .                  # Command injection  
grep -rn "subprocess.call" .          # Command injection  
grep -rn "innerHTML" .                # XSS  
grep -rn "dangerouslySetInnerHTML" .  # React XSS  
grep -rn "f\".*{.*}\"" .              # Python f-string injection  
grep -rn "\$\{" .                     # Template injection  


