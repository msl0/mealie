pipeline {
    agent {
        label 'node01'
    }
    stages {
        stage('Snyk') {
          steps {
            echo 'Testing...'
            snykSecurity(
              snykInstallation: 'snyk',
              snykTokenId: 'snyk',
              // place other parameters here
            )
          }
        }
    }
}
