pipeline {
    agent {
    	label 'node'
    }
    stages {
        stage('Snyk') {
          steps {
            snykSecurity(
              snykInstallation: 'snyk',
              snykTokenId: 'snyk',
              additionalArguments: '--all-projects'
            )
          }
        }
    }
}
