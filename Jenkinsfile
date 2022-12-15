pipeline {
    agent none
    tools {
 
    }
    stages {
        stage('SonarQube Analysis') {
            agent { label 'node01' }
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
