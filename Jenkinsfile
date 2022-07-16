pipeline {
    stages {
        stage('Snyk') {
            agent {
                docker {
                    label 'node01'
                    image 'snyk/snyk:python-3.10'
                }
            }
          steps {
            snykSecurity(
              snykInstallation: 'snyk',
              snykTokenId: 'snyktest'
            )
          }
        }
        stage('Snyk2') {
                    agent {
                        docker {
                            label 'node01'
                            image 'snyk/snyk:node-16'
                        }
                    }
                  steps {
                    snykSecurity(
                      snykInstallation: 'snyk',
                      snykTokenId: 'snyktest'
                    )
                  }
                }
    }
}
