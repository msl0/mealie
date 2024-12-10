pipeline {
    agent none
    stages {
        stage('SonarQube Analysis') {
            agent {
                docker {
                    image 'sonarsource/sonar-scanner-cli'
                    label 'node'
                    args '-v /tmp/.sonar:/opt/sonar-scanner/.sonar'
                }
            }
            steps {
              sh 'mkdir -p /tmp/.sonar && chmod -R 777 /tmp/.sonar'
              sh 'node --version'
              script {
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonarqube') {
                  sh 'node --version' 
                  sh 'sonar-scanner'
                }
              }
            }
        }
    }
}
