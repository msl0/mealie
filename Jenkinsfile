pipeline {
    agent none
    stages {
        stage('SonarQube Analysis') {
            agent { label 'node01' }
            steps {
              script {
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonar') {
                  sh 'sonar-scanner'
                }
              }
            }
        }
    }
}
