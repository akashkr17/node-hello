pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
     environment {
            CI = 'true'
        }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
                    steps {
                        sh 'npm test'
                    }
                }
                stage('Deliver') {
                            steps {
                                sh 'npm pack'
                                sh 'npm start'
                                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                                sh 'kill $(cat .pidfile)'
                            }
                        }

    }
}
