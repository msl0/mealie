pipeline {
    agent none
    stages {
        stage('Prepare Environment') {
            agent { label 'node' }
            steps {
                sh 'mkdir -p /tmp/.sonar && chmod -R 777 /tmp/.sonar'
            }
        }
        stage('SonarQube Analysis') {
            agent {
                docker {
                    image 'sonarsource/sonar-scanner-cli'
                    label 'node'
                    args '-v /tmp/.sonar:/opt/sonar-scanner/.sonar'
                }
            }
            steps {
              script {
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonarqube') {
                  sh 'sonar-scanner'
                }
              }
            }
        }
    }
}
