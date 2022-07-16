pipeline {
    agent {
        docker {
            image 'python:3.10-slim'
            label 'node01'
        }
    }
    stages {
        stage('Snyk') {
          steps {
            sh 'snyk -v' 
            echo 'Testing...'
            snykSecurity(
              snykInstallation: 'snyk',
              snykTokenId: 'snyk'
              // place other parameters here
            )
          }
        }
    }
}
