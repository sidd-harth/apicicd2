pipeline {
  agent any
    tools {
        maven 'M2'
        jdk 'JDK'
        nodejs 'NODEJS'
    }
    stages {
        stage ('pwd1') {
            steps {
                bat "pwd"
            }
        }
stage ('pwd2') {
            steps {
              bat "cd test-dir && npm install"
      
               bat "cd test-dir && gulp test"
            }
        }
       
    }
        
    
}
