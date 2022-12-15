pipeline {
    agent none
    stages {
        stage('SonarQube Analysis') {
            agent { label 'node01' }
            steps {
              script {
                node = tool 'nodejs';
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonar') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
              }
            }
        }
    }
}
