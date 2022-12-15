pipeline {
    agent none
    stages {
        stage('SonarQube Analysis') {
            agent {
                docker {
                    image 'sonarsource/sonar-scanner-cli'
                    label 'node01'
                }
            }
            steps {
              script {
                node = tool 'nodejs';
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
