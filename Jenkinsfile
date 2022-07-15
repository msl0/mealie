pipeline {
    agent none
    stages {
        stage('SonarQube Analysis') {
            agent {
                docker {
                    image 'sonarsource/sonar-scanner-cli:latest'
                    label 'node01'
                }
            }
            steps {
              script {
                node = tool 'node.js';
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonar') {
                  sh 'node -version' 
                  sh 'sonar-scanner'
                }
              }
            }
        }
    }
}
