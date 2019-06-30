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
              bat "cd hr-api/test-dir && npm install"
      
               bat "cd hr-api/test-dir/test/features && cucumber-js --format json:reports.json features/prod_tests.feature"
            }
        }
       
    }
        
    
}
