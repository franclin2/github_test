pipeline {
    agent { label 'ubuntu-latest' }

    stages {
        stage('Checkout Repository') {
            steps {
                checkout scm
            }
        }

        stage('Setup Node.js') {
            steps {
                sh 'curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -'
                sh 'sudo apt-get install -y nodejs'
            }
        }

        stage('Run npm Tests') {
            steps {
                sh 'npm install'
                sh 'npm test'
            }
        }
    }
}
