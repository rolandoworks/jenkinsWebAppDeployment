## Final project: Master CICD and DevOps using Jenkins ##
This was a  Hands-On practice Course on Jenkins admin.

## Motivation: ##
This repo contains a [Jenkinsfile](https://github.com/rolandoworks/jenkinsWebAppDeployment/blob/master/Jenkinsfile) to build, check the code quality and deploy a webApp.war file on a Tomcat server. The Jenkinsfile executes the maven goals, using the [pom.xml](https://github.com/rolandoworks/jenkinsWebAppDeployment/blob/master/pom.xml) configuration file.

#### A video with the complete CI-CD lifecycle (push->package->sonarCheck->deploy->emailNotification) ####
[![img)](view)](https://user-images.githubusercontent.com/54998736/177064552-366da9aa-83e8-4bea-85ae-bb8afbbcb00c.mp4)

### Systems ###
1) The Jenkins instance was running on Tomcat on a remote server (ubuntu 20.04), as well as the SonarQube code analysis instance.

2) The Job is triggered once a new commit is pushed into the github repo or manually from the Jenkins dashboard.

### Note: ###
After a successful run a target/webApp.war artifact is generated and deployed.

