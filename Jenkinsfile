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
              sh 'mkdir -p ${WORKSPACE}/.sonar && chmod -R 777 ${WORKSPACE}/.sonar'
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
