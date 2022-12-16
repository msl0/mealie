pipeline {
    agent {
        label 'node01'
    }
    environment { 
        DB_ENGINE = 'postgres'
        POSTGRES_SERVER = 'localhost'
    }
    tools {
      nodejs 'nodejs'
    }
    stages {
        stage('Install dependencies') {
            steps {
                script {
                    container = docker.image('postgres').run('-e POSTGRES_USER=mealie -e POSTGRES_PASSWORD=mealie -e POSTGRES_DB=mealie --health-cmd pg_isready --health-interval 10s --health-timeout 5s --health-retries 5 -p 5432:5432')
                }
                sh '''
                    sudo apt update
                    sudo apt install python3 make libsasl2-dev libldap2-dev libssl-dev tesseract-ocr-all -y
                    curl -sSL https://install.python-poetry.org | python3 -
                    export PATH="/var/lib/jenkins/.local/bin:$PATH
                    poetry install
                    poetry add \"psycopg2-binary==2.8.6\"
                    npm i --global yarn
                    cd frontend
                    yarn
                '''
            }
        }
        stage('Tests') {
            steps {
                sh '''
                    yarn test:ci
                    yarn build
                    make backend-test
                '''
            }
        }
        stage('SonarQube Analysis') {
            tools {
              nodejs 'nodejs'
            }
            steps {
              script {
                scannerHome = tool 'SonarScanner';
                withSonarQubeEnv('sonar') {
                  sh 'npm i postcss-sass --save'
                  sh "${scannerHome}/bin/sonar-scanner"
                }
              }
            }
        }
    }
    post { 
        always { 
            script {
                container.stop()
            }
        }
    }
}
