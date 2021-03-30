# Running SonarQube in Docker managed by Portainer to test a Maven Project


## Install SonarQube in Docker

sudo docker pull sonarqube

sudo docker run -d --name sonarqube -p 9001:9000 -p 9092:9092 sonarqube  # runs under http://localhost:9001

## Open Portainer to start/stop this Docker image in Browser 

http://localhost:9000/

Open SonarQube in Browser

http://localhost:9001


## Crateing an Admin Token

-> Administration (in top menu)

-> Security

-> Users

-> Update Tokens Icon
Type Token Name 
-> Generate (button)
-> done (button)


it generates token : 63ff9f6e91cb99a16598ffc52050ebc4d533a4ec

## To run the Sonar Test

Open the Java Project folder in terminal 

Run this command

mvn sonar:sonar -Dsonar.host.url=http://buffalo.theworkpc.com:9001 -Dsonar.login=63ff9f6e91cb99a16598ffc52050ebc4d533a4ec

mvn clean verify sonar:sonar -Dsonar.host.url=http://buffalo.theworkpc.com:9001 -Dsonar.login=63ff9f6e91cb99a16598ffc52050ebc4d533a4ec

## Viewing test results

Open SonarQube in Browser

-> Project (in top menu)

### Please note this is a bad Java Project with deliberate codeing errors

