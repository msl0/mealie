pipeline {
    agent {
        label 'node01'
    }
    stages {
        stage('SonarQube Analysis') {
            tools {
              nodejs 'nodejs'
            }
            steps {
              script {
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonar') {
                  sh 'npm i postcss-sass --save'
                  sh "${scannerHome}/bin/sonar-scanner"
                }
              }
            }
        }
    }
}
