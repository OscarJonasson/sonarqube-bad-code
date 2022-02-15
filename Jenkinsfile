pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Scan') {
      steps {
        withSonarQubeEnv(installationName: 'sonarqube') { 
           sh '''
                ${scannerHome}/bin/sonar-scanner \
                -D sonar.projectKey=javascript_test11 \
                -D sonar.projectName=javascript_test11 \
                '''
        }
      }
    }
  }
}
