pipeline {
    agent {
    	label 'node'
    }
    stages {
        stage('Snyk') {
          steps {
            snykSecurity(
              snykInstallation: 'snyk',
              snykTokenId: 'snyktest',
              additionalArguments: '--all-projects'
            )
          }
        }
    }
}
