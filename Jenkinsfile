pipeline {
    agent {
        docker {
            image 'python:3.9-alpine'
            args '-v /var/lib/jenkins/tools/io.snyk.jenkins.tools.SnykInstallation/snyk:/var/lib/jenkins/tools/io.snyk.jenkins.tools.SnykInstallation/snyk'
            label 'node01'
        }
    }
    tools {
      snyk 'snyk'
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
