pipeline {
    agent { docker { image 'node:16.17.1-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
                sh 'echo "App is running"'
                sh 'npm pack'
                sh 'npm start'
            }
        }
    }
}
