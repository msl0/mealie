pipeline {
    agent none
    stages {
        stage('SonarQube Analysis') {
            agent {
                docker {
                    image 'sonarsource/sonar-scanner-cli'
                    label 'node'
                }
            }
            steps {
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
