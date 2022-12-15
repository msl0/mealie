pipeline {
    agent none
    tools {
        maven 'apache-maven-3.0.1' 
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
