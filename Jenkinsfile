pipeline {
    agent {
        docker {
            label 'node01'
            image 'python:latest'
        }
    }
    stages {
        stage('Snyk') {
          steps {
            snykSecurity(
              snykInstallation: 'snyk',
              snykTokenId: 'snyktest'
            )
          }
        }
    }
}
