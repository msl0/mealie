pipeline {
    agent none
    stages {
        stage('SonarQube Analysis') {
            agent {
                docker {
                    image 'sonarsource/sonar-scanner-cli'
                    label 'node'
                    args '-v ${WORKSPACE}/.sonar:/opt/sonar-scanner/.sonar'
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
