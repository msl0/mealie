pipeline {
    agent {
        docker {
            image 'python:3.9-alpine'
            label 'node01'
        }
    }
    tools {
      snyk 'snyk'
    }
    stages {
        stage('Snyk') {
          steps {
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
