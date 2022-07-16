pipeline {
    agent none
    environment { 
        SNYK_TOKEN = credentials('snyktest') 
    }
    stages {
        stage('Snyk') {
            agent {
                docker {
                    label 'node01'
                    image 'snyk/snyk:python-3.10'
                }
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
