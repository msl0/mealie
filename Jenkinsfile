pipeline {
    agent {
        docker {
            image 'snyk/snyk:python-3.10'
            label 'node01'
        }
    }
    stages {
        stage('Snyk') {
          steps {
            snyk -v 
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
