pipeline {
    agent {
        node {
            label 'worker_2a'
            }
    }

 stages {  


  stage('SCM') {
    steps { checkout scm}
    
  }
  stage('SonarQube Analysis') {

    steps { 
    withSonarQubeEnv(installationName: 'sonarqubeserver1')  {
      sh "./gradlew org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar"
    }
    }
  }
 }
}
