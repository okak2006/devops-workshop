## SonarQube Configuration 

1. Create Sonar cloud account on https://sonarcloud.io
2. Generate an Authentication token on SonarQube
    Account --> my account --> Security --> Generate Tokens 

3. On Jenkins create credentials 
   Manage Jenkins --> manage credentials --> system --> Global credentials --> add credentials
 - Credentials type: `Secret text`
 - ID: `sonarqube-key`
 - Secret: token generated from step 2

4. Install SonarQube plugin
    Manage Jenkins --> Available plugins 
    Search for `sonarqube scanner`

5. Configure sonarqube server 
   Manage Jenkins --> Configure System --> sonarqube server 
   Add Sonarqube server 
   - Name: `sonar-server`
   - Server URL: `https://sonarcloud.io/`
   - Server authentication token: `sonarqube-key`

6. Configure sonarqube scanner 
   Manage Jenkins --> Global Tool configuration --> Sonarqube scanner 
   Add sonarqube scanner 
   - Sonarqube scanner: `sonarqube-scanner`

7. Add Unit Tests Stage in Jenkins

8. Observe Quality Gate (threshold for SonarQube to determine pass or fail)
   Go to SonarQube ---> Projects ---> <organization> ---> Quality Gate
