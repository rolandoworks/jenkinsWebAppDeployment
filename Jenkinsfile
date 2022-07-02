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

	stage('Deploying Stage') {
           steps {
               input('Do you want to deploy the ${currentBuild.currentResult} file to Tomcat?')
                  deploy adapters: [tomcat9(credentialsId: 'TomcatDeploymentUser', path: '', url: 'http://192.241.159.67:8080/')], contextPath: 'jenkinsWebAppDeployment', war: 'target/*.war'
            }
        }    
    }
}
