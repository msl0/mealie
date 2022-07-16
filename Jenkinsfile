pipeline {
    agent {
        label 'node01'
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
