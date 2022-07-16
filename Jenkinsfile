pipeline {
    agent {
        docker {
            label 'node01'
            image 'snyk/snyk'
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
