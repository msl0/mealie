pipeline {
    agent none
    stages {
        stage('Prepare Environment') {
            agent { label 'node' }
            steps {
                // Clean up and create the .sonar directory in the workspace
                sh 'rm -rf ${WORKSPACE}/.sonar'
                sh 'mkdir -p ${WORKSPACE}/.sonar'
            }
        }
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
                withSonarQubeEnv('local_sonar') {
                  sh 'sonar-scanner'
                }
              }
            }
        }
    }
}
