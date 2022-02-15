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
                ${JENKINS_HOME}/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarQube_Scanner/bin/sonar-scanner \
                -D sonar.projectKey=javascript_test11 \
                -D sonar.projectName=javascript_test11 \
                '''
        }
      }
    }
  }
}
