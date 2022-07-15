pipeline {
    agent 'node'
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
