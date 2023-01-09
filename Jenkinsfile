pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/akashkr17/node-hello'
      }
    }
     
    stage('Build') {
      steps {
        sh 'npm install'
         sh 'npm pack'
         sh 'npm start'
      }
    }  
    
            
    stage('Test') {
      steps {
        sh 'node test'
      }
    }
  }
}
