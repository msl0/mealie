pipeline {
    agent {
    	label 'node01'
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
