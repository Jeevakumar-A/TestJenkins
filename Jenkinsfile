
pipeline {
    agent any
    stages {
        stage('Build') {
            agent{
                docker{
                    image "node:18-alpine"
                    args '-v $HOME/.npm:/root/.npm'
                    reuseNode true
                }
            }
            steps {
                sh 'ls -la'
                sh 'node --version'
                sh 'npm --version'
                sh 'npm ci --no-audit'
                sh 'npm audit fix'
                sh 'ls -la'
            }
        }
    }
}
