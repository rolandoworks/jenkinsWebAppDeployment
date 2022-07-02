pipeline {
    agent any
    environment {
        JAVA_HOME="${tool 'JDKDefault'}"
        PATH="${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Cleaning Stage') {
           steps {
              sh "mvn clean"
           }
        } 

        stage('Packaging Stage') {
           steps {
              sh "mvn package"
           }
        }
	
	stage('SonarQube analysis Stage') {
           steps {
               withSonarQubeEnv('sonarqube-tokenized') {
                  sh 'mvn sonar:sonar'
              }
           }
        }    
    }
}
