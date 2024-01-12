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
                withSonarQubeEnv('sonar') {
                  sh 'node --version' 
                  sh 'sonar-scanner'
                }
              }
            }
        }
    }
}
