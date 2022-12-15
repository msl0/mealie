pipeline {
    agent {
        label 'node01'
    }
    stages {
        stage('SonarQube Analysis') {
            steps {
              script {
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonar') {
                  sh "${scannerHome}/bin/sonar-scanner"
                }
              }
            }
        }
    }
}
